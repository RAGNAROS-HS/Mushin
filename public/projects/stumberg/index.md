# Stumberg



Stumberg is my crown jewel. It is my largest personal project so far, and the first in this series. The original idea was to replicate the functionality of chatgpt but tailored to my needs. I hated repeating myself all the time and trying to curb its agreeable responses, so I set out on this journey.

The final product was a working agent with multiple modes, persistent conversations, file context, and a search subagent, all tailored to me. Although I will admit that I have discontinued use and maintenence of the project, as the scope of the project just grew larger and larger, upkeep of API's bugfixing etc, all take lots of time, time which I wanted to spend learning other new things.

Also the usage was not that practical, booting up a docker container and running in localhost is not ideal, if I were to revisit this project I would definitely prioritize having CI/CD and a proper deployment pipeline.

Although the idea of stumberg was somewhat revived in my project "Goswin", you can learn more about it [here](/projects/goswin/).

## ✨ Features

| Feature                      | Description                                                                        |
| ---------------------------- | ---------------------------------------------------------------------------------- |
| **Multi-Mode Operation**     | Four distinct modes with tailored system prompts, model selection, and tool access |
| **Persistent Conversations** | PostgreSQL-backed state with thread-based history and automatic checkpointing      |
| **File Context**             | Per-conversation uploads (txt, md, py, json, pdf) injected into system prompts     |
| **Search Subagent**          | Dedicated subagent with web, Reddit, subreddit, and r/BuyItForLife search          |
| **Vector Search (RAG)**      | Pinecone-powered semantic retrieval for knowledge base querying                    |
| **Weather**                  | Real-time, location-based weather via Open-Meteo                                   |

---

## 🎛️ Modes

| Mode         | Model        | Purpose                                                         |
| ------------ | ------------ | --------------------------------------------------------------- |
| **Personal** | GPT-4o       | Shopping & lifestyle — Reddit + r/BuyItForLife integration      |
| **Work**     | GPT-4o       | Factual research & study — no assumptions                       |
| **Code**     | GPT-4o       | Code creation, debugging & optimization — full output, no fluff |
| **Fast**     | GPT-4.1-nano | Ultra-fast, minimal responses                                   |

---

## 🏗️ Architecture

LangGraph state machine with the following flow:

```mermaid
graph LR
    A[Streamlit UI] --> B[Agent Graph]
    B --> C{Tool Routing}
    C --> D[Weather Tool]
    C --> E[Vector Search]
    C --> F[Search Subagent]
    F --> G[Web Search]
    F --> H[Reddit Search]
    F --> I[Subreddit Search]
    F --> J[BuyForLife Search]
    B --> K[(PostgreSQL)]
```

### Tools

| Tool                  | Source          | Description                             |
| --------------------- | --------------- | --------------------------------------- |
| `get_weather`         | Open-Meteo API  | Real-time weather data                  |
| `retrieve_context`    | Pinecone        | Vector search for RAG                   |
| `ask_search_agent`    | Search Subagent | Delegates to specialized search tools ↓ |
| ↳ `general_search`    | LinkupClient    | Web search                              |
| ↳ `reddit_search`     | PRAW            | Reddit-wide search                      |
| ↳ `subreddit_search`  | PRAW            | Targeted subreddit search               |
| ↳ `buyforlife_search` | PRAW            | r/BuyItForLife scraping                 |

---

## 🛠️ Tech Stack

| Layer             | Technology                                   |
| ----------------- | -------------------------------------------- |
| **Orchestration** | LangGraph                                    |
| **LLM Framework** | LangChain                                    |
| **UI**            | Streamlit                                    |
| **Database**      | PostgreSQL (`langgraph.checkpoint.postgres`) |
| **Models**        | GPT-4o, GPT-4.1-nano (OpenAI)                |
| **Vector DB**     | Pinecone                                     |
| **Web Search**    | LinkupClient                                 |
| **Reddit**        | PRAW                                         |
| **Weather**       | Open-Meteo API                               |
| **Tracing**       | LangSmith *(optional)*                       |

---

## 📁 Project Structure

```
Stumberg/
├── app.py                  # Streamlit interface
├── main.py                 # CLI entry point
├── graph.py                # LangGraph agent graph
├── models.py               # Model configurations
├── prompts.py              # Mode-specific system prompts
├── schema.py               # AgentState definition
├── tools/
│   ├── search.py           # Search tool implementations
│   ├── weather.py          # Weather tool
│   └── vector_search.py    # Pinecone integration
├── subagents/
│   └── search_subagent.py  # Search delegation subgraph
├── middleware/
│   └── call_wrapping.py    # Call wrapping utilities
├── RAG_building_scripts/   # Vector store build utilities
├── Dockerfile
├── requirements.txt
├── langgraph.json          # LangGraph deployment config
└── ROADMAP.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- PostgreSQL
- OpenAI API key

### Install

```bash
pip install -r requirements.txt
```

### Configure

Create a `.env` file:

```env
# Required
OPENAI_API_KEY=your_key
DB_URI=postgresql://user:password@host:port/database

# Optional
PINECONE_API_KEY=your_key
LINKUP_API_KEY=your_key
LANGCHAIN_API_KEY=your_key
LANGCHAIN_PROJECT=your_project
CONVERSATION_DATA_PATH=/path/to/conversation/data
```

### Run

```bash
# Streamlit UI
streamlit run app.py

# CLI
python main.py
```

### Docker

```bash
docker build -t stumberg-agent .
docker run -p 8501:8501 \
  -v /path/to/data:/host_e/conversation_data \
  --env-file .env \
  stumberg-agent
```

---

## 📄 License

Personal use and experimentation.


---

> Author: Hugo Sokołowski-Katzer  
> URL: http://localhost:1313/projects/stumberg/  

