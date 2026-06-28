# Path: AI Engineer

This is an opinionated order for getting from zero to building production AI systems. Not every step is mandatory — skip what you already know. The goal is to be able to build, deploy, and explain a real AI application.

---

## Stage 1 — Python Foundations (weeks 1–4)

You cannot build AI systems without Python. Everything else depends on this.

- Variables, functions, loops, conditionals
- Lists, dictionaries, sets — when to use each
- File I/O — read and write CSVs and text files
- Libraries: `requests`, `json`, `os`
- Object-oriented basics — classes, methods, `self`

**Where to start:** CS50P (Harvard, free) or Bro Code's full Python course on YouTube.

Build something before moving on: a web scraper, a CLI tool, a file organiser.

---

## Stage 2 — Data & Math Basics (weeks 3–6, overlap with Stage 1)

You do not need to become a mathematician. You need enough to read ML papers without panic.

- **Linear algebra**: vectors, matrices, dot product, matrix multiplication → 3Blue1Brown Essence of Linear Algebra (free, YouTube)
- **Statistics**: mean, variance, distributions, Bayes theorem → StatQuest on YouTube
- **NumPy and Pandas**: the two libraries every ML engineer uses daily

---

## Stage 3 — ML Fundamentals (weeks 5–10)

Understanding what models are doing is more important than memorising formulas.

- Supervised vs unsupervised learning
- Linear regression, logistic regression, decision trees, random forests
- How neural networks learn (forward pass, loss, backpropagation, gradient descent)
- Train/validation/test split, overfitting, underfitting

**Read:** [concepts/ml-algorithms.md](../concepts/ml-algorithms.md) and [concepts/neural-networks.md](../concepts/neural-networks.md)

**Course:** Machine Learning Specialization (Andrew Ng / DeepLearning.AI, free to audit)

---

## Stage 4 — LLMs and the Modern Stack (weeks 8–14)

This is the core of AI engineering today.

- How LLMs work: tokenisation, transformers, attention, context window
- Calling LLM APIs (OpenAI, Anthropic, etc.)
- Prompt engineering: zero-shot, few-shot, chain of thought
- Embeddings and vector databases
- RAG — retrieval-augmented generation: indexing, retrieval, generation

**Read:** [concepts/llm.md](../concepts/llm.md), [concepts/embeddings.md](../concepts/embeddings.md), [concepts/rag.md](../concepts/rag.md)

**Build:** a PDF chatbot using RAG before moving on.

---

## Stage 5 — APIs and Backend (weeks 12–16)

AI products need a backend. You need to know how to expose your model as a service.

- REST APIs: HTTP methods, status codes, JSON
- FastAPI: build and document an endpoint in Python
- Databases: PostgreSQL basics, SQLite for prototypes
- Docker: containerise your app so it runs the same everywhere

**Read:** [concepts/api.md](../concepts/api.md)

**Build:** wrap your RAG chatbot in a FastAPI backend with a `/chat` endpoint.

---

## Stage 6 — Agents and Production (weeks 14–20)

- Agentic workflows: tool use, memory, multi-step reasoning
- LangChain / LangGraph for orchestrating multi-step LLM pipelines
- Evaluation: how do you know your RAG system is actually working?
- Monitoring: logging requests, tracking latency and cost
- Deployment: Railway, Render, or AWS for getting something live

**Courses:** HuggingFace Agents Course, Complete Agentic AI Course (LangChain/LangGraph)

---

## What a finished AI engineer can do

- Build a RAG system over custom documents
- Wrap it in a FastAPI backend and a simple frontend
- Deploy it so real users can hit it
- Monitor it and improve the retrieval quality over time
- Explain every component when asked in an interview
