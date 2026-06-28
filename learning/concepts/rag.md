# RAG — Retrieval-Augmented Generation

An LLM only knows what was in its training data. Ask it about your company's internal documents, last week's news, or anything it was not trained on and it either makes something up or says it does not know.

RAG solves this by giving the model access to external information at the moment it answers a question.

---

## The Core Idea

Instead of asking the LLM to answer from memory, you:

1. **Retrieve** — find the most relevant documents or chunks of text related to the question
2. **Augment** — put those documents into the prompt alongside the question
3. **Generate** — let the LLM answer using the retrieved content as context

The model is no longer guessing from memory. It is reading the relevant material and summarising the answer.

---

## Step 1: Indexing Your Documents

Before you can retrieve anything, you prepare your documents once upfront.

**Chunking** — split each document into smaller pieces. A 50-page PDF becomes hundreds of small paragraphs. You want to retrieve the relevant part, not the whole thing.

**Embedding** — convert each chunk into a list of numbers (an embedding) that represents its meaning. Chunks about similar topics get similar numbers.

**Storing** — save the embeddings in a **vector database** designed for fast similarity search.

---

## Step 2: Retrieval

When a user asks a question:

1. Convert the question into an embedding
2. Search the vector database for chunks with the closest embeddings to the question
3. Return the top few most relevant chunks

This is **semantic search** — it finds meaning, not just keyword matches. "What is our refund policy?" will find a chunk saying "items may be returned within 30 days" even if the word "refund" never appears there.

---

## Step 3: Generation

The retrieved chunks go into the prompt alongside the question:

```
Context:
[Chunk 1: relevant paragraph]
[Chunk 2: relevant paragraph]

Question: What is our refund policy?

Answer using only the context above.
```

The LLM reads the context, finds the answer, and responds. Constrained to the provided context, it is much less likely to invent information.

---

## Why RAG Instead of Fine-Tuning?

Fine-tuning retrains the model with new information. This is slow, expensive, and the knowledge becomes stale when documents update.

RAG is dynamic. Update your document index and the model immediately has access to the new information — no retraining needed.

---

## What Can Go Wrong

**Bad chunking** — chunks too large bring noise; too small lose context needed to make sense of the answer.

**Poor retrieval** — wrong chunks come back, model answers from incorrect information.

**Hallucination at the edges** — if the retrieved context does not contain the answer, some models fill in the gap. Adding "say you do not know if the answer is not in the provided context" to the prompt helps.

A well-built RAG system pays as much attention to retrieval quality as to generation.
