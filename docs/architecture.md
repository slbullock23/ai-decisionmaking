# 🏗️ Architecture
*How the pieces talk to each other*

This document explains how the frontend, backend, database, and AI layer work together to support collaborative decision-making.

---

## 1. System Overview

The system is composed of four main parts:

- **Next.js (Frontend)**
  - User-facing interface
  - Where users submit decisions and confidence levels
  - Communicates with the backend via REST APIs

- **FastAPI (Backend API)**
  - Validates user input
  - Stores and retrieves data
  - Computes decision scores
  - Communicates directly with the AI layer (Ollama)

- **PostgreSQL (Database)**
  - Stores users, decisions, confidence scores, feedback, and final outcomes
  - Serves as the source of truth for historical performance tracking

- **Ollama (Local AI Runtime)**
  - Analyzes group input
  - Detects disagreement, redundancy, and risk signals
  - Returns structured feedback and insights to the backend

---

## 2. Data Flow

1. A user submits a decision along with a confidence score from the frontend  
2. The backend validates and records the input in the database  
3. The backend sends the aggregated data to the AI layer  
4. The AI analyzes the inputs for:
   - Conflicting opinions
   - Overconfidence or imbalance
   - Missing or overlooked context  
5. Feedback is returned to the backend and sent to the user  
6. Once the real-world outcome is known, it is logged and used to update scoring and accuracy metrics  

---

## 3. Architectural Decision Records (ADRs)

### ADR 1: Use Ollama as the Local AI Runtime

**Decision**  
We use Ollama to run large language models locally for analysis and feedback generation.

**Rationale**
- The application requires AI to analyze user-provided decisions and generate insights
- Ollama provides a simple, local runtime for loading and switching between models
- The backend communicates directly with Ollama via its API

**Consequences**

**Pros**
- Local and offline inference (no cloud dependency)
- Strong data privacy (user data never leaves the machine or private network)
- Cost-effective (no per-token or subscription fees)
- Fast experimentation with different models
- Unified runtime with a consistent API
- Full control over performance and optimization

**Cons**
- Performance depends on available CPU/GPU
- Requires maintaining models and runtime updates
- Limited support for very large models
- Harder to scale for many concurrent users
- No built-in cloud features (monitoring, vector search, guardrails)

---

### ADR 2: Use FastAPI as the Backend Framework

**Decision**  
We use FastAPI as the backend API layer.

**Rationale**
- The system needs a backend to handle UI requests, business logic, AI orchestration, and database access
- FastAPI provides a clean, high-performance framework with strong typing and validation
- It integrates smoothly with Python-based AI tooling

**Consequences**

**Pros**
- High performance for most workloads
- Automatic request validation using type hints
- Async-first design for handling concurrent requests
- Built-in interactive API documentation
- Large ecosystem and community support
- Excellent compatibility with AI and data-processing libraries

**Cons**
- Python is slower than some alternatives in heavy concurrency scenarios
- Requires careful async programming to avoid bottlenecks
- Production scaling needs additional setup (e.g., Uvicorn + Gunicorn)
- Flexible but less opinionated, requiring more architectural decisions
