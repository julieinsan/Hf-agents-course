# :hugs: Hf-agents-course
My notes for the HF agents course: [here](https://huggingface.co/learn/agents-course/unit0/introduction).


## Unit 1: Introduction to Agents

The Generic Tool Class example:

```python

class Tool:
    """
    A class representing a reusable piece of code (Tool).
    
    Attributes:
        name (str): Name of the tool.
        description (str): A textual description of what the tool does.
        func (callable): The function this tool wraps.
        arguments (list): A list of argument.
        outputs (str or list): The return type(s) of the wrapped function.
    """
    def __init__(self, 
                 name: str, 
                 description: str, 
                 func: callable, 
                 arguments: list,
                 outputs: str):
        self.name = name
        self.description = description
        self.func = func
        self.arguments = arguments
        self.outputs = outputs

    def to_string(self) -> str:
        """
        Return a string representation of the tool, 
        including its name, description, arguments, and outputs.
        """
        args_str = ", ".join([
            f"{arg_name}: {arg_type}" for arg_name, arg_type in self.arguments
        ])
        
        return (
            f"Tool Name: {self.name},"
            f" Description: {self.description},"
            f" Arguments: {args_str},"
            f" Outputs: {self.outputs}"
        )

    def __call__(self, *args, **kwargs):
        """
        Invoke the underlying function (callable) with provided arguments.
        """
        return self.func(*args, **kwargs)
```

We can use Python's ```inspect``` module to retrieve the info for us, then use @tool decorator.

```python
@tool
def calculator(a: int, b: int) -> int:
    """Multiply two integers."""
    return a * b

print(calculator.to_string())
```

the ```to_string``` method generates the text to insert into the system prompt for the LLM to know about the tool.

![image](https://github.com/user-attachments/assets/54a1d69a-1269-4265-8ac8-29dc9fd82034)

## Thought-Action-Observation

## Thought Process

**ReAct approach** "Let's think step by step"


![image](https://github.com/user-attachments/assets/3a2a9870-a504-482d-90cc-248ba268324c)


## Actions: Enabling Agent to Engage with Environment

Different types of agents: 

* JSON Agent: Action to take is specified in JSON format
* Code Agent: Agent writes a block of code that is interpreted externally
* Function-calling Agent: Subcategory of JSON Agent which has been fine-tuned to generate a new message for each action.

Types of Actions:

* Information Gathering: web searches, query db, retrieve docs
* Tool Usage: API call, calculations, execute code
* Env Interaction: manipulating digital interfaces or controlling physical devices
* Communication: Engage with user via chat or collab with other agents

![image](https://github.com/user-attachments/assets/77fc2bb0-9573-44e4-9aac-07413b7315eb)
