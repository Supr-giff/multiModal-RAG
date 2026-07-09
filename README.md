# Multimodal RAG with LangChain, Ollama and ChromaDB

## Overview

This project demonstrates a production-style Multimodal Retrieval-Augmented Generation (RAG) pipeline using local models.

The pipeline can:

* Parse PDF documents
* Extract text, tables and images
* Create AI-enhanced summaries
* Generate embeddings
* Store embeddings in ChromaDB
* Retrieve relevant content
* Answer user questions using a local LLM

---

# Project Structure

```text
multimodal-rag/
│
├── data/
│   ├── attention-is-all-you-need.pdf
│   └── (other PDFs)
│
├── db/
│   └── chroma_db/
│
├── dbv2/
│   └── chroma_db/
│
├── json-files/
│   ├── chunks_export.json
│   └── rag_results.json
│
├── notebooks/
│   └── multimodal_rag.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

# Technologies Used

* Python
* LangChain
* Ollama
* ChromaDB
* Unstructured
* Tesseract OCR
* Poppler

---

# Installation

## 1. Clone the repository

```bash
git clone https://github.com/Supr-giff/multiModal-RAG.git
cd multimodal-rag
```

---

## 2. Create a virtual environment

Windows

```bash
python -m venv venv
```

Activate

```bash
venv\Scripts\activate
```

---

## 3. Install Python packages

```bash
pip install -r requirements.txt
```

---

# Install Ollama

Download and install Ollama.

After installation, pull the required models.

```bash
ollama pull llama3.2
ollama pull nomic-embed-text
```

Verify installation.

```bash
ollama list
```

---

# Install Tesseract OCR (Windows)

Tesseract is used to extract text from scanned PDFs and images.

1. Download the Windows installer.
2. Install Tesseract.
3. During installation, add it to the system PATH.

Verify:

```bash
tesseract --version
```

---

# Install Poppler (Windows)

Poppler is used to process PDF files.

1. Download the Windows build of Poppler.
2. Extract the files.
3. Add the Poppler **bin** directory to your system PATH.

Verify:

```bash
pdftotext -v
```

---

# Folder Setup

Create these folders before running the project.

```text
data/
db/
json-files/
```

Place your PDF documents inside:

```text
data/
```

---

# Running the Pipeline

The pipeline performs the following steps.

1. Partition PDF
2. Extract text
3. Extract tables
4. Extract images
5. Create semantic chunks
6. Generate AI summaries
7. Create embeddings
8. Store vectors in ChromaDB

---

# Query Workflow

The retrieval workflow is:

```text
User Question
      │
      ▼
Retriever
      │
      ▼
Relevant Chunks
      │
      ▼
Ollama LLM
      │
      ▼
Final Answer
```

---

# Requirements

Install all Python dependencies using:

```bash
pip install -r requirements.txt
```

---

# Notes

* This project runs completely locally.
* No OpenAI API key is required.
* ChromaDB stores embeddings locally.
* Ollama performs embedding generation and answer generation.

---

# Future Improvements

* Image captioning
* OCR improvements
* Hybrid search
* Metadata filtering
* Reranking
* Support for Word, PowerPoint and Excel documents
* Web document ingestion
