---
title: MIRRA — Resume & Role Alignment
subtitle: FAISS + SentenceTransformers pipeline for fast resume-to-role matching.
date: 2025-05-01
tags: [NLP, GenAI, RAG, FAISS]
thumnail: /assets/images/projects/mirra.png

# header:
#   image: /assets/images/projects/mirra-banner.png
#   caption: "Semantic matching with embeddings + ANN search"

links:
  - label: GitHub
    url: https://github.com/hantayc/mirra
  - label: Live Demo
    url: https://<demo-link>
---

## Problem
Matching resumes to job descriptions is noisy and time-consuming. Keyword search breaks down quickly, and even strong candidates can be missed if terminology doesn’t line up cleanly.

## Solution
I built an embedding-based matching system that represents both resumes and job descriptions in a shared vector space, enabling fast semantic similarity search and ranking.

## What I built
- End-to-end embedding pipeline using SentenceTransformers
- FAISS index for approximate nearest neighbor retrieval at scale
- Scoring, filtering, and reranking logic to improve match quality
- Lightweight evaluation using labeled resume–job pairs

## Tech Stack
SentenceTransformers · FAISS · Python · LangChain · Vector Similarity Search

## Results
- Reduced search latency from minutes to milliseconds per query using FAISS ANN
- Improved relevance of top-ranked matches through reranking and thresholding
- System generalizes across roles without hand-crafted keyword rules

## Next improvements
- Incorporate user feedback for active learning and continual improvement
- Add per-skill explainability to make match scores more transparent