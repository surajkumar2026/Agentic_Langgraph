# Build A Basic Chatbot With Langgraph (GRAPH API)

## Project Overview

This project demonstrates building a basic chatbot using LangGraph’s GRAPH API. It showcases constructing state graphs and managing conversational state through nodes and edges.

## Features

* Implements a chatbot using LangGraph’s `StateGraph` and `add_messages` annotation.
* Demonstrates node creation, state updates, and message flow.
* Example chatbot function using an LLM integration.

## Technologies Used

* Python 3.11+
* LangGraph
* dotenv
* Typing Extensions

## Setup Instructions

1. Clone the repository or download the project files.
2. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Set up environment variables using a `.env` file if required (e.g., LLM API keys).
4. Run the notebook or Python script:

   ```bash
   jupyter notebook chatbot.ipynb
   ```

## How It Works

* A `State` is defined using Python `TypedDict` to hold conversation messages.
* `StateGraph` is created with defined start and end nodes.
* Node functions, like `chatbot(state: State)`, invoke an LLM to generate responses.
* Message flow is handled through graph edges and annotations.

## Example Snippet

```python
class State(TypedDict):
    messages: Annotated[list, add_messages]

def chatbot(state: State):
    return {"messages": [llm.invoke(state["messages"])]}
```

## Author
Suraj kumar
