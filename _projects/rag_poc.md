---
title: Designing and Evaluating a Retrieval-Augmented (RAG) System
subtitle: Architecting a production-style GenAI retrieval pipeline with evaluation frameworks
date: 2024-12-07
tags: [GenAI, Retrieval-Augmented Generation, LLM Systems, Vector Search, Applied ML, Evaluation]
thumbnail: /assets/images/projects/rag_poc.png
---

[📄 Technical Report](/assets/files/rag_poc.pdf){: .btn .btn--primary }
[💻 Source Code](https://github.com/hantayc/rag-poc){: .btn .btn--info }

---

## What I Built

I **designed and implemented a Retrieval-Augmented Generation (RAG) system** that combines vector-based document retrieval with large language models to generate grounded, up-to-date answers to Generative AI questions.

The system mirrors how RAG is used in **real-world knowledge assistants**, emphasizing retrieval quality, system tradeoffs, and reliable evaluation—not just prompt engineering.

---

## Why It Matters

Standalone LLMs struggle with hallucinations and stale knowledge.  
This project shows how a **RAG architecture** can:
- Ground responses in relevant source documents
- Improve factual reliability without retraining models
- Support different user audiences (technical and non-technical)

---

## System Design

**End-to-end RAG pipeline:**
- Document ingestion with configurable chunking strategies
- Sentence-embedding vector search for retrieval
- Context injection into LLM prompts
- Deterministic generation for consistent evaluation

I treated chunking, retrieval thresholds, and decoding settings as **first-class system design choices**, not defaults.

---

## What I Evaluated

- How chunk size and overlap affect answer quality
- When high similarity scores fail to produce useful context
- Stability of LLM-based evaluation under deterministic vs. sampled decoding

**Key insight:**  
High retrieval similarity does not guarantee better answers—effective RAG systems require balancing relevance, context depth, and noise.

---

## Skills Demonstrated

- Designing **end-to-end GenAI systems**
- Vector search & embedding-based retrieval
- Evaluating ML systems beyond surface metrics
- Translating research techniques into **production-oriented patterns**

---

## Tech Stack

Python · LangChain · Sentence Transformers · Vector Search · LLMs