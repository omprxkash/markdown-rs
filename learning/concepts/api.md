# APIs — How Software Talks to Other Software

An API (Application Programming Interface) is a way for one piece of software to ask another piece of software to do something, without needing to know how it works internally.

Analogy: a waiter in a restaurant. You tell the waiter what you want. The waiter passes the order to the kitchen. The kitchen prepares it. The waiter brings back the result. You never see inside the kitchen — you just talk to the waiter.

The API is the waiter. Your app is the customer. The other service (a database, payment system, AI model) is the kitchen.

---

## Why Bother with an API at All?

You could connect a frontend app directly to the database. A lot of beginners ask why you would not just do that. Here is why:

**Security** — frontend code (JavaScript, in a browser) is fully visible to any user who opens DevTools. If you put database credentials in the frontend, anyone can read them and access the database directly. An API sits in the middle, exposing only what you deliberately choose to expose.

**Versatility** — with an API backend, you can have a website, a mobile app, and a desktop app all sharing the same data. They all call the same API. One change to the backend is reflected everywhere.

**Modularity** — because the frontend and backend only communicate through a defined interface, you can rewrite the backend in a completely different language without the frontend noticing, as long as the API behaves the same.

**Interoperability** — you can make certain endpoints public and let anyone build their own app on top of your data. This is how third-party clients for Twitter, Reddit, and other platforms work.

---

## REST APIs — The Standard

**REST** is the most common style for web APIs. Every piece of data is a **resource** with its own URL. You interact with it using standard actions that map to HTTP methods:

| Action | HTTP Method | Example |
|---|---|---|
| Get data | GET | Get a list of users |
| Create data | POST | Create a new user |
| Update/replace | PUT | Replace a resource entirely |
| Delete data | DELETE | Delete a user |

---

## POST vs PUT

Both write data to the server. The difference matters in practice.

**POST** — adds a new resource. Run it twice, you get two records. The ID is assigned by the server after creation so you do not know it in advance.

**PUT** — replaces a specific resource, identified by ID in the URL (`/drinks/42`). Run it ten times with the same data and you get the same result — this is called **idempotent**. Because PUT targets an existing resource by ID, you typically POST first to create it, then PUT to update it.

In practice a lot of teams just use POST for everything. The important thing is being consistent.

---

## A Request and a Response

Every API interaction has two parts.

**Request** — what you are asking for: the URL, the method, optional headers (like authentication tokens), optional body (data you are sending, in JSON).

**Response** — what comes back: a status code and a body (the data or error message).

---

## Status Codes

| Code | Meaning |
|---|---|
| 200 | OK — everything worked |
| 201 | Created — new resource was made |
| 400 | Bad Request — something wrong with what you sent |
| 401 | Unauthorized — not logged in |
| 403 | Forbidden — logged in but not allowed |
| 404 | Not Found — resource does not exist |
| 500 | Server Error — something broke on the server |

---

## JSON — The Common Language

APIs send and receive data in **JSON** — a simple text format readable in any language.

```json
{
  "name": "Omprakash",
  "age": 23,
  "skills": ["Python", "RAG", "LangChain"]
}
```

Your app sends JSON to the API and gets JSON back.

---

## Consuming an API in Python

The `requests` library is the standard way to call any HTTP API from Python.

```python
import requests

response = requests.get("https://api.example.com/questions")
data = response.json()

for item in data["items"]:
    print(item["title"])
```

`response.status_code` gives you the HTTP status code. `response.json()` parses the response body as JSON.

---

## Building an API in Python

FastAPI is the standard Python framework for AI backends. Fast to write, automatically generates interactive documentation at `/docs`.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/drinks")
def get_drinks():
    return {"drinks": ["cola", "grape soda"]}

@app.get("/drinks/{drink_id}")
def get_drink(drink_id: int):
    return {"id": drink_id, "name": "cola"}
```

Flask is the older alternative — simpler but requires more manual wiring for JSON responses and routing.

---

## Design Principles

- URLs describe resources, not actions: `/users` not `/getUsers`
- Use the correct HTTP method — GET must never change data
- Return useful error messages: `{"error": "email is required"}` not just a 400
- Version your API: `/api/v1/users` so you can release `/api/v2/` without breaking existing clients

---

## APIs in AI Engineering

Every AI product is built on top of APIs:

- Call an LLM provider API to get completions
- Frontend calls your backend API to submit messages
- Backend calls a vector database API to retrieve chunks
- Backend calls an embedding API to convert text to vectors

APIs are the plumbing that connects every component. Understanding them is not optional in AI engineering.
