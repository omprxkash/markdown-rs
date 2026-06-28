# Embeddings and Vector Databases

Computers work with numbers, not meaning. To do anything intelligent with text — search by topic, compare sentences, find related content — you first need a way to turn language into numbers that capture meaning.

Embeddings are that bridge.

---

## What an Embedding Is

An **embedding** is a list of numbers (a vector) that represents the meaning of a piece of text.

The key property: **similar meaning → similar numbers**.

Embed "cat" and "kitten" — the resulting vectors are close together. "Cat" and "car engine" are far apart. This is not hand-coded — it emerges from training on enormous amounts of text.

A typical embedding might be 1,536 numbers long. That list encodes everything a model knows about the meaning of the input.

---

## Visualising Similarity

Imagine plotting points on a map. Each point is an embedded sentence. Sentences about cooking cluster together. Programming content clusters elsewhere. A question about Python lands near other programming content, not near pasta recipes.

Vector databases let you search this map — given a new sentence, find the closest points.

---

## Semantic Search

Traditional search finds documents by matching keywords exactly. "Refund policy" only finds documents containing those exact words.

**Semantic search** finds documents by meaning. Embed the search query and find chunks with the closest embeddings. A chunk saying "items can be returned within 30 days" will match "can I get my money back" — even with zero shared words.

This powers RAG, recommendation systems, and modern AI-powered search.

---

## Generating Embeddings

Pass text to an embedding model and get back the vector:

```python
from openai import OpenAI

client = OpenAI()

response = client.embeddings.create(
    model="text-embedding-3-small",
    input="How do neural networks learn?"
)

vector = response.data[0].embedding  # a list of 1536 numbers
```

That list can now be stored, compared, and searched.

---

## Vector Databases — Storing and Searching at Scale

Regular databases are built for exact lookups. Vector databases are built for similarity search — finding the K most similar vectors to a query, across millions of stored vectors.

Common options: Pinecone, Weaviate, Qdrant, Chroma (lightweight, runs locally).

The search algorithm is called **approximate nearest neighbour (ANN)** — slightly inexact but fast enough for real-world use.

---

## How It All Fits Together

| Step | What happens |
|---|---|
| Index documents | Chunk → embed each chunk → store in vector database |
| User sends query | Embed the query → search vector DB for closest chunks |
| Generate answer | Pass chunks + question to LLM → get response |

This is the RAG pipeline. Embeddings are what make the retrieval step work.

---

## Beyond Text

The same idea applies to images, audio, and code — any data that can be meaningfully compared. Similar images get similar vectors (reverse image search). Similar code functions cluster together (code search). The underlying principle is the same: similar things should be close in vector space.
