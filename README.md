
RAG AI Document Retrieval System

Production-grade Retrieval-Augmented Generation (RAG) system designed for enterprise knowledge management and document-grounded question answering.

The system transforms heterogeneous technical documentation (PDFs, images, tables, manuals) into a semantic knowledge layer using OCR, layout detection, embeddings, and hybrid retrieval.
A locally deployed LLM then generates context-grounded answers with minimal hallucination, enabling reliable knowledge access across large document repositories.



Architecture Overview

Document Sources
     │
     ▼
OCR & Layout Detection
(PaddleOCR + Unstructured)
     │
     ▼
Semantic Chunking + Metadata Extraction
     │
     ▼
Embedding Generation
(nomic-embed-text, 768D)
     │
     ▼
Vector Storage
(ChromaDB)
     │
     ▼
Hybrid Retrieval
(Vector Search + BM25)
     │
     ▼
Multi-Stage Reranking
(MMR + Cross-Encoder)
     │
     ▼
LLM Generation
(Mistral / Phi-3 via Ollama)
     │
     ▼
Grounded Response




Key Capabilities
	•	Enterprise Document Ingestion
	•	OCR processing for scanned PDFs and images
	•	Layout-aware extraction of tables, headings, and sections
	•	Semantic Knowledge Indexing
	•	Intelligent chunking with metadata enrichment
	•	High-dimensional embeddings for contextual retrieval
	•	Hybrid Search Engine
	•	Vector similarity search + BM25 keyword matching
	•	Metadata-aware filtering and fuzzy product matching
	•	Relevance Optimization
	•	Multi-stage reranking pipeline
	•	Maximal Marginal Relevance (MMR) for diversity
	•	Grounded AI Responses
	•	Local LLM inference via Ollama
	•	Strict context-only prompt design to minimize hallucinations



Tech Stack

AI / NLP
	•	Ollama
	•	Mistral / Phi-3
	•	nomic-embed-text (768D)

Document Processing
	•	PaddleOCR
	•	Unstructured.io

Search & Retrieval
	•	ChromaDB
	•	BM25
	•	RapidFuzz

Backend
	•	Python
	•	FastAPI

Infrastructure
	•	Docker
	•	Local LLM deployment



Repository Structure

docs_raw/                Raw enterprise documents
docs_processed/          OCR + parsed outputs

rag_ingest.py            Document ingestion pipeline
rag.py                   Retrieval + reranking logic
rag_pipeline.py          End-to-end RAG workflow

ocr_service.py           OCR microservice
layout_detector_service.py Layout detection service

semantic_chunker.py      Chunking + metadata processing
main.py                  FastAPI application
auth.py                  Authentication layer




Contributors

Tanay Singh
AI / Backend Development
https://github.com/tanaysingh0312

Jahnavi Dave
Research / Backend Development
https://github.com/jahnavikdave1834



License

Apache License 2.0

