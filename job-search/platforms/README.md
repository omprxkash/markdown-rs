# Job Platforms — How to Use Them and How ATS Works

Every job platform has a slightly different model. Some are search-based (Naukri, Indeed), some are invite-based (Instahyre, Wellfound), some are aggregators (Simplify). Understanding which is which changes how you invest your time on each one.

This folder has guides for each platform I use. This README covers the one thing that cuts across all of them: ATS.

---

## What ATS is and why it matters on every platform

ATS stands for Applicant Tracking System. It's the software that sits between you submitting an application and a human ever seeing it. When a recruiter posts a job, applications go into the ATS first. The ATS parses your resume, scores it against the job description, and helps the recruiter filter the pile.

The two things ATS does that matter to you:

**1. Keyword extraction**
The ATS pulls skills, job titles, and phrases from your resume and matches them against what the job description asked for. If the job says "RAG" and your resume says "retrieval-augmented generation", a dumb ATS might not match them. This is why exact phrasing from the job description matters.

Common AI/SWE keywords that parse reliably:
- Write "LangChain" not "Langchain" (capitalisation matters in some systems)
- "Python" not "python" or "Python 3"
- "Machine Learning" in full, not just "ML" (some systems don't expand acronyms)
- "Natural Language Processing" and "NLP" — include both
- "RAG" and "Retrieval-Augmented Generation" — include both
- "AWS" not "Amazon Web Services" (the acronym is the recognised term)

**2. Resume parsing**
ATS reads your resume as plain text. Anything that breaks the parser means your information doesn't get read correctly. Common culprits:

| Thing that breaks ATS | What to do instead |
|----------------------|-------------------|
| Two-column resume layout | Single column only |
| Tables for the skills section | Plain comma-separated list or bullet points |
| Text inside images or logos | Text only — no scanned PDFs |
| Unusual section headers ("What I've Done") | Standard headers ("Experience", "Skills", "Education") |
| Fancy fonts (thin weights, decorative) | Any standard sans-serif — Calibri, Arial, Helvetica |
| Headers and footers containing key info | Put name and contact in the main body |
| PDF created from a design tool (Canva, Figma) | Export from Word, Google Docs, or LaTeX |

**The safe resume format:** Single column. Standard section headers. Contact info at the top in plain text. Dates in MM/YYYY format. Skills as a comma-separated inline list, not a table or icon grid.

---

## How each platform feeds ATS differently

| Platform | Who sees it first | How ATS applies |
|----------|------------------|-----------------|
| Indeed | Indeed's own parser + company ATS if they redirect | Your Indeed profile IS your application — completeness matters |
| LinkedIn Easy Apply | LinkedIn sends your profile to company ATS | LinkedIn profile needs to mirror your resume |
| Naukri | Naukri's algorithm + company ATS for downloads | Naukri scores your resume before companies do |
| Wellfound | Company team (no ATS layer — it's direct) | No ATS; your profile is read by humans from day one |
| Instahyre | Instahyre scores profile → passes to company | Keyword match matters; profile completeness score is shown |
| Simplify | Aggregates listings; auto-fills into company ATS | The resume you store in Simplify needs to be ATS-clean |

---

## The one universal rule

Match your language to the job description. Read the JD, note the exact phrases they use for the skills you have, and make sure those exact phrases appear at least once in your resume. This is not keyword stuffing — it's speaking the same language as the system that filters you.

---

## Platform guides

| File | Platform | Type |
|------|----------|------|
| [indeed.md](indeed.md) | Indeed | Search-based, profile completeness |
| [wellfound.md](wellfound.md) | Wellfound (AngelList) | Invite/startup-focused |
| [simplify.md](simplify.md) | Simplify.jobs | Aggregator + application tracker |
