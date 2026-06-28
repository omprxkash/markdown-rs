# Path: Full Stack Developer

Full stack means you can build both what users see (frontend) and what runs behind it (backend + database). This path goes from zero to a deployed web application. It is longer than the AI path — budget 6–9 months for your first real project.

---

## Before you start — find your why

Set a concrete goal before touching the first tutorial. Vague goals produce vague results.

Good goals:
- "I want to get a software engineering internship by April"
- "I want to build and launch a SaaS product by end of year"
- "I want to build 5 projects that use both frontend and backend"

Project-oriented goals keep you honest. If it is June and you wanted 5 projects but you only have 1, you know to speed up.

---

## Stage 1 — Internet & Web Fundamentals (week 1)

Everything on this path happens on the web. Before writing any code, understand the system you are building on.

- How the internet works (DNS, HTTP, client–server model)
- What happens when you type a URL and press Enter
- Difference between a website and a web application

---

## Stage 2 — HTML & CSS (weeks 2–4)

HTML is the structure. CSS is the styling. Together they produce everything visual on the web.

- HTML tags: headings, paragraphs, links, images, forms, divs, spans
- CSS: box model, flexbox, grid, colours, typography, responsive design
- Chrome DevTools: inspect elements, debug layout, watch network requests

**Tip:** as soon as you get stuck, ask an LLM. Describe your problem, paste your code, ask why it is not working. This accelerates learning more than opening 10 Google tabs.

**Project:** build a personal landing page from scratch — no templates.

---

## Stage 3 — JavaScript (weeks 4–8)

JavaScript makes web pages interactive and is the language of the frontend.

- Variables, functions, arrays, objects
- DOM manipulation: selecting elements, listening for events, updating content
- Async JavaScript: fetch, promises, async/await
- ES6+ features: arrow functions, destructuring, spread operator, modules

**Project:** a browser-based to-do list that saves to localStorage.

---

## Stage 4 — React (weeks 8–12)

React is the standard library for building complex user interfaces.

- Components, props, state
- useEffect, useState hooks
- Routing with React Router
- Calling APIs from the frontend

**Project:** a multi-page app that fetches data from a public API and displays it.

---

## Stage 5 — Backend with Node.js or Python (weeks 10–16)

The backend handles business logic, authentication, and database operations.

**Option A — Node.js (Express):** same language as the frontend, large ecosystem
**Option B — Python (FastAPI or Django):** better for teams heading toward AI/ML

What to learn regardless of language:
- REST API design: routes, HTTP methods, status codes, JSON responses
- Middleware: logging, error handling, authentication
- Environment variables and secrets management

**Project:** build the backend for your frontend from Stage 4 — replace the public API with your own.

---

## Stage 6 — Databases (weeks 14–18)

Applications need to store data. Most production apps use a relational database.

- SQL basics: SELECT, INSERT, UPDATE, DELETE, JOIN
- PostgreSQL for production, SQLite for local dev
- ORMs (Prisma for Node, SQLAlchemy for Python) — interact with the database using code instead of raw SQL
- When to use NoSQL (MongoDB) vs SQL

**Read:** [concepts/sql.md](../concepts/sql.md) (coming soon)

---

## Stage 7 — Auth, Deployment & Polish (weeks 18–24)

- Authentication: sessions vs JWTs, OAuth (sign in with Google)
- Deployment: Railway or Render for the backend, Vercel for the frontend
- CI/CD basics: GitHub Actions to run tests and deploy on push
- Environment management: `.env` files, never commit secrets

**Final project:** a full stack SaaS application with user accounts, a database, and a deployed URL you can share.

---

## What a finished full stack developer can do

- Build a React frontend that communicates with a custom REST API
- Design and query a relational database
- Handle user authentication securely
- Deploy both frontend and backend so real people can use it
- Debug frontend issues in DevTools and backend issues in server logs
