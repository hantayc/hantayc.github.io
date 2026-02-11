---
title: Designing and Evaluating a Retrieval-Augmented (RAG) System
subtitle: Architecting a production-style GenAI retrieval pipeline with evaluation frameworks
date: 2024-12-07
tags: [GenAI, Retrieval-Augmented Generation, LLM Systems, Vector Search, Applied ML, Evaluation]
---

- 📄 **Technical Report:**  
  [Read the full evaluation and methodology (PDF)](/assets/files/rag_poc.pdf){: .btn .btn--primary}

- 💻 **Source Code:**  
  [View the RAG system implementation](https://github.com/hantayc/rag-poc)

---

## Overview 
I **designed, built, and evaluated a Retrieval-Augmented Generation (RAG) system** for answering Generative AI questions using an open-book architecture. The system combines **vector-based document retrieval** with **large language models (LLMs)** to generate grounded, up-to-date responses tailored to different user audiences.

Rather than treating RAG as a black box, this project focuses on **system design, retrieval quality, and evaluation rigor**—surfacing the tradeoffs that matter when deploying GenAI systems in real business and product environments.