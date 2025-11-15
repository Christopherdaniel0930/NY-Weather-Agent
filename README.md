💠 Weather & Time Agent — Google ADK

AI Agent powered by Google’s Agent Development Kit (ADK) + Gemini Models

<p align="center"> <img src="https://img.shields.io/badge/Google-ADK-blue?style=for-the-badge&logo=google" /> <img src="https://img.shields.io/badge/Python-3.10+-green?style=for-the-badge&logo=python" /> <img src="https://img.shields.io/badge/Gemini%20Model-Flash%202.0-orange?style=for-the-badge&logo=google" /> <img src="https://img.shields.io/badge/License-MIT-purple?style=for-the-badge" /> </p> <p align="center"> <img src="https://raw.githubusercontent.com/google/adk-python/main/assets/agent-development-kit.png" width="420px"/> </p>
🚀 Overview

This project demonstrates how to build a simple yet functional AI-powered Agent using Google ADK (Agent Development Kit).

The agent can:

✔ Return current time in a supported city
✔ Return weather conditions (sample data)
✔ Use the Gemini gemini-2.0-flash model
✔ Respond interactively using ADK’s CLI runner

🧠 Features

🌤 Weather Tool — returns a sample weather report

⏰ Time Tool — returns live time using Python ZoneInfo

🤖 LLM Integration — powered by Gemini Flash 2.0

🔧 ADK Tooling — automatic routing of requests

📦 Clean Project Structure

🧩 Easily expandable (add more tools, workflows, multi-agent systems)

📂 Project Structure
project/
│
├── agent.py         # Defines the agent and its tools
├── __init__.py      # Package initializer
├── .env             # Gemini API key & ADK environment config
└── README.md        # Documentation

🛠 Installation & Setup
1) Clone the repo
git clone https://github.com/your-username/weather-time-agent.git
cd weather-time-agent

2) Create a virtual environment
python -m venv env1
env1\Scripts\activate   # Windows

3) Install dependencies
pip install google-adk

4) Set your .env file

Create a .env file in the root folder:

GOOGLE_GENAI_USE_VERTEXAI=FALSE
GOOGLE_API_KEY=YOUR_GEMINI_API_KEY


Get your API key from:
🔗 https://aistudio.google.com/app/apikey

▶️ Running the Agent

Run the agent using ADK’s CLI:

adk run weather_time_agent


You will enter an interactive chat environment:

You: What is the time in New York?
Agent: The current time in New York is 2025-02-15 09:12:30 EST-0500

You: What’s the weather in New York?
Agent: The weather in New York is sunny with a temperature of 25°C.


🔧 How the Agent Works

Your agent is defined like this:
(From agent.py)

root_agent = Agent(
    name="weather_time_agent",
    model="gemini-2.0-flash",
    description="Agent to answer questions about the time and weather in a city.",
    instruction="You are a helpful agent.",
    tools=[get_weather, get_current_time],
)

🛠 Tools
get_weather(city)

Returns weather only for New York

Sample data used for demonstration

get_current_time(city)

Uses zoneinfo.ZoneInfo

Returns real system time

📊 Usage Diagram (Architecture Flow)
          ┌────────────────────────────┐
          │        User Query          │
          └──────────────┬─────────────┘
                         ▼
           ┌────────────────────────┐
           │     ADK Root Agent     │
           └────────────┬───────────┘
                        │
        ┌───────────────┼────────────────┐
        ▼                               ▼
┌───────────────┐              ┌─────────────────┐
│  Time Tool     │              │  Weather Tool   │
│ get_time()     │              │ get_weather()   │
└───────────────┘              └─────────────────┘
        │                               │
        └───────────────┬───────────────┘
                        ▼
           ┌────────────────────────┐
           │      Gemini LLM        │
           │  gemini-2.0-flash      │
           └────────────┬───────────┘
                        ▼
           ┌────────────────────────┐
           │    Final Response       │
           └────────────────────────┘

🧩 Expand This Agent

You can extend this project by adding:

🌍 More cities

🌦 Real weather API integration (OpenWeatherMap, AccuWeather)

🗺️ Maps search tool

📰 News fetching tool

🎤 Voice input (FastAPI + Speech-to-Text)

🤝 Multi-agent workflows (Planner → Tools → Reporter)

Want me to build any of these for you?
Just ask — I can generate the code instantly.

🐞 Troubleshooting
❌ API key not valid

Fix your .env:

GOOGLE_API_KEY=your_key_here


Restart terminal.

❌ Windows symlink error

Enable Developer Mode or run as Administrator.

📜 License

MIT License © 2025 — Christopherdaniel0930
