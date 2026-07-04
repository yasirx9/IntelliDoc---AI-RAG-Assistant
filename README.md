<div align="center">

# ⚡ IntelliDoc — AI RAG Assistant

### _Intelligent Document Analysis Powered by RAG, LangChain & LangGraph_

A three-mode question-answering system that lets you upload any PDF and interact with it through **document-only retrieval**, **AI-enhanced answers**, or **live web search** — all from a beautiful, modern interface.

</div>

---

## 🌟 About the Journey

This project is the **Capstone Project** of the **AI Bootcamp**, held in collaboration with **iCodeGuru** and **DigiTech**. The bootcamp was an incredible, transformative learning experience that took me from the fundamentals of AI all the way to building production-grade applications.

Throughout the bootcamp, I had the privilege of:

- 🧠 **Deep-diving into Retrieval-Augmented Generation (RAG)** — learning how to ground AI responses in real documents to produce accurate, trustworthy answers instead of hallucinations
- 🔗 **Mastering LangChain & LangGraph** — building composable AI chains and multi-step agent workflows that can reason, retrieve, and act autonomously
- 📊 **Working with Vector Databases & Embeddings** — understanding how to convert human language into mathematical representations and perform semantic search at scale with FAISS
- 🌐 **Building Agentic AI Systems** — designing LangGraph agents that can search the web in real-time using Tavily and synthesize information from multiple sources
- 🚀 **Full-Stack AI Deployment** — creating production APIs with FastAPI, connecting them to modern frontends, and deploying to cloud platforms

The mentorship, the community, and the hands-on projects at **iCodeGuru × DigiTech** were genuinely inspiring. Every session pushed me to think bigger, build better, and understand the real-world impact of AI. This capstone project is a reflection of everything I learned — from embedding models to agentic reasoning — packed into one cohesive application.

> _"The best way to learn AI is to build with it — and this bootcamp gave me exactly that opportunity."_

## 👨‍💻 Author

<div align="center">

### Muhammad Yasir

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yasirx9/)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://yasirportfolio.page.gd/?i=1)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yasirx9)

---

## 🎯 Three Powerful Modes

| Mode | What It Does |
|:----:|:-------------|
| **📄 Document Only** | Answers strictly from your uploaded PDF. No outside knowledge. Pure retrieval. |
| **🧠 Document + AI** | Uses the document first, then supplements with general AI knowledge when the document is insufficient. Clearly prefixes additions with "From general knowledge:". |
| **🌐 Web Search** | Ignores any local document. Uses Tavily to fetch live search results, then answers with Groq. Perfect for real-time questions. |

---

## 📁 Project Structure

```
IntelliDoc/
├── index.html         # Premium dark-mode chat UI
├── main.py            # FastAPI server — four endpoints
├── ingestion.py       # CLI: embed a PDF and save a FAISS index
├── rag.py             # Core RAG module: get_answer(question)
├── agent.py           # LangGraph web-search agent (mode 3)
├── requirements.txt   # Python dependencies
├── .env               # API keys (never commit this)
└── deployment.md      # Railway + Vercel deployment guide
```

---

## 🛠️ Setup

```bash
# 1. Create and activate virtual environment
python -m venv .venv

# Windows:
.venv\Scripts\activate
# Mac/Linux:
source .venv/bin/activate

# 2. Install dependencies
pip install -r requirements.txt
```

Copy `.env` and fill in your keys:

```env
GROQ_API_KEY=gsk_...
TAVILY_API_KEY=tvly-...
```

---

## 🚀 Usage

### Option A — CLI Ingestion + API

```bash
# 1. Ingest a PDF
python ingestion.py --file your_document.pdf

# 2. Start the API
uvicorn main:app --reload

# 3. Open index.html in a browser
```

### Option B — Upload via the UI

Start the API first, then upload a PDF directly from the sidebar in `index.html`.

---

## 📡 API Endpoints

| Method | Path | Description |
|:------:|:----:|:------------|
| `GET`  | `/health` | Health check |
| `GET`  | `/index-status` | Returns `{"indexed": true/false}` |
| `POST` | `/ingest` | Upload a PDF (multipart form) → `{"status":"ok","chunks":N}` |
| `POST` | `/ask` | `{"question": str, "mode": 1\|2\|3}` → `{"answer": str, "sources": [...]}` |

---

## 🏗️ Tech Stack

| Component | Technology |
|:---------:|:-----------|
| **LLM** | Groq (`llama-3.3-70b-versatile`) |
| **Embeddings** | HuggingFace `all-MiniLM-L6-v2` (local, no API key needed) |
| **Vector Store** | FAISS (local disk) |
| **Agent** | LangGraph (two-node graph for web search) |
| **Web Search** | Tavily |
| **API** | FastAPI + Uvicorn |
| **Frontend** | Vanilla HTML/CSS/JS — dark-mode glassmorphism design |

---

</div>

---

<div align="center">

_Built with ❤️ during the AI Bootcamp by iCodeGuru × DigiTech_

</div>
