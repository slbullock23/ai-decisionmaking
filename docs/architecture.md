3. The Architecture (architecture.md)
Think of this as: the “How the pieces talk” explanation
System Overview
	•	Next.js: where users submit decisions, communicated with backend API
	•	FastAPI: validates inputs, stores data, computes scores, calls Ollama directly
	•	PostgreSQL: stores users, decisions, confidence, and outcomes
	•	Ollama: analyzes disagreement, redundancy, and risk signals
Data Flow
	•	User submits a decision and confidence
	•	Server records the input
	•	AI checks for:
	◦	Conflicting opinions
	◦	Overconfidence
	◦	Missing common signals (contextual information)
	•	Feedback is returned to the user
	•	Outcome is later logged and used for scoring

ADRs
	•	 
	◦	We are using Ollama as our Local AI for this software.
	◦	We need to have an AI capable of analyzing user provided information and returning insight, recommendations of decisions.
	◦	We will use Ollama as the local AI runtime responsible for loading, managing, and running LLM models. The application’s backend (API layer) will connect to Ollama to submit prompts and receive responses.
	◦	Consequences
	▪	Pros

Local & offline inference — No dependency on external cloud AI services.
Data privacy — User information never leaves the machine or private network.
Cost-effective — No per-token or monthly AI API costs.
Fast experimentation — Easy to switch between models using ollama pull <model>.
Unified runtime — Standardized API for multiple models.
Performance control — Ability to optimize models (quantization) for local hardware.
	•	Cons
Hardware dependent — Performance varies heavily based on CPU/GPU available.
Operational overhead — Need to maintain the runtime, model versions, and updates.
Limited model size — Very large models may not run well locally.
Scaling challenges — Harder to support many simultaneous AI requests.Lack of some cloud features — No built-in vector search, monitoring tools, or guardrails unless we add them ourselves.


	•	 
	◦	 We are using FastAPI as our backend API layer
	◦	The project requires a backend service to handle incoming UI requests, process business logic, interact with the AI layer (Ollama), and communicate with the database.
	◦	We will use FastAPI as the backend framework for building our API endpoints.
The backend service will expose REST endpoints that the UI uses, orchestrate calls to Ollama (local AI), apply business logic, and interact with the database.
	•	 Consequences
	◦	Pros
High performance — Based on Starlette and Pydantic, comparable to Node/Go for many workloads.Automatic validation & typing — Uses Python type hints for data validation without extra boilerplate.Async-first design — Works well with async DB drivers, AI inference calls, and concurrent tasks.Excellent developer experience — Built-in interactive docs via Swagger and ReDoc.Large ecosystem — Many libraries and community support.Easy integration with Python AI tools — Smooth compatibility with Ollama client libs, open-source AI models, and data processing pipelines.
	•	Pros
Python runtime performance limitations — Not as fast as Go/Node in raw concurrency-heavy workloads.
Requires familiarity with async Python — Mistakes in async usage can lead to performance bottlenecks.
Scaling needs careful planning — Typically requires running behind Uvicorn + Gunicorn for production.
More opinionated frameworks exist — FastAPI gives flexibility but requires additional choices for structure, testing, and dependency management.