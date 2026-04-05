🤖 Multi-Agent AI Orchestrator
A robust, serverless multi-agent system designed to manage tasks and schedules using natural language. This project demonstrates how a Primary Agent can coordinate specialized Sub-Agents (Tools) to interact with databases and external APIs.

🚀 Features
Primary Orchestrator: Uses a ReAct (Reasoning + Acting) loop to decompose complex user prompts.

Specialized Sub-Agents: * Task Agent: Interfaces with a database to create, retrieve, and update to-dos.

Schedule Agent: Manages calendar events and time-slot logic.

Serverless Deployment: Fully containerized and optimized for Google Cloud Run.

Interactive UI: Integrated Gradio chat interface for real-time testing.

🛠️ Tech Stack
Language: Python 3.11

Frameworks: FastAPI, LangGraph, LangChain

LLM: OpenAI GPT-4o / GPT-4 Turbo

Infrastructure: Docker, Google Cloud Build, Google Cloud Run

Frontend: Gradio

🏗️ Architecture
The system follows a modular architecture:

API Gateway (FastAPI): Receives user requests and handles authentication.

Orchestration Layer (LangGraph): Manages the state of the conversation and decides which tool to call next.

Tool Layer (MCP-inspired): Functions that execute specific actions like SQL queries or API calls.

💻 Installation & Setup
Local Development
Clone the Repo

Bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
Install Dependencies

Bash
pip install -r requirements.txt
Environment Variables
Create a .env file and add:

Code snippet
OPENAI_API_KEY=your_api_key_here
Run the App

Bash
uvicorn main:app --reload
☁️ Deployment
This project is designed to be deployed via Google Cloud Run.

Bash
gcloud run deploy agent-service \
    --source . \
    --region us-central1 \
    --allow-unauthenticated \
    --set-env-vars OPENAI_API_KEY="your-key-here"
📝 Example Usage
User Input: > "I have a big presentation on Friday. Add it to my tasks and clear my Thursday afternoon calendar for preparation."

Agent Response:

"I've added 'Friday Presentation' to your task list with high priority. I also identified 3 meetings on Thursday afternoon and moved them to Monday morning to give you prep time."
