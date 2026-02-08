# 🧠✨ Collaborative Decision Intelligence

> **Make better decisions together — and prove it.**

This project is a collaborative decision-making app that helps groups move beyond loud opinions and gut feelings. Instead of just capturing *what* people think, it measures **confidence, accuracy, and decision quality over time**.

Think of it as a structured group chat for decisions, powered by data and AI.

---

## 🚩 The Problem

Groups make decisions constantly: friends, teams, clubs, and student organizations.  
But those decisions usually suffer from the same issues:

- The loudest voice wins  
- Confidence is not measured  
- There is no record of who was actually right  
- No way to know if the group outperformed an individual  

Existing tools (group chats, polls, spreadsheets) capture opinions, **not decision quality**.

---

## 🎯 The Solution

A collaborative decision-making platform where users:

- Submit decisions **with confidence scores**
- Receive structured AI feedback
- Track outcomes and accuracy over time
- See when groups outperform individuals

The goal is not to replace human judgment, but to **improve it with feedback, accountability, and insight**.

---

## 👥 Target Users

Small, focused groups (5–20 people) making repeat decisions:

- Students working on projects  
- Friends debating sports outcomes  
- Clubs deciding budgets or events  
- Beginner finance or banking clubs practicing risk assessment  

> Sports, banking, and similar domains are **test environments**, not the end goal.  
> They provide fast, measurable feedback for validating group decision intelligence.

---

## ✨ Core Features

- Create or join decision groups  
- Submit decisions with confidence scores  
- AI-powered feedback on disagreement and overconfidence  
- Leaderboards tracking individual and group accuracy  
- Historical views of past decisions and outcomes  
- Offline-friendly decision logging (AI enhances, never blocks)

---

## 🏗️ Architecture Overview

The system is composed of four main components:

- **Next.js (Frontend)**  
  User interface for submitting decisions and viewing feedback  

- **FastAPI (Backend)**  
  Handles validation, business logic, AI orchestration, and data access  

- **PostgreSQL (Database)**  
  Stores users, decisions, confidence scores, and outcomes  

- **Ollama (Local AI Runtime)**  
  Analyzes group inputs and returns explainable insights  

### High-Level Data Flow

1. User submits a decision and confidence  
2. Backend validates and stores the input  
3. AI analyzes group patterns (conflict, overconfidence, missing context)  
4. Feedback is returned to the user  
5. Outcomes are later logged and used for scoring  

---

## 🤖 AI Philosophy

- AI is an **advisor**, not a decision-maker  
- The app works **without AI** if necessary  
- AI feedback is always **explainable in plain language**  
- Decisions are never blocked due to AI availability  

---

## 📋 Requirements Snapshot

### Functional
- Group creation and management  
- Decision and confidence submission  
- Outcome tracking  
- Leaderboards and history views  

### Non-Functional
- Fast feedback (under 1 second)  
- Fair scoring (no edits after submission)  
- Simple UX (structured like a group chat)  

---

## 🧩 Tech Stack

- **Frontend:** Next.js  
- **Backend:** FastAPI (Python)  
- **Database:** PostgreSQL  
- **AI Runtime:** Ollama (local LLM inference)  

### Why This Stack?

- Python excels at data analysis and AI integration  
- FastAPI offers speed, validation, and clean APIs  
- Local AI ensures privacy, cost control, and experimentation  
- Web-first UI supports fast group interaction  

---

## 📈 Long-Term Vision

Over time, the platform reveals:

- Who is consistently accurate  
- When groups outperform individuals  
- How confidence aligns with reality  

The ultimate goal is to **build smarter groups**, not louder ones.

---

## 🚀 Status

This project is in active development and currently focused on defining core intelligence, architecture, and minimum viable features.

Contributions, feedback, and ideas are welcome.

---
## 🐳 Run with Docker (Quick Start)

The easiest way to run the app is with Docker.

### Start everything
From the project root, run:

```bash
docker compose up --build
```
This starts:
```
Frontend → http://localhost:3000
Backend → http://localhost:8000
```

Stop everything
```
docker compose down
```

(Optional) Reset all data
```
docker compose down -v
```

(Optional) Pull an AI model
```
docker exec -it ollama ollama pull llama3
```

That’s it. You’re running the full stack locally 🚀