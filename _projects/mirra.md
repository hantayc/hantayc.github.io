---
title: MIRRA — Resume & Role Alignment
subtitle: FAISS + SentenceTransformers pipeline to match resumes to job descriptions with fast similarity search.
date: 2025-05-01
tags: [NLP, GenAI, RAG, FAISS]
links:
  - label: GitHub
    url: https://github.com/<yourhandle>/<repo>
  - label: Live Demo
    url: https://<demo-link>
---

## Problem
Hiring teams and candidates struggle to quickly identify strong matches between resumes and roles.

## Solution
Built a skill-matching and ranking system using embeddings + ANN retrieval.

## What I built
- Embedding pipeline with SentenceTransformers
- FAISS index for fast retrieval
- Scoring + reranking logic
- Evaluation against labeled examples

## Results
- Reduced search time from minutes to milliseconds per query (FAISS ANN)
- Improved match quality via reranking and thresholding

## Next improvements
- Add feedback loop + active learning
- Add per-skill explainability