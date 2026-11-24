# LLM Question Answering Workflow using LangGraph

## Overview

This project demonstrates how to build a simple **LLM-based Question Answering Workflow** using LangGraph.

The workflow integrates a Large Language Model (LLM) into a graph-based execution system to process user questions and generate relevant answers.

It follows a sequential execution pattern in which the input question is passed through an LLM node, processed by the model, and returned as the final answer.

The main objective is to understand how LangGraph manages workflow execution, state, nodes, and edges while integrating an LLM into an application.

## Workflow Architecture

The project follows a simple sequential workflow:

```text
       START
          |
          v
    User Question
          |
          v
      LLM QA Node
          |
          v
    Generate Answer
          |
          v
         END
```

## How It Works

1. **Initialize State:** Define the workflow state using Python's `TypedDict`, containing the question and answer fields.
2. **Initialize LLM:** Load the Hugging Face language model using LangChain's HuggingFacePipeline integration.
3. **Create LLM Node:** Define a Python function that receives the current state, extracts the question, and sends it to the LLM.
4. **Generate Response:** The LLM processes the prompt and generates an answer.
5. **Update State:** Store the generated answer in the workflow state.
6. **Build Graph:** Create a `StateGraph`, register the LLM node, and connect the START and END nodes.
7. **Compile and Execute:** Compile the graph and invoke it with the initial input state to retrieve the final result.

## Key Concepts Covered

- **LangGraph:** Building and executing graph-based workflows.
- **StateGraph:** Defining the structure of the workflow.
- **TypedDict:** Defining the workflow state and its data structure.
- **Nodes:** Implementing individual processing tasks using Python functions.
- **Edges:** Defining the execution flow between nodes.
- **START and END:** Defining workflow entry and exit points.
- **LLM Integration:** Connecting a language model to a LangGraph node.
- **State Management:** Passing and updating information throughout workflow execution.
- **Graph Compilation:** Converting the graph definition into an executable workflow.

## Technologies Used

- Python
- LangGraph
- LangChain
- Hugging Face Transformers
- HuggingFacePipeline
- Qwen2.5-0.5B-Instruct

## Project Structure

```text
LLM_Sequential_Workflow/
│
├── llm_workflow.ipynb
├── README.md
└── requirements.txt
```

## Installation

Install the required libraries:

```bash
pip install -U langgraph langchain langchain-huggingface transformers accelerate torch
```

## Model

This project uses **Qwen2.5-0.5B-Instruct**, a lightweight instruction-tuned language model from Hugging Face.

The model runs locally through the Transformers pipeline, so a hosted LLM API key is not required.

## Learning Outcomes

Through this project, I learned how to:

- Integrate an LLM into a LangGraph workflow.
- Define and manage workflow state using `TypedDict`.
- Create nodes using Python functions.
- Connect nodes using graph edges.
- Compile and execute a sequential workflow.
- Pass user inputs to an LLM and retrieve generated responses.
- Understand how LangGraph orchestrates LLM execution.







