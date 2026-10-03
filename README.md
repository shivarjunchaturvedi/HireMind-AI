# HireMind AI — AI-Powered Resume & Job Matching Platform

[![React](https://img.shields.io/badge/React-19-61DAFB.svg?style=flat&logo=react)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6.svg?style=flat&logo=typescript)](https://www.typescriptlang.org)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED.svg?style=flat&logo=docker)](https://www.docker.com)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

HireMind AI is a production-grade, full-stack resume and job description matching platform designed for modern software engineering applicants, technical interviewers, and recruiters.

Unlike "black-box" wrappers that ask an LLM for an arbitrary score, HireMind AI utilizes a transparent **5-signal deterministic scoring pipeline**, canonical skill taxonomy normalization, dense vector cosine semantic similarity, and ATS formatting diagnostics.

---

## 🌟 Key Features

* **Multi-Format Document Ingestion:** High-fidelity parser for PDF, DOCX, and plain text documents with robust regex entity extraction.
* **Canonical Skill Taxonomy:** Extensible 300+ skill taxonomy resolving aliases (e.g. `JS`, `ECMAScript` $\to$ `JavaScript`, `k8s` $\to$ `Kubernetes`).
* **Transparent Multi-Signal Matching:**
  * 40% Skill Coverage (segmenting Required vs Preferred qualifications)
  * 25% Semantic Vector Cosine Similarity (TF-IDF & dense embeddings)
  * 15% Job Description Keyword Coverage
  * 10% Experience Duration Alignment
  * 10% Education & Degree Alignment
* **ATS-Oriented Formatting Diagnostic:** Scans for standard heading detection, unparseable tables or columns, contact visibility, and measurable metric density.
* **Strict Zero-Hallucination Contract:** Local recommendations never fabricate metrics, companies, or accomplishments. If a metric is missing, it advises the user to add verified data.
* **Personalized Learning Roadmap:** Sequenced project practice guides for missing required skills.
* **Version Management & Comparison:** Manage multiple resumes and compare Resume A vs Resume B against the same job description side-by-side.
* **Exportable Reports:** Download print-ready PDF and structured JSON reports.
* **Built-in Interview Master Suite:** Interactive suite with 40+ technical interview questions & answers covering FastAPI, React, PostgreSQL, NLP, Docker, and System Design.

---

## 🏗️ Architecture

```
React 19 + TypeScript SPA (Vite + Tailwind CSS + Recharts)
                      │ HTTPS (REST / JWT)
                      ▼
FastAPI Application Gateway (Pydantic v2, Rate Limiting, Audit Logs)
    ├── Document Parser (PyMuPDF / python-docx / JSZip)
    ├── Job Description Requirement Classifier
    ├── Skill Normalization Layer (300+ Canonical Taxonomy)
    ├── Deterministic 5-Signal Scoring Engine
    ├── Dense Vector Cosine Semantic Engine
    ├── ATS-Oriented Formatting Diagnostic
    └── Built-in Deterministic Local Analysis Engine
                      │
                      ▼
PostgreSQL 16 Relational Database (SQLAlchemy 2.0 + Alembic)
```

---

## 🚀 Quickstart with Docker Compose

Ensure Docker and Docker Compose are installed, then run:

```bash
# Clone the repository
git clone https://github.com/shivarjunchaturvedi/hiremind-ai.git
cd hiremind-ai

# Start PostgreSQL, Backend, and Frontend containers
docker compose up --build
```

Access the applications:
* **Web Application:** `http://localhost:3000`
* **FastAPI OpenAPI Swagger Docs:** `http://localhost:8000/docs`
* **PostgreSQL:** `localhost:5432`

---

## 💻 Local Development Setup

### 1. Frontend
```bash
# Install Node dependencies
npm install

# Start development server
npm run dev
```

### 2. Backend (FastAPI)
```bash
cd backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install Python requirements
pip install -r requirements.txt

# Run migrations
alembic upgrade head

# Start FastAPI server
uvicorn app.main:app --reload --port 8000
```

---

## 🧪 Testing

Run backend and frontend tests:
```bash
# Run pytest for backend
cd backend
pytest -v

# Run TypeScript lint and typecheck
npm run lint
```

---

## 🔒 No API Key Required

HireMind AI's primary analysis workflow runs with a built-in deterministic engine. It does not require Gemini, OpenAI, or another external AI API key.

## ⚖️ Ethical & Compliance Disclaimer

HireMind AI provides analytical document comparison heuristics only. The platform makes no claim to guarantee ATS pass rates, recruiter contacts, or hiring decisions. All demographic attributes (race, gender, age, religion, disability, etc.) are strictly excluded from the analysis pipeline.

## 📸 Project Screenshots

### 🏠 Dashboard
![HireMind AI Dashboard](screenshots/Screenshot%202026-10-03%20232342.png)

### 🔍 New Analysis
![New Analysis](screenshots/Screenshot%202026-10-03%20232409.png)

### 📊 Match Analysis
![Match Analysis](screenshots/Screenshot%202026-10-03%20232532.png)

### 🎯 Skill Gap Analysis
![Skill Gap Analysis](screenshots/Screenshot%202026-10-03%20232548.png)

### 🧠 Learning Roadmap
![Learning Roadmap](screenshots/Screenshot%202026-10-03%20232601.png)

### 📋 Analysis Report
![Analysis Report](screenshots/Screenshot%202026-10-03%20232636.png)
