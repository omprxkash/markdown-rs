# omari repo — how to add content and push to GitHub

## Repo locations

| Location | Path |
|----------|------|
| Local copy | `D:\Work\Personal\omari` |
| GitHub | https://github.com/omprxkash/omari |
| Private folder (never pushed) | `D:\Work\Personal\omari\private\` |

The `private/` folder is in `.gitignore` — anything saved there stays local only. Everything else in the repo is public on GitHub.

---

## Folder structure — where new content goes

```
omari/
├── learning/
│   ├── concepts/     plain-language explainers (what something IS, before code)
│   ├── resources/    curated link collections by topic
│   ├── projects/     project ideas to build
│   ├── paths/        step-by-step learning paths
│   └── career/       interview prep, certifications — generic only, no personal info
├── job-search/
│   ├── platforms/    how each job platform works (ATS, algorithms)
│   ├── linkedin/     profile copy and strategy
│   └── naukri/       profile copy and strategy
├── ideas/            project specs and concepts
├── roadmap.md        learning sequence
└── tools.md          tool recommendations
```

**Rule: anything with your name, employer, college, internship, or personal story goes in `private/` — not in the repo.**

---

## What type of content goes where

| Content type | Folder | Example |
|-------------|--------|---------|
| Concept explainer from a video/course | `learning/concepts/` | `git.md`, `api.md`, `llm.md` |
| Resource list (links, courses, tools) | `learning/resources/` | `ai-ml.md`, `python.md` |
| Project ideas | `learning/projects/builds.md` | Add a row to the existing file |
| Learning path (sequenced stages) | `learning/paths/` | `ai-engineer.md` |
| Generic interview prep (no personal info) | `learning/career/` | `data-scientist-interview.md` |
| Personal interview prep (with your story) | `private/` | `data-scientist-interview-prep.md` |
| Raw transcript (with or without timestamps) | `private/` | `transcript-ml-algorithms-tim.md` |
| Job platform notes | `job-search/platforms/` | `indeed.md` |
| Profile copy (LinkedIn/Naukri) | `job-search/linkedin/` or `job-search/naukri/` | `headline.md` |
| New project spec | `ideas/` | `memory-layer.md` |

---

## Adding a new concept explainer (most common task)

1. **Paste the transcript here** — Claude will clean it (remove timestamps, strip filler) and write a structured explainer
2. The cleaned explainer goes to `learning/concepts/<topic>.md`
3. The raw transcript (if you want to keep it) goes to `private/transcript-<topic>.md`
4. Update `learning/README.md` — add a row to the concepts table
5. Push

---

## How to push to GitHub (from PowerShell in the repo folder)

```powershell
cd D:\Work\Personal\omari

# Stage specific files (preferred — never use git add . blindly)
git add learning/concepts/newfile.md
git add learning/README.md

# Or stage everything tracked (safe since private/ is gitignored)
git add -A

# Commit
git commit -m "add <topic> concept explainer"

# Push
git push origin main
```

If push is rejected (someone else pushed or you updated GitHub directly via MCP):
```powershell
git pull origin main --rebase
git push origin main
```

---

## Working with Claude Code on this repo

When you give Claude a transcript or document to add:

1. Say which folder it belongs in (concepts, resources, career, private, etc.)
2. Say whether to push to GitHub or keep it local only
3. If it has personal info — names, employers, colleges — it stays in `private/`

Claude will:
- Strip timestamps from video transcripts
- Write the explainer in the repo's style (plain language, examples, soundbites)
- Update `learning/README.md` if a new file is added to `learning/`
- Commit with a clear message and push

---

## Current private files

| File | What it is |
|------|-----------|
| `data-scientist-interview-prep.md` | Full personal prep — opening story, company context, 30 Q&A |
| `interview-prep-data-scientist.md` | Clean version — personal parts stripped, all educational content kept |
| `job-profile-audit.md` | Cross-platform LinkedIn/Naukri/Indeed audit with specific action items |
| `transcript-ml-algorithms-tim.md` | Tim's 17-min ML algorithms transcript (timestamps removed) |
| `transcript-ml-fundamentals-sha.md` | Sha's ML fundamentals transcript (timestamps removed) |
| `workflow.md` | This file |

---

## Concepts already on GitHub

| File | Topic |
|------|-------|
| `learning/concepts/llm.md` | Transformers, tokenisation, context window, fine-tuning |
| `learning/concepts/rag.md` | Indexing, retrieval, generation pipeline |
| `learning/concepts/api.md` | REST, HTTP, FastAPI, why APIs exist |
| `learning/concepts/embeddings.md` | What embeddings are, semantic search, vector DBs |
| `learning/concepts/git.md` | Commits, branching, conflicts, merge vs rebase |
| `learning/concepts/ai-overview.md` | AI, ML, deep learning overview |
| `learning/concepts/ml-algorithms.md` | Every major algorithm with examples |
| `learning/concepts/neural-networks.md` | Forward pass, backprop, training loops |
| `learning/concepts/python.md` | Variables, functions, OOP |
| `learning/concepts/dsa.md` | Arrays, hash maps, trees, sorting |

**Gaps still to fill:** `sql.md` (referenced in paths/fullstack.md as "coming soon"), agentic AI / LangChain deep-dive
