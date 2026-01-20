# MoSPI RAG Chatbot – Data AI/ML Assignment

## Overview
This notebook implements a lightweight Retrieval-Augmented Generation (RAG) system
using a structured MoSPI-style dataset. The pipeline covers data ingestion, validation,
text chunking, vector embedding using SentenceTransformers, FAISS-based retrieval,
and dataset-grounded question answering.

The entire system runs end-to-end inside a single Google Colab notebook for ease
of evaluation and reproducibility.

---

## Features
- Structured dataset ingestion (CSV-based)
- ETL pipeline including data cleaning, validation, and text chunking
- Document-to-chunk lineage for traceability
- Semantic embeddings using SentenceTransformers
- FAISS vector database for efficient similarity-based retrieval
- RAG-based chatbot with strict dataset grounding and source awareness
- Explicit handling of unanswerable questions to prevent hallucinations

---

## Setup Instructions
1. Open this notebook in Google Colab.
2. Run all cells from top to bottom.
3. Required libraries are installed directly in the notebook using `pip`.

---

## Run Instructions
- Load the dataset from CSV.
- Perform ETL (validation and chunking).
- Generate embeddings and build FAISS index.
- Query the system using the `ask_question()` function.

Example:
```python
answer, sources = ask_question("What does the CPI report say about inflation?")
```
## Author

Divya Bajla
