# Naukri Projects

The current Naukri profile shows 2023–2024 projects heavily — Heart Disease Prediction, Subtitle Generator, Cardiogastrointestinal Prediction, Caption Generation. These were fine as learning projects at the time, but they're basic ML classifiers and they make the profile look like a student portfolio when the target is a production AI engineer role.

The 2025–2026 work is dramatically stronger. Replace the old entries.

---

## Projects to ADD (keep these, prioritise order)

### 1. Campus Insight — AI-Native Learning Management System
**Date:** Feb 2026 – May 2026

Built an AI-native LMS from scratch that auto-generates courses, lectures, and quizzes on demand — no manual content authoring. LangGraph agentic workflows orchestrate Claude + Gemini + Pinecone RAG pipelines. Full AWS infrastructure (ECS, RDS, S3) with a Neo4j graph layer and GitHub Actions CI/CD.

- Cut content creation time by 70%
- Reduced deployment overhead by 40%

Stack: TypeScript, Python, LangGraph, RAG, Claude API, Gemini, Pinecone, AWS (ECS, RDS, S3), Neo4j, GitHub Actions

---

### 2. LLM-Aided OCR — Accurate Text Recognition
**Date:** Dec 2024 – Apr 2025
**Status:** Patent filed

Post-OCR correction pipeline using Tesseract, OpenAI, and Llama with semantic chunking and self-scoring. Deployed with Flask and Docker, supports async correction, OpenCV preprocessing, NER, translation, and audio output. Patent filed through IIPRD.

Stack: Python, Tesseract, OpenAI API, Llama, Flask, Docker, OpenCV

---

### 3. WarLens — Transfer Learning for Event Classification in Conflict Zones
**Date:** Feb 2025 – Apr 2025
**Published:** IEEE Xplore, Jun 2025

Transfer learning system for classifying events in conflict-zone imagery. Routes high-confidence cases to the appropriate humanitarian response cluster, surfaces ambiguous cases for human review with visual attention heatmaps.

Associated with Vellore Institute of Technology. Published on IEEE Xplore: [https://ieeexplore.ieee.org/document/11040802]

---

### 4. Enhancing 3D Models with Generative AI for Digital Fabrication
**Date:** Jun 2025 – Sep 2025

Realistic texture generation for 3D model stylisation using Variational Autoencoders (VAEs). Heightfield generation induces tactile properties in 3D objects. Formative and perception study showed 70% lower MSE vs. baseline.

Stack: Python, PyTorch, VAE, TensorFlow

---

## Projects to REMOVE or ARCHIVE

These served their purpose but are now replaced by stronger work. Remove them from the visible profile (archive them rather than delete, in case you need them later):

| Project | Reason to remove |
|---------|-----------------|
| Heart and Liver Disease Prediction using ML Classifiers | Basic scikit-learn classifiers, no novel contribution |
| AI-Based Subtitle Generator for Visually Impaired Users | Replaced by the OCR project which covers similar territory and has a patent |
| Advancement Predictive Modeling for Cardiogastrointestinal Disorders | Same category as Heart/Liver Prediction — redundant |
| Advancing Text Processing – AI Multi-Model Caption Generation | Replaced by stronger NLP work |
| TensorFlow Histopathological Cancer Detection | Keep only if the publication link is live on IEEE — if the paper is published, keep it; if not, archive |

---

## Note on the AI Engineer project (Naukri "Sep 2025 – Dec 2025")

There's a project on Naukri titled "AI Engineer" with a generic description ("Engineered an innovative Ed-Tech platform"). This is probably the Campus Insight LMS or the PB Tech RAG work — it should either be renamed and given the proper description above, or removed.

---

## Coming soon — Persistent Memory Layer for LLM Agents

Spec is in [../projects/memory-layer.md](../projects/memory-layer.md). Once the initial version is built and on GitHub, add it here as the top entry.
