# Example A2A Agent

This repository implements a simple Agent-to-Agent (A2A) communication example based on Google's A2A protocol. A2A is Google's proposed standard for enabling AI agents to communicate with each other through a standardized API.

## Overview

The implementation consists of two main components:

1. **Server (server.py)**: A Flask-based server that implements the A2A protocol endpoints:
   - `/.well-known/agent.json` - Provides the agent's metadata (Agent Card)
   - `/tasks/send` - Accepts and processes tasks from other agents

2. **Client (client.py)**: A simple client that demonstrates how to:
   - Discover an agent by fetching its Agent Card
   - Send a task to the agent
   - Process the agent's response

The example agent has web search capabilities using Brave Search through the Model Context Protocol (MCP).

## Setup

1. Create a virtual environment:

   **Windows**:
   ```
   python -m venv venv
   venv\Scripts\activate
   ```

   **macOS/Linux**:
   ```
   python3 -m venv venv
   source venv/bin/activate
   ```

2. Create a `.env` file based on the `.env.example` template:
   ```
   GEMINI_API_KEY=
   BRAVE_API_KEY=your_brave_api_key
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Run the server:
   ```
   python server.py
   ```

5. In a separate terminal, run the client (make sure to activate the virtual environment first):
   ```
   python client.py
   ```

## A2A Protocol

Google's A2A protocol defines a standard way for agents to communicate with each other through HTTP endpoints. The key components include:

- **Agent Card**: A JSON document that describes an agent's capabilities and endpoints
- **Task API**: Endpoints for sending tasks to agents and receiving responses
- **Standardized Message Format**: A consistent structure for messages exchanged between agents

For more information on Google's A2A protocol, refer to the official documentation.
