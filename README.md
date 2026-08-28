# RAG Pipeline Notebook

A learning project and practical Jupyter notebook demonstrating a Retrieval-Augmented Generation (RAG) pipeline for PDF documents.

## What it covers

- Loading PDF documents with LangChain
- Splitting documents into overlapping chunks
- Creating embeddings with `all-MiniLM-L6-v2`
- Storing embeddings in a local Chroma vector store
- Retrieving relevant chunks using semantic similarity
- Generating answers with Groq or OpenAI chat models

## Project Structure

```
RAG/
├── RAG_pipeline.ipynb
├── data/
│   ├── pdfs/           # Input PDFs
│   ├── Python.txt      # Text-loader example
│   └── vector_store/   # Generated Chroma data
└── README.md
```

## Setup

Create and activate a Python 3.10+ environment, then install the dependencies:

```
pip install langchain langchain-core langchain-community langchain-text-splitters \
pypdf pymupdf sentence-transformers chromadb scikit-learn \
langchain-groq langchain-openai python-dotenv
```

Open `RAG_pipeline.ipynb` in VS Code or Jupyter and run the cells from top to bottom.

Add your PDF documents to `data/pdfs/` before running the ingestion section.

## API Keys

The notebook reads API keys from a local `.env` file.

Create a `.env` file in the project directory:

```
GROQ_API_KEY=your-groq-key
OPENAI_API_KEY=your-openai-key
```

You only need to provide the key for the model provider you intend to use.

**Never commit API keys or `.env` files to GitHub.**

## Notes

- `data/vector_store/` is generated locally and is ignored by Git. It can be rebuilt by running the ingestion cells.
- Only commit PDF files that you have permission to redistribute.
- This is a **learning project** intended to demonstrate the fundamentals of building a RAG pipeline. It is not a production-ready RAG application.

## Repository

**Repository name:** `rag-pipeline-notebook`

**Description:** Educational LangChain RAG pipeline with PDF ingestion, sentence-transformer embeddings, Chroma retrieval, and Groq/OpenAI generation.
