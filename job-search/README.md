# Job Search

Everything I've learned about how the job search pipeline actually works — platform mechanics, profile copy, and what changes signal to recruiters and algorithms.

This section is split into three parts:

---

## [`platforms/`](platforms/)

Platform-by-platform breakdowns of how each site actually surfaces candidates. Covers ATS fundamentals, what breaks resume parsers, how recruiter search filters work, and what the "profile completeness" scores actually measure.

Start with [`platforms/README.md`](platforms/README.md) for the ATS overview that applies everywhere, then read the individual platform files.

- [`platforms/indeed.md`](platforms/indeed.md) — how Indeed search, profile completeness, and last-active ranking work
- [`platforms/wellfound.md`](platforms/wellfound.md) — startup-focused, no ATS, human reads profile; Desired Role field matters a lot
- [`platforms/simplify.md`](platforms/simplify.md) — application tracker + auto-fill; the resume you store here is what goes into company ATS

---

## [`linkedin/`](linkedin/)

How LinkedIn recruiter search actually ranks profiles, plus my complete profile copy — paste-ready.

- [`linkedin/README.md`](linkedin/README.md) — recruiter search mechanics, Open to Work setup, InMail reply templates
- [`linkedin/headline.md`](linkedin/headline.md) — headline options with reasoning (headline is the highest-weight signal in LinkedIn search)
- [`linkedin/about.md`](linkedin/about.md) — full About section, ~220 words
- [`linkedin/experience/`](linkedin/experience/) — rewritten bullets for each role, leading with quantified outcomes

---

## [`naukri/`](naukri/)

Naukri-specific profile copy and how its search and freshness algorithms work.

- [`naukri/README.md`](naukri/README.md) — how Naukri's recruiter tools, profile visibility, and freshness algorithm work
- [`naukri/headline.md`](naukri/headline.md) — resume headline
- [`naukri/summary.md`](naukri/summary.md) — profile summary, rewritten to lead with production AI work
- [`naukri/skills.md`](naukri/skills.md) — skills ordered by recruiter search relevance
- [`naukri/projects.md`](naukri/projects.md) — which projects to show and what to archive

---

## The principle behind all of it

Recruiter search on every platform is keyword matching first. The algorithm doesn't read context — it looks for terms in specific fields and weights them by field. A skill listed under "Skills" outranks the same word buried in a job description.

The most common mistake is burying the most relevant work. Write the number first, then explain how, then leave out what's obvious from the job title.

For the mechanics of what each field actually weighs, read [`platforms/README.md`](platforms/README.md) first.
