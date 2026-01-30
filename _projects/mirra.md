---
title: MIRRA — Resume & Role Alignment
subtitle: AI-powered job matching system using semantic embeddings and structured feature extraction.
date: 2026-01-20
tags: [NLP, LLMs, Semantic Search, ML Systems]
thumbnail: /assets/images/projects/mirra.png
header:
  image: /assets/images/projects/mirra.png
  caption: "Intelligent resume-to-role matching powered by embeddings and logic-aware scoring"

links:
  - label: GitHub
    icon: "fab fa-github"
    url: "https://github.com/hantayc/mirra_matcher"
  - label: Berkeley iSchool Project
    icon: "fas fa-university"
    url: "https://www.ischool.berkeley.edu/projects/2025/mirra-matching-intelligence-resume-role-alignment"
  - label: Demo
    icon: "fas fa-play-circle"
    url: "https://www.youtube.com/watch?v=4Nf8LLRe0IM&embeds_referring_euri=https%3A%2F%2Fwww.ischool.berkeley.edu%2F&source_ve_path=MjM4NTE&themeRefresh=1"
---

[📂 View on GitHub](https://github.com/hantayc/mirra_matcher){: .btn .btn--primary} [🎓 Berkeley iSchool](https://www.ischool.berkeley.edu/projects/2025/mirra-matching-intelligence-resume-role-alignment){: .btn .btn--info} [▶️ Demo Video](https://www.youtube.com/watch?v=4Nf8LLRe0IM&embeds_referring_euri=https%3A%2F%2Fwww.ischool.berkeley.edu%2F&source_ve_path=MjM4NTE&themeRefresh=1){: .btn .btn--success}

## Problem & Motivation

Job search remains overwhelmingly inefficient. The average job seeker in the U.S. spends ~6 months searching, often sifting through thousands of irrelevant postings. Despite AI integration in platforms like LinkedIn and Indeed, most systems provide case-by-case assessments without offering a **quantifiable, consistent metric** that clearly indicates how well a candidate fits a role.

Current keyword-based and basic ranking systems fail to capture semantic alignment between resume skills and job requirements, leading to either massive false positives (irrelevant recommendations) or missed opportunities (strong candidates overlooked due to terminology mismatches).

## Our Approach

MIRRA addresses this by building an **intelligent, interpretable resume-to-job matching system** that:

1. **Extracts structured information** from unstructured resumes and job descriptions using LLM-powered feature extraction (GPT-4o teacher → fine-tuned LLaMA 3.1 student via QLoRA distillation)
2. **Encodes requirements semantically** using dense embeddings (multilingual-e5-large-instruct) while preserving logical structure (AND/OR conditions)
3. **Scores candidates across multiple dimensions**—skills, education, experience, credentials—using logic-aware matching that understands compositional language
4. **Provides interpretability** by surfacing both matched and unmet requirements

## Technical Architecture

### Feature Extraction
At the core is a **teacher-student distillation framework**:
- **Teacher**: GPT-4o generates labeled training data by extracting structured JSON from resumes and job descriptions across categories (hard_skills, education, credentials, professional_background, etc.)
- **Student**: Fine-tuned LLaMA 3.1 (QLoRA) learns to replicate GPT-4o's extraction at low latency and reduced cost

This preserves extraction quality while enabling scalable inference.

### Multidimensional Semantic Matching

The matching algorithm is **logic-aware and compositional**:

- **Skills**: If a job requires "Python AND interactive dashboards," the system understands this as a conjunction and scores accordingly. For "Python, Java, OR R," it takes the maximum similarity across alternatives.
- **Education**: Maps degrees to hierarchical levels (Bachelor's → Master's → PhD) and evaluates semantic fit between major and required field of study. If a job allows "Master's or equivalent experience," MIRRA infers domain relevance from work history and weights by years of experience.
- **Experience**: Sorts relevant skills by similarity and accumulates years until thresholds are met (e.g., 5+ years AWS).
- **Aggregation**: Safe averaging across dimensions ensures candidates aren't penalized for missing criteria the job description doesn't specify.

### Infrastructure
- **Streamlit** frontend for intuitive resume/job upload
- **AWS SageMaker** hosting the embedding model for scalable inference
- **Pinecone** vector database for efficient retrieval
- Custom matching logic orchestrating semantic similarity across all dimensions

## Evaluation & Results

We evaluated MIRRA against industry benchmarks using **LLM-as-a-judge** (OpenAI's O1 reasoning model) across 10 candidates and 10 job search scenarios:

- **vs. Dice.com**: **55% improvement** in relevance scores (MIRRA correctly ranks highly relevant roles higher)
- **vs. LinkedIn**: **17% improvement** in relevance scores

The evaluation criteria: Hard Skills, Professional Experience, Education, Credentials, and Job Fit (seniority alignment). A candidate must meet ≥70% of qualifications per category to score a point (max 5).

## Key Insights
1. **Overqualification filtering matters**: MIRRA excels at identifying qualified matches but can rank entry-level roles highly if the job description lacks explicit experience requirements. Solution: user-facing filters for salary and experience level.

2. **Domain-specific embeddings are critical**: General-purpose models struggle with nuanced job terminology. Future work involves fine-tuning embeddings on job market language and skill taxonomies.

3. **Extraction quality scales with prompt structure**: Our 3-prompt pipeline worked well; expanding to domain-specific prompts per criteria would improve label quality and extraction precision.

## Impact

MIRRA bridges the gap between **semantic relevance and interpretability** in job matching. By providing candidates with a quantifiable match score backed by explicit reasoning (which skills match, which don't, educational alignment path), it streamlines job search from overwhelming manual review to focused, informed decision-making.

This is especially impactful for job seekers in tech-adjacent roles where skills terminology varies widely and credential equivalencies are common.