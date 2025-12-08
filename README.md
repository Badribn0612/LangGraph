# LangGraph Learning Repository

This repository contains a collection of Jupyter notebooks exploring various concepts and patterns in LangGraph, a library for building stateful, multi-actor applications with LLMs (Large Language Models).

## Overview

LangGraph enables the creation of complex AI workflows with multiple agents, state management, and flexible graph-based architectures. This repository serves as a learning resource covering fundamental concepts to advanced patterns.

## Prerequisites

- Python 3.11+
- Virtual environment (recommended)
- API keys for LLM providers (Anthropic, OpenAI, etc.)
- Environment variables configured in `.env` file

## Installation

1. Create and activate a virtual environment:
```bash
python -m venv langgraph
source langgraph/bin/activate  # On Windows: langgraph\Scripts\activate
```

2. Install dependencies:
```bash
pip install langgraph langchain langchain-openai langchain-anthropic langchain-community langchain-tavily langchain-text-splitters
```

3. Set up environment variables:
Create a `.env` file in the root directory with your API keys:
```
ANTHROPIC_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here
TAVILY_API_KEY=your_key_here
```

## Notebooks

### 1. Simple Chatbot (`simple_chatbot.ipynb` & `simple_chatbot.py`)
- **Description**: Basic introduction to LangGraph with a simple chatbot implementation
- **Concepts**: 
  - StateGraph creation
  - Node and edge definition
  - Basic message handling
  - Streaming responses
- **Key Learning**: Understanding the fundamental structure of a LangGraph application

### 2. Chatbot with Conversation Memory (`chatbot_with_conversation_memory.ipynb`)
- **Description**: Extends the simple chatbot with persistent conversation memory
- **Concepts**:
  - MemorySaver for checkpointing
  - State persistence across conversations
  - Production-ready memory solutions (SqliteSaver, PostgresSaver)
- **Key Learning**: How to maintain conversation context and state

### 3. Chatbot with Search (`chatbot_with_search.ipynb`)
- **Description**: Adds web search capabilities to the chatbot using Tavily
- **Concepts**:
  - Tool binding to LLMs
  - Tool invocation patterns
  - Integrating external APIs
- **Key Learning**: Extending agent capabilities with tools

### 4. Exploring Agents (`exploring_agents.ipynb`)
- **Description**: Exploration of prebuilt ReAct agents and their capabilities
- **Concepts**:
  - `create_react_agent` from `langgraph.prebuilt`
  - Structured outputs with agents
  - Custom prompts for agents
  - Model initialization patterns
- **Key Learning**: Using prebuilt agent components vs building from scratch

### 5. Agent Supervisor (`agent_supervisor.ipynb`)
- **Description**: Multi-agent system with a supervisor agent coordinating specialized agents
- **Concepts**:
  - Supervisor pattern
  - Specialized agent creation (research agent)
  - Multi-agent coordination
  - Agent routing and delegation
- **Key Learning**: Building complex multi-agent systems

### 6. Async LangGraph (`async_langgraph.ipynb`)
- **Description**: Asynchronous patterns in LangGraph
- **Concepts**:
  - Async/await with LangGraph
  - `ainvoke` for async execution
  - Async node definitions
- **Key Learning**: Performance optimization through async operations

### 7. Agentic RAG (`agentic_rag.ipynb`)
- **Description**: Retrieval-Augmented Generation implementation using agents
- **Concepts**:
  - Document loading and splitting
  - Vector store creation (InMemoryVectorStore)
  - Embeddings and retrieval
  - RAG patterns with LangGraph
- **Key Learning**: Combining retrieval systems with agent workflows

### 8. Corrective RAG (`corrective_rag.ipynb`)
- **Description**: Advanced RAG pattern with retrieval grading and correction
- **Concepts**:
  - Retrieval quality assessment
  - Self-correction mechanisms
  - Advanced RAG workflows
- **Key Learning**: Improving RAG accuracy through feedback loops

### 9. LangGraph Agents (`langgraph_agents.ipynb`)
- **Description**: Advanced agent patterns including recursion limits
- **Concepts**:
  - Recursion limits and error handling
  - `GraphRecursionError` management
  - Configuring agent iteration limits
  - Tool integration patterns
- **Key Learning**: Controlling agent behavior and preventing infinite loops

## Project Structure

```
LangGraph/
├── README.md                          # This file
├── .gitignore                         # Git ignore rules
├── documentation.txt                  # Reference links and package ecosystem
├── simple_chatbot.py                  # Simple chatbot script
├── simple_chatbot.ipynb               # Simple chatbot notebook
├── chatbot_with_conversation_memory.ipynb
├── chatbot_with_search.ipynb
├── exploring_agents.ipynb
├── agent_supervisor.ipynb
├── async_langgraph.ipynb
├── agentic_rag.ipynb
├── corrective_rag.ipynb
├── langgraph_agents.ipynb
└── langgraph/                         # Virtual environment directory
```

## Key Concepts Covered

### State Management
- TypedDict for state definition
- Annotated types with reducer functions (`add_messages`)
- State updates and persistence

### Graph Construction
- `StateGraph` creation
- Node addition and configuration
- Edge definition (START, END, conditional edges)
- Graph compilation

### Agents
- ReAct agent pattern
- Tool integration
- Structured outputs
- Custom prompts and configurations

### Advanced Patterns
- Multi-agent systems
- Supervisor patterns
- RAG implementations
- Async execution
- Error handling and recursion limits

## LangGraph Package Ecosystem

As documented in `documentation.txt`, the LangGraph ecosystem includes:

- **langgraph** (base): Core LangGraph functionality
- **langgraph-prebuilt**: Prebuilt components for creating agents
- **langgraph-supervisor**: Tools for building supervisor agents
- **langgraph-swarm**: Tools for building swarm multi-agent systems
- **langchain-mcp-adapters**: Interfaces to MCP servers
- **langmem**: Agent memory management (short-term and long-term)
- **agentevals**: Utilities to evaluate agent performance

## Resources

- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [LangGraph Tutorials](https://langchain-ai.github.io/langgraph/tutorials/introduction/)
- [ReAct Agent Guide](https://langchain-ai.github.io/langgraph/how-tos/react-agent-from-scratch/)
- [Agent Overview](https://langchain-ai.github.io/langgraph/agents/overview/)
- [Tool Usage Documentation](https://langchain-ai.github.io/langgraph/agents/tools/)

## Notes

- All notebooks use environment variables from `.env` file
- The virtual environment directory (`langgraph/`) is excluded from git
- Some notebooks may require additional dependencies (check individual notebook cells)
- API keys should never be committed to version control

## Contributing

This is a personal learning repository. Feel free to explore and adapt the code for your own learning purposes.

## License

This repository is for educational purposes.

