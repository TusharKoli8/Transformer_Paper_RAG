# Transformer Paper RAG

A local Retrieval Augmented Generation (RAG) system that lets you ask questions about the famous research paper **"Attention Is All You Need"** using **Groq LLM**, **FAISS**, and **Sentence Transformers**.


##  Overview

This project builds an intelligent questio answering system over the Transformer paper.

Instead of sending the full PDF directly to an LLM, the system:

- Extracts text from the PDF
- Splits it into smaller chunks
- Converts each chunk into vector embeddings
- Stores embeddings in a local FAISS vector database
- Retrieves the most relevant chunks based on user queries
- Sends retrieved context + question to Groq LLM for accurate answers

This improves answer quality, reduces token usage, and keeps responses grounded in the source document.


##  Features

- PDF-based question answering
- Local vector search using FAISS
- Semantic embeddings using Sentence Transformers
- Fast inference with Groq LLM
- CLI-based interactive chat system
- Persistent vector storage


##  Tech Stack

- Python
- Groq API
- FAISS
- Sentence Transformers
- PyPDF
- NumPy
- Pickle


##  Project Structure

transformer-paper-rag/
├── data/
│   └── attention_is_all_you_need.pdf
├── store/
│   ├── faiss_index
│   └── chunks
├── __init__.py
├── ingest.py
├── retriever.py
├── rag_chain.py
├── agents.py
├── main.py
└── README.md


Install dependencies:

---bash
pip install -r requirements.txt


Create a `.env` file:

---env
GROQ_API_KEY=your_api_key_here


##  Usage

### Step 1: Ingest the PDF

---bash
python app\ingest.py

This will:

- Read the PDF
- Create text chunks
- Generate embeddings
- Store vectors in FAISS

### Step 2: Start Chat

---bash
python app\main.py

Now ask questions like:

- What is self attention?
- Why do transformers remove recurrence?
- What is positional encoding?


##  Use Cases

- Research paper understanding
- Academic learning
- Local document Q&A
- RAG pipeline learning
