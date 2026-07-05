# 🚀 Production-Grade Hybrid RAG System (FAISS + BM25 + Cross-Encoder)

## 📌 Project Overview

This project implements an **Enterprise-Grade Retrieval-Augmented Generation (RAG) system** designed for high-precision document understanding and question answering.

The system combines:
- 🔍 **Dense Vector Search (FAISS)**
- 🔑 **Keyword Search (BM25)**
- 🧠 **Neural Re-ranking (Cross-Encoder)**
- 🤖 **LLM Generation (Gemini API)**

This hybrid architecture significantly improves retrieval accuracy and reduces hallucinations.

---

## ⚙️ Key Features

### 🔹 Hybrid Retrieval System
- Combines semantic search (FAISS) and lexical search (BM25)
- Ensures both meaning-based and keyword-based retrieval

### 🔹 Cross-Encoder Re-ranking
- Uses `ms-marco-MiniLM-L-6-v2`
- Re-ranks retrieved chunks for highest relevance

### 🔹 Document Processing Pipeline
- PDF ingestion using PyPDFLoader
- Recursive text chunking with overlap control

### 🔹 Persistent Indexing
- FAISS index saved to disk
- BM25 + chunks serialized using pickle
- Fast reload without reprocessing documents

### 🔹 Hallucination Control
- Strict prompt enforcement:
  > "Use ONLY the context. If not found, return NOT FOUND IN DOCUMENT"

### 🔹 Metrics & Telemetry
- Query latency tracking
- Retrieval overlap scoring
- System performance reporting

---

## 🧠 Architecture Flow
PDF Document
↓
Text Loader (PyPDFLoader)
↓
Chunking (RecursiveCharacterTextSplitter)
↓
────────────────────────────
│ Hybrid Indexing Layer │
│ - FAISS (Vector DB) │
│ - BM25 (Keyword Search) │
────────────────────────────
↓
Candidate Retrieval
↓
Cross-Encoder Re-ranking
↓
Top-K Context Selection
↓
LLM (Gemini 2.5 Flash)
↓
Final Answer

---

## 📦 Tech Stack

- Python 🐍
- LangChain 🦜
- FAISS (Facebook AI Similarity Search)
- BM25 (Rank-BM25)
- Sentence Transformers
- Cross-Encoder (`ms-marco-MiniLM-L-6-v2`)
- Google Gemini API
- NumPy, Pickle, Logging

---

## 📁 Project Structure
week 7/
│
├── notebook.ipynb
├── Comprehensive Study on Artificial Intelligence.pdf
├── requirements.txt
├── .gitignore
│
├── my_secure_rag_index/
│ ├── faiss index
│ ├── bm25.pkl
│ └── chunks.pkl
│
└── README.md

---

## 🚀 How to Run

### 1️⃣ Install dependencies
```bash
pip install -r requirements.txt

2️⃣ Set environment variables
Create a .env file:
GEMINI_API_KEY=your_api_key_here

