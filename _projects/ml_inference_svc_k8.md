--- 
title: FastAPI ML Inference Service on Kubernetes 
subtitle: Deployed a FastAPI-based ML Service with Redis Caching, load testing, and observability
date: 2025-12-05
tags: [Machine Learning, MLOps, FastAPI, Kubernetes, Grafana, Redis, System Design, Azure, Poetry, Docker]
thumbnail: /assets/images/projects/255.png

--- 
[💻 Source Code](https://github.com/hantayc/lab-4-production-kubernetes-hantayc){: .btn .btn--info }

--- 
## What I Built

- A **FastAPI ML inference service** loading a serialized model at startup  
- **Single and bulk prediction endpoints** for scalable inference  
- **Redis caching layer** to reduce repeated model computation  
- **Dockerized deployment** with Kubernetes manifests  
- **Prometheus + Grafana dashboards** for system monitoring  
- **Load testing** to validate latency, CPU, and memory behavior  

This mirrors how ML models are deployed in real production environments.

---

## API Endpoints

- `GET /lab/health` — health check with server timestamp  
- `GET /lab/hello` — connectivity test endpoint  
- `POST /lab/predict` — single-row housing price prediction  
- `POST /lab/bulk-predict` — batch predictions for higher throughput  
- `/lab/docs` — auto-generated OpenAPI / Swagger documentation  

All requests are schema-validated to ensure safe inference.

---

## System Architecture

- **FastAPI** for async request handling  
- **Serialized ML pipeline** loaded once per container  
- **Redis** for inference caching  
- **Kubernetes Deployments & Services** for API and Redis  
- **Namespace isolation** for clean environments  
- **AKS-compatible configuration** for cloud deployment  

---

## Performance & Observability

I instrumented the service with **Prometheus and Grafana** to analyze real system behavior under load:

- Request latency percentiles (P50–P99)  
- CPU utilization during traffic spikes  
- Memory allocation and garbage collection patterns  
- Throughput and request injection behavior  

Load testing confirmed:
- Stable latency under concurrent traffic  
- Predictable CPU and memory usage  
- Cache effectiveness in reducing compute overhead  

---

## Skills Demonstrated

- ML model deployment & inference serving  
- API design for data science systems  
- Docker & Kubernetes (local + AKS)  
- Caching strategies for ML workloads  
- Load testing and performance analysis  
- Production monitoring & observability  

---

## Tech Stack

Python · FastAPI · Docker · Kubernetes · Redis · Prometheus · Grafana · Poetry · PyTest


