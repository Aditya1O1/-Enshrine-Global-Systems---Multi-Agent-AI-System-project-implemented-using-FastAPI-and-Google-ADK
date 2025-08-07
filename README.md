# 🧠 Enshrine Global Systems – Multi-Agent AI System

**Author:** Aditya Kumar Pandey  
**Program:** MTech (AI & Data Science)  
**Institution:** Indian Institute of Information Technology, Bhagalpur  

---

## 📌 Overview

This project implements a **Multi-Agent AI System** using FastAPI and Google Colab that can dynamically execute user-defined goals by chaining intelligent agents. The system supports real-world queries like:

- “Get the current Bitcoin price and summarize sentiment”
- “Find the next SpaceX launch and weather at launch site”

It is designed to be modular, explainable, and extensible.

---

## 🧭 System Architecture

### 🔹 User Goal Input
Users provide a goal in natural language (e.g., *“Get Bitcoin price and summarize sentiment”*).

### 🔹 Planner Agent
- Parses the goal into sub-tasks
- Selects appropriate agents for execution

### 🔹 Agent Chain Execution
Each agent handles a part of the pipeline and passes output to the next:

1. **Data Fetcher** – Calls APIs to collect real-world data  
2. **Validator / Enhancer** – Enhances or verifies raw data (e.g., weather for launch site)  
3. **Summarizer** – Consolidates all agent outputs into a human-readable response

### 🔹 Final Output
A structured, summarized response is returned to the user or API caller.

---

## 🧠 Agents in Action

| Agent           | Functionality |
|----------------|----------------|
| **Planner Agent** | Parses input, determines sequence of actions |
| **SpaceX Agent** | Fetches next launch data using SpaceX API |
| **Weather Agent** | Gets weather forecast via OpenWeatherMap API |
| **Bitcoin Agent** | Fetches real-time BTC price using CoinGecko |
| **Sentiment Agent (Optional)** | Uses NewsAPI for recent crypto news |
| **Summarizer Agent** | Generates final structured summary |

---

## 🚀 API & Usage

### ⚙️ FastAPI Endpoints
- `POST /evaluate`: Accepts user goals in JSON and returns multi-agent output
- `GET /evaluations`: Retrieves previous evaluation history

### 🔗 Live Swagger UI
Access the live FastAPI interface:

👉 [Swagger UI](https://b660-35-233-131-53.ngrok-free.app/docs)

### 📥 Example Input
```json
{
  "goal": "Get the current price of Bitcoin and summarize recent sentiment"
}
