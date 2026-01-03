# 🧠 Multi-LLM Consensus Engine for Domain Productivity  
### (Smart GitHub Repository Analyzer)

---

## 📌 Problem Statement

In productivity-driven domains such as education, finance, healthcare, telecom, and software engineering, users increasingly rely on Generative AI systems to understand, analyze, and reason over complex codebases and documents. However, most existing AI-powered analysis tools depend on a **single Large Language Model (LLM)**, making them vulnerable to hallucinations, bias, incomplete reasoning, and inconsistent outputs.

The problem addressed in this project is the lack of **reliable, trustworthy, and explainable AI-driven repository analysis**, especially when used for productivity-critical tasks such as code understanding, architectural review, and technical decision-making.

---

## 💡 Proposed Solution

This project implements a **Multi-LLM Consensus Engine** embedded within a **Smart GitHub Repository Analyzer**.

Instead of relying on a single LLM, the system:
- Queries **multiple LLMs independently**
- Collects and embeds their responses
- Computes semantic agreement using similarity scoring
- Produces a **final consensus-based answer**

> One model can be wrong.  
> Multiple independent models agreeing is stronger.

---

## 🏗️ System Architecture

User Query
↓
Prompt Normalization
↓
LLM Fan-Out (Independent Calls)
├── LLaMA / Groq LLM
├── Model-B (Future)
└── Model-C (Future)
↓
Response Collection
↓
Embedding Generation
↓
Similarity Scoring (Cosine Similarity)
↓
Consensus Decision Layer
↓
Final Answer


---

## 🧠 AI & ML Concepts Used

### Generative AI
- Large Language Models (LLMs)
- Prompt Engineering
- Context Engineering
- Multi-model inference
- Token generation control

### Machine Learning
- Text embeddings
- Vector similarity (cosine similarity)
- BM25 document ranking
- Semantic agreement scoring

### Agentic & Advanced Concepts
- Multi-model orchestration
- Consensus-based reasoning
- LLM-as-components architecture
- Foundations for Agentic AI extension

---

## 🔧 Technology Stack

### Frontend
- **Streamlit** (>=1.23.1)

### Backend
- **Python** 3.12

### LLM Integration
- **Groq API** (groq>=0.4.0)
- Custom `GroqLLM` class (LangChain-compatible)

### Frameworks & Libraries
- LangChain (`langchain`, `langchain-core`, `langchain-community`)
- NLTK (tokenization with `punkt_tab`)
- rank-bm25 (document ranking)
- pandas (data processing)
- GitPython (repository cloning)
- Plotly & NetworkX (visualizations)
- python-dotenv (environment management)

---

## 📁 Project Structure

/Intelligent-Github-Repository-Analyzer/
├── main.py # Main Streamlit application (~2337 lines)
├── repo_reader.py # Git repository cloning & indexing
├── questions.py # Question context & handling
├── utility.py # Tokenization & helper utilities
├── requirements.txt # Python dependencies
├── .env # Environment variables (API keys)
├── README.md # Project documentation
├── PROJECT_SUMMARY.md # Development snapshot
├── repo_cache/ # Cached repositories
└── pycache/


---

## ⚙️ Key Features

### Repository Analysis
- Clone and analyze public GitHub repositories
- File indexing with caching
- Support for multiple file types (py, md, txt, etc.)

### Intelligent Question Answering
- Ask natural-language questions about codebases
- Context-aware answers using ranked documents
- Conversation history tracking

### Retrieval & Ranking
- BM25-based document ranking
- Tokenization using NLTK
- Context window optimization

### Visualization
- Repository structure visualization
- Dependency and architecture graphs
- Code statistics dashboards

---

## 🔁 Consensus Strategy (Planned Extension)

1. Each LLM receives the **same prompt**
2. Models operate **independently**
3. Each response is embedded using a common embedding model
4. Pairwise cosine similarity is computed
5. The response with the **highest average agreement** is selected

This ensures:
- Reduced hallucination risk
- Improved reliability
- Transparent decision logic

---

## ▶️ How to Run

### Install Dependencies
```bash
pip install -r requirements.txt

NLTK Setup

python3 -c "import nltk; nltk.download('punkt_tab')"

Set API Key

export GROQ_API_KEY=your_key

Run Application

python3 -m streamlit run main.py

Access at:

    http://localhost:8501

📊 Evaluation & Guardrails
Evaluation

    Semantic agreement analysis

    Manual qualitative validation

    Failure and disagreement analysis

Guardrails

    Timeout handling

    Fallback logic

    Input sanitization

    Output consistency checks

Known Limitations

    Increased latency with multi-model inference

    API cost considerations

    Consensus does not guarantee absolute correctness

🧪 Reproducibility

    Deterministic prompts

    Version-controlled code

    Configurable model parameters

    Clear separation of UI and logic

🚀 Future Scope

    Multi-LLM consensus implementation

    Retrieval-Augmented Generation (RAG) with ChromaDB

    Agentic task execution

    Domain-based model weighting

    FastAPI backend for production deployment

    Dockerization & CI/CD

📜 Assumptions

    API keys are provided by the user

    Internet access is available

    Local LLMs are pre-downloaded if used

🤖 AI Tool Usage Disclosure

This project was developed using:

    GitHub Copilot (code assistance)

    ChatGPT (design and architectural guidance)

AI interaction logs are retained as per hackathon guidelines.
🏁 Conclusion

This project demonstrates a scalable, defensible, and production-oriented Generative AI system that moves beyond single-model limitations by combining repository intelligence, retrieval techniques, and multi-model consensus reasoning to improve reliability in productivity-focused applications.
