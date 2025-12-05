🏥 Clinical RAG System with MIMIC-IV Dataset
Overview

This project implements a Retrieval-Augmented Generation (RAG) system that answers clinical queries using the MIMIC-IV-Ext Direct dataset.

The system combines:

Hybrid Retrieval: BM25 + Dense embeddings with FAISS indexing for efficient and relevant document retrieval.

Generative Model: FLAN-T5 generates context-aware answers based on retrieved documents.

Interactive Streamlit Frontend: Users can input queries, adjust retrieval parameters, and view answers and document relevance.

This setup demonstrates how RAG can bridge structured clinical datasets and natural language understanding.

Features

Hybrid Retriever

BM25 (sparse) + SentenceTransformer embeddings (dense)

FAISS index for fast similarity search

Tunable weighting between BM25 and dense scores

Generative Model

FLAN-T5 (google/flan-t5-base) for answer generation

Prompt includes top retrieved documents

Handles long context using chunking and truncation

Streamlit Frontend

Upload ZIP dataset

Enter clinical queries

Adjust top-K documents and hybrid weight

Display generated answers and document scores

Evaluation & Ethics

Simulated precision@K and recall@K metrics

Ethical checklist: anonymization, HIPAA/GDPR compliance

Installation

Clone the repository

git clone https://github.com/yourusername/clinical-rag-system.git
cd clinical-rag-system


Install dependencies

pip install -r requirements.txt


Example requirements.txt:

streamlit
sentence-transformers
transformers
torch
faiss-cpu
rank_bm25
numpy


Place the ZIP dataset (e.g., mimic-iv-ext-direct-1.0.0.zip) in the project folder.

Usage

Run the Streamlit app:

streamlit run app.py


In the app:

Enter the path to your ZIP dataset

Load the dataset → initializes retriever and FLAN-T5 model

Enter a clinical query

Adjust Top-K Documents and Hybrid Weight (alpha)

Click Search to get generated answers and relevant documents
