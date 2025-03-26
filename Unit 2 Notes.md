# Unit 2: Introduction to Agentic Frameworks

* smolagents
* LLamaIndex
* LangGraph

With Agentic Frameworks, you get:

* LLM engine to power the system
* list of tools the agent can access
* parser for extracting tool calls from the LLM output
* system prompt synced with the parser
* memory system
* error logging and retry mechanisms to control LLM mistakes.

## Unit 2.1: Smolagents

`CodeAgents` are the primary type of agent in `smolagents`. These agents produce python code to perform actions.

### Why use smolagents

It's simple, works with any LLM through integration with HF tools and external APIs. First-class support for Code Agents, has seamless integration with HF Hub, allowing the use of Gradio Spaces as tools.

![image](https://github.com/user-attachments/assets/bba82476-2f34-4380-b0b5-2ee160d23b6f)





![image](https://github.com/user-attachments/assets/5cb2ff81-86ee-448e-9aed-3583e1fc934e)

## Why Code Agents?

Research shows that tool-calling LLMs work more effectively with code directly rather than parsing JSON to determine which tool to use. 

Advantages:

* **Composability**: Easily combine and reuse actions
* **Object Management**: Work directly with complex structures like images
* **Generality**: Express any computationally possible task
* **Natural for LLMs**: High-quality code is already present in the LLM training data.
[<img src="https://cdn-icons-png.flaticon.com/512/2883/2883482.png" width="25" />]()





