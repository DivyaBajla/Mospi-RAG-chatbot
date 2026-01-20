# Submission Notes

## What Worked

- Successfully implemented an end-to-end Retrieval-Augmented Generation (RAG) pipeline using a structured, MoSPI-style dataset.
- Designed a clean ETL workflow including data loading, validation, text chunking with overlap, and document-to-chunk lineage tracking.
- Generated dense vector embeddings using SentenceTransformers and built an efficient similarity search index using FAISS.
- Implemented a retrieval-aware question answering function where responses are strictly grounded in retrieved document context.
- Added explicit handling for unanswerable questions, ensuring the system refuses to answer when relevant information is not present in the dataset.
- The entire pipeline executes reproducibly within a single Google Collab Notebook, making it easy to run and evaluate without additional infrastructure.

## What Didn’t Work / Limitations

- Live web scraping from the MoSPI website was not enabled due to access restrictions and dynamic rendering issues encountered in cloud notebook environments.
- The chatbot interaction is limited to function calls within the notebook; no external API or web-based UI was implemented.
- The dataset size is intentionally limited and manually curated for demonstration purposes, which may restrict answer coverage.
- A local LLaMA model (via Ollama) and Docker-based deployment were not integrated in this version to keep the setup lightweight and Colab-compatible.

## What I Would Do Next

- Enable incremental and resilient web scraping from the MoSPI website with proper rate limiting, retries, and content fingerprinting.
- Integrate LLaMA 3 Instruct using Ollama or llama.cpp for local, instruction-tuned generation.
- Expose the RAG system through a FastAPI service with clearly defined `/ask`, `/ingest`, and `/health` endpoints.
- Build a simple web-based UI (e.g., Streamlit) to allow interactive querying and source inspection.
- Dockerize the complete pipeline (scraper, ETL, vector store, API, and UI) to ensure portability and production-ready deployment.

