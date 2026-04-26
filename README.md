# AI-Medical-Assistant-Chatbot-RAG-based-Application
This application is a Medical Domain Chatbot built using Retrieval-Augmented Generation (RAG). It allows users to upload their own medical documents (e.g., textbooks, reports), and the system intelligently answers queries by retrieving the most relevant content before generating a final response.

## 🧠 Project Overview

This application is a **Medical Domain Chatbot** built using **Retrieval-Augmented Generation (RAG)**.  
It allows users to upload their own medical documents (e.g., textbooks, reports), and the system intelligently answers queries by retrieving the most relevant content before generating a final response.

---

## 🎓 What is RAG?

**RAG (Retrieval-Augmented Generation)** enhances language models by supplying relevant external context from a knowledge base, preventing hallucinations and improving accuracy—especially for factual or specialized domains like **medicine**.

---

## 🔄 Architecture

```text
User Input
   ↓
Query Embedding → Pinecone Vector DB ← Embedded Chunks ← Chunking ← PDF Loader
   ↓
Retrieved Docs
   ↓
RAG Chain (Groq + LangChain)
   ↓
LLM-generated Answer.

📄 For a detailed view, refer to assets/MedicalAssistant.pdf



---

## 🚀 Features

- 📄 Upload medical PDFs (notes, books, reports)
- ✂️ Automatic text extraction & semantic chunking
- 🧠 Embeddings using **Google / BGE models**
- 🗄️ Vector storage with **Pinecone**
- ⚡ Ultra-fast responses via **Groq LLaMA3-70B**
- 🔗 LangChain-powered RAG pipeline
- 🌐 FastAPI backend for scalable APIs
- 💬 Streamlit UI for interaction

---

## 🧰 Tech Stack

<p align="center">

![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green?style=for-the-badge&logo=fastapi)
![LangChain](https://img.shields.io/badge/LangChain-RAG-orange?style=for-the-badge)
![Pinecone](https://img.shields.io/badge/Pinecone-VectorDB-purple?style=for-the-badge)
![Groq](https://img.shields.io/badge/Groq-LLM-black?style=for-the-badge)
![Streamlit](https://img.shields.io/badge/Streamlit-Frontend-red?style=for-the-badge&logo=streamlit)

</p>

| Component   | Tech Used |
|------------|----------|
| LLM        | Groq API (LLaMA3-70B) |
| Embeddings | Google Generative AI / BGE |
| Vector DB  | Pinecone |
| Framework  | LangChain |
| Backend    | FastAPI |
| Deployment | Render |

---

## 📡 API Endpoints

### 🔹 Upload PDFs
```http
POST /upload_pdfs/


