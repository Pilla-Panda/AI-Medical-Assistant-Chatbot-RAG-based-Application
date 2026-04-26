# AI-Medical-Assistant-Chatbot-RAG-based-Application
This application is a Medical Domain Chatbot built using Retrieval-Augmented Generation (RAG). It allows users to upload their own medical documents (e.g., textbooks, reports), and the system intelligently answers queries by retrieving the most relevant content before generating a final response.

## 📌 Project Overview

This project is a **Medical Domain Chatbot** built using **Retrieval-Augmented Generation (RAG)**.  
It enables users to upload medical documents (e.g., textbooks, reports) and intelligently answers queries by retrieving the most relevant context before generating accurate responses.

---

## 🎓 What is RAG?

**RAG (Retrieval-Augmented Generation)** enhances Large Language Models (LLMs) by incorporating external knowledge from a vector database.  
This approach:
- Reduces hallucinations  
- Improves factual accuracy  
- Performs well in domain-specific areas like **medicine**

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
LLM-generated Answer

----
````
##🚀 Features
📄 Upload medical PDFs (books, notes, reports)
✂️ Automatic text extraction & semantic chunking
🧠 Embedding generation using Google / BGE models
🗄️ Efficient vector storage with Pinecone
⚡ Fast inference via Groq LLaMA3-70B
🔗 End-to-end RAG pipeline using LangChain
🌐 FastAPI backend with REST APIs
💬 Interactive UI using Streamlit

-----

| Component   | Tech Used |
|------------|----------|
| LLM        | Groq API (LLaMA3-70B) |
| Embeddings | Google Generative AI / BGE |
| Vector DB  | Pinecone |
| Framework  | LangChain |
| Backend    | FastAPI |
| Deployment | Render |


------

##📚 API Endpoints
POST /upload_pdfs/ --- Upload one or more PDF files

POST /ask/ --- Ask a question --- Form field: `question`

------

##📁 Folder Structure

```text
assets/
│── DIABETES.pdf
│── MedicalAssistant.pdf
│── medicalAssistant.png

client/
│── components/
│   ├── chatUI.py
│   ├── history_download.py
│   └── upload.py
│── utils/
│   └── api.py
│── app.py
│── config.py
│── requirements.txt

server/
│── middlewares/
│   └── exception_handlers.py
│── modules/
│   ├── llm.py
│   ├── load_vectorstore.py
│   ├── pdf_handlers.py
│   └── query_handlers.py
│── routes/
│   ├── ask_question.py
│   └── upload_pdfs.py
│── uploaded_docs/
│── main.py
│── logger.py
│── requirements.txt

````

##⚡ Quick Setup

````text
# Clone the repo
$ git clone https://github.com/snsupratim/medicalAssistant.git
$ cd medicalAssistant/server

# Create virtual env
$ uv venv
$ .venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
$ uv pip install -r requirements.txt

# Set environment variables (.env)
GOOGLE_API_KEY=...
GROQ_API_KEY=...
PINECONE_API_KEY=...

# Run the server
$ uvicorn main:app --reload --port 8000


$ cd medicalAssistant/client

# Create virtual env
$ uv venv
$ .venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
$ uv pip install -r requirements.txt

# Run the server
$ streamlit run app.py

````

##🌐 Deployment
Hosted on Render

Configure start command as:
```text
uvicorn main:app --host 0.0.0.0 --port 10000

````

##🌟 Credits
Built by Yash Kumar
Inspired by LangChain, Groq, Pinecone, and FastAPI ecosystems

##🎉 License
This project is licensed under the MIT License.
