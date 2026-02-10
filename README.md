
# 📄 Retrieval-Augmented Question Answering (RAG) System

## Overview

This project implements a basic **Retrieval-Augmented Generation (RAG)** system to answer questions from custom documents.
The system retrieves relevant document chunks using vector similarity search and then answers queries using a question-answering model grounded in the retrieved context.

The goal is to reduce hallucinations by ensuring answers are derived only from relevant source content.

---

## Approach

1. **Document Processing**

   * Loaded a custom text document
   * Split the document into smaller chunks for efficient retrieval

2. **Embedding & Retrieval**

   * Generated sentence embeddings using a lightweight transformer model
   * Stored embeddings in a FAISS vector index
   * Retrieved top-K relevant chunks based on semantic similarity

3. **Question Answering**

   * Passed retrieved context to an extractive QA model
   * Returned answers strictly from retrieved content

4. **Hallucination Control**

   * Applied a retrieval distance threshold to filter weak matches
   * Used model confidence scores to handle unanswerable questions safely

---

## Technologies Used

* Python
* SentenceTransformers (for embeddings)
* FAISS (vector similarity search)
* Hugging Face Transformers (question-answering pipeline)
* Jupyter Notebook

---

## Key Features

* Semantic document retrieval using vector search
* Context-grounded question answering
* Confidence-based handling of unknown queries
* Lightweight and reproducible notebook-based implementation

---

## Example Behavior

**Question:** What is the WFH policy?
**Answer:** All employees are eligible for a hybrid WFH schedule.

**Question:** What is the dental policy?
**Answer:** I don't have that information.

---

## Notes

* This project is a prototype intended to demonstrate RAG concepts.
* The QA model is extractive and selects answers only from retrieved document context.
* The system avoids hallucinations by combining retrieval relevance checks with answer confidence thresholds.

---

## Key Learnings

* How retrieval improves reliability of language model outputs
* Practical challenges of semantic search and QA models
* Importance of confidence and relevance checks in real-world RAG systems

