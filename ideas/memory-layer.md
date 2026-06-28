# Project Idea: Persistent Memory Layer for LLM Agents

This is the next thing I want to build. It addresses a gap in my portfolio — everything I've shipped so far uses LLMs, but nothing is focused on memory, which is both an active research problem and something I've been thinking about for a while.

The Naukri headline already says "interested in evolving memory for LLMs and context distillation." This project would make that claim concrete.

---

## What the problem is

Current LLM agents have no memory between sessions. Every conversation starts cold. You can work around this by manually stuffing context into the system prompt, but that doesn't scale and it doesn't let the model build a real understanding of a user, a codebase, or a problem space over time.

The tools that exist are either:
- Too heavyweight (full database setups that require significant infrastructure)
- Too simple (just saving the last N messages)
- Opinionated about which LLM or framework you're using

What I want to build is a lightweight library that wraps any LangGraph agent and gives it two memory tiers that persist across sessions, with a consolidation step to stop memory from bloating.

---

## What it does

### Memory Tier 1 — Episodic (FAISS)

Stores each conversation turn as a vector embedding in a local FAISS index. On every new turn, the agent automatically retrieves the K most semantically similar past turns and injects them as context.

This is the "remember when we talked about X" layer — it surfaces relevant past conversations without requiring the model to store everything.

### Memory Tier 2 — Semantic (Neo4j)

After each conversation, a background step extracts key facts, entities, and relationships from the exchange and writes them to a Neo4j knowledge graph. The agent can query this graph directly on each turn via Cypher.

This is the "I know that X is your employer and Y is the project you're working on" layer — persistent structured facts that don't depend on semantic similarity to be retrieved.

### Memory Consolidation

A scheduled job runs every N conversations and summarises older episodic memory into more compact representations. This prevents the FAISS index from growing indefinitely and keeps retrieval fast as usage accumulates.

---

## What you end up with

A CLI chatbot that remembers you across sessions. After five conversations about a project, the agent already knows the context, the constraints, the last decision made, and the open questions — without being told again.

The demo also includes a simple web UI showing the Neo4j knowledge graph growing in real time as conversations happen.

---

## Why this is a strong portfolio piece

- "Memory for LLMs" is one of the most searched and discussed problems in AI tooling right now (2025–2026)
- There's no standard open-source solution that does exactly this — most memory libraries are either LLM-vendor locked or abandoned
- It's composable — works as a wrapper around any LangGraph agent, not just the demo chatbot
- The dual-tier design (vector + graph) maps directly to what I built at PTC (FAISS pipelines + knowledge graphs) and Campus Insight (LangGraph + Neo4j)
- Once it's on GitHub as a pip-installable package, it becomes the strongest piece in the portfolio

---

## Stack

| Component | Tool |
|-----------|------|
| Agent framework | LangGraph |
| Episodic memory | FAISS (local) or Chroma (cloud option) |
| Semantic memory | Neo4j (local via Docker) |
| LLM | Claude API (primary), configurable |
| API layer | FastAPI |
| Demo UI | React + TypeScript (optional for v1) |
| Packaging | Python package (pip installable) |
| Deployment | Docker Compose (FAISS + Neo4j + API in one command) |

---

## Build phases

**v0.1 — core memory, no UI**
- FAISS episodic retrieval working
- Neo4j entity extraction working
- LangGraph agent wrapper complete
- CLI demo working across sessions
- Docker Compose for local setup

**v0.2 — consolidation + packaging**
- Consolidation job implemented
- pip installable as a standalone library
- README with working example

**v0.3 — web UI + publish**
- React knowledge graph visualisation
- PyPI publish
- Blog post or LinkedIn writeup

---

## Name ideas

- `memchain` — memory chain for LLMs
- `agent-memory` — descriptive, searchable
- `episodic` — clean, domain-accurate
- `memnon` — from mnemonics, also sounds distinct

---

## Add to Naukri/LinkedIn when

Once v0.1 is live on GitHub with a clean README and a working demo. Even without a PyPI package, a repo that runs in one `docker compose up` command is enough to list as a project.
