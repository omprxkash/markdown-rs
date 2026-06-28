# markdown-rs

A personal knowledge base for AI and software engineering — put together by Omprakash, AI engineer, VIT CS grad (2025), Chennai.

**Markdown** — everything is written in plain text that renders on GitHub without any tooling.
**Rs** — Resources. Curated links, notes, learning paths, and reference material, not a blog or a portfolio.

This started as a way to organise everything collected while breaking into AI engineering: study resources, notes on how job platforms actually work, profile copy that gets responses, and specs for projects worth building. Most of it came from months of trying things and figuring out what actually helped versus what just felt productive.

Fork it, strip out what you don't need, keep whatever is useful.

---

## What's here

**Learning** — the main section. Covers AI and machine learning from the ground up: how algorithms actually work, how neural networks and large language models are built, RAG systems, agents, and the full engineering stack around them. Also covers Python, data structures, algorithms, system design, databases, and DevOps. AI resources are split into focused files (foundations, LLMs, RAG, agents, engineering) instead of one long list. Courses are tracked separately with watched vs. queued status.

**Roadmap** — the sequence that made sense after going through it: what to learn first, what to skip early on, and how each piece connects to real engineering work. Opinionated, and reflects what showed up in production and interviews, not just courses.

**Job search** — how each platform actually filters candidates (ATS mechanics, keyword weighting, search algorithms), and paste-ready profile copy for LinkedIn and Naukri with content that works. The goal was to understand the systems well enough to stop guessing.

**Ideas** — specs for projects worth building, written to be picked up and executed.

---

## Where to start

Learning AI engineering → [`learning/`](learning/)

Course watchlist (watched + queued) → [`learning/courses/watchlist.md`](learning/courses/watchlist.md)

Understanding how job platforms filter candidates → [`job-search/platforms/`](job-search/platforms/)

Profile copy you can paste and edit → [`job-search/linkedin/`](job-search/linkedin/) or [`job-search/naukri/`](job-search/naukri/)

An opinionated learning sequence → [`roadmap.md`](roadmap.md)

---

## Structure

```
markdown-rs/
├── learning/
│   ├── concepts/        # plain-language explainers (AI, LLMs, RAG, APIs, Git, Python, DSA)
│   ├── resources/
│   │   ├── ai/          # foundations · llms · rag · agents · engineering
│   │   ├── fullstack.md
│   │   ├── databases.md
│   │   ├── system-design.md
│   │   ├── devops.md
│   │   ├── python.md
│   │   ├── dsa.md
│   │   └── mathematics.md
│   ├── courses/         # watchlist — watched and queued
│   ├── paths/           # ai-engineer · fullstack
│   ├── projects/        # builds and project ideas
│   └── career/          # interview prep, certifications
├── job-search/
│   ├── linkedin/        # headline, about, experience copy
│   ├── naukri/          # headline, summary, skills, projects
│   └── platforms/       # how each platform filters candidates
├── ideas/               # project specs worth building
├── roadmap.md
└── tools.md
```

---

## The one thing that changed the most

Both profiles had the same problem — the most impressive work was buried or missing entirely.

Before: *"Worked on cloud incident management system improving operational efficiency"*

After: *"Reduced triage time by 23% using Graph RAG and LLM inference for cloud incident RCA — built the knowledge graph from Confluence docs, incident tickets, and runbooks"*

Same project. Same work. Completely different first impression. The fix was consistent: lead with the number, explain the mechanism, skip what is obvious.

---

## AI engineering path

[`roadmap.md`](roadmap.md) has the sequence worth following if you are starting now — what to prioritise, what to defer, and what actually held up in production.
