# EduRAG - Multilingual NCERT Doubt Solver using OPEA-Based RAG Pipeline :

## 🚀 Overview :

EduRAG is a curriculum-locked, multilingual AI tutoring system that answers student doubts strictly from NCERT textbooks (Grades 6–10). Unlike general-purpose LLMs, this system:

- Does NOT use internet knowledge
- Does NOT hallucinate
- Uses only NCERT textbooks
- Provides chapter-level citations
- Supports English, Hindi & Urdu

Built using an OPEA-based modular RAG architecture optimized for Intel CPUs.

## 🎥 Demo

[![EduRAG Demo](https://img.youtube.com/vi/Ws-2bcPOpAI/maxresdefault.jpg)](https://youtu.be/Ws-2bcPOpAI)

**▶️ [Watch the full demo on YouTube](https://youtu.be/Ws-2bcPOpAI)**

## 🎯 Problem It Solves :

### In Indian classrooms:

- Students ask doubts in different languages
- General AI tools hallucinate answers
- No system provides textbook-verified citations
- Most solutions require GPU/cloud infrastructure

### EduRAG solves this by:

- Restricting knowledge to NCERT
- Enabling cross-lingual retrieval
- Running entirely on local CPU
- Providing explainable answers with citations

## 🧠 Architecture (OPEA-Based RAG):

This project follows the Observe → Plan → Execute → Act loop:

### I. Observe
- Detect language (EN / HI / UR)
- Normalize subject & grade

### II. Plan
Apply metadata hard-filtering:
- Grade
- Subject
- Chapter

### III. Execute
- Retrieve relevant chunks using FAISS
- Augment prompt with NCERT context
- Generate answer using Qwen2.5-0.5B-Instruct

### IV. Act
- Provide chapter-level citations
- Store session history
- Collect student feedback

## 🧩 Tech Stack:

### 1.Backend
- FastAPI
- LangChain
- FAISS
- HuggingFace Transformers
- Qwen2.5-0.5B-Instruct
- Multilingual-E5-Small
- Helsinki-NLP Translation Models

### 2.Frontend
- HTML5
- CSS3
- Vanilla JavaScript

## 🌐 Multilingual Support:

| Subject Type | Query Language | Output |
|--------------|---------------|--------|
| Hindi        | Hindi         | Hindi  |
| Urdu         | Urdu          | Urdu   |
| Science      | EN / HI / UR  | Same as query |
| Maths        | EN / HI / UR  | Same as query |
| Social Sci   | EN / HI / UR  | Same as query |

Cross-lingual semantic mapping is enabled using multilingual embeddings.

## 📊 Performance:

* ⏱ Latency: 2.5 – 4.5 seconds (CPU)
* 📚 40+ NCERT textbooks indexed
* 🎯 >85% grounded response accuracy
* 🔎 Top-k metadata-filtered retrieval

## 📁 Project Structure:
```
├── backend/
│   ├── main.py
│   ├── chat_memory.py
│   ├── feedback.py
│   └── feedback_store.json
│
├── rag/
│   └── rag_pipeline.py
│
├── vectorstore/
│   └── faiss_index/
│
├── frontend/
│   └── index.html
│
├── data/
│   └── ncert_pdfs/
│
└── README.md
```
## ▶️ Running Locally:

- Install dependencies - pip install fastapi uvicorn torch transformers langchain faiss-cpu
- Start backend - uvicorn backend.main:app --reload
- Open frontend - Open frontend/index.html in browser.

## 🔐 Zero Hallucination Policy:

If answer is not found in NCERT:
"This question is outside the NCERT curriculum."

No external knowledge is ever used.

## 🎓 Academic Context:

Focus Areas: 
- Retrieval-Augmented Generation
- Multilingual NLP
- Educational AI
- Explainable AI
- CPU-Optimized Inference
