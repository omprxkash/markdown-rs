# Large Language Models — What They Are and How They Work

A large language model (LLM) is a neural network trained to predict what comes next in text. That one task — predict the next word — turns out to be enough to produce a system that can write, reason, summarise, translate, and answer questions.

---

## How Text Becomes Numbers

Computers work with numbers, not words. Before any text enters an LLM, it gets converted into numbers using **tokenisation**.

A **token** is a small chunk of text — roughly a word or part of a word. "programming" might become two tokens: "program" and "ming." A sentence of 15 words might be 20 tokens.

Each token is then converted into an **embedding** — a list of hundreds of numbers representing its meaning. Words with similar meanings end up with similar numbers. "King" and "Queen" are close to each other in this space. "Banana" is far from both.

---

## What Training Looks Like

Training an LLM is simple in principle:

1. Take a massive amount of text (books, websites, code, papers)
2. For each position in the text, ask the model to predict the next token
3. Compare the prediction to the actual next token
4. Update the weights slightly to make better predictions
5. Repeat billions of times

After enough of this, the model has absorbed patterns of language, facts about the world, reasoning structures, and coding conventions — all from learning to predict the next token.

---

## The Transformer — The Architecture Behind Every LLM

Modern LLMs are built on the **transformer architecture**. The key mechanism is **attention**.

Attention lets the model look at every other word in the context when predicting the next word. When completing "The capital of France is ___", the model gives high attention to "France" and "capital" and almost none to "The."

This is why LLMs can handle long contexts and maintain coherence — attention lets every part of the text influence every other part.

---

## Context Window

An LLM can only consider a fixed amount of text at once. This is the **context window**, measured in tokens. If the window is 128,000 tokens, the model can hold roughly 100,000 words at once before it starts forgetting the beginning.

Longer context windows are more capable but more expensive to run.

---

## In-Context Learning

LLMs do not need retraining to learn new tasks. You can teach them by example inside the prompt.

**Zero-shot:** just ask. "Translate this to French."

**Few-shot:** show examples first. "Dog → Chien. Cat → Chat. House → ?"

The model picks up the pattern from examples in the prompt and applies it to the new input.

---

## Development vs Production

**In development:** you iterate on prompts, speed matters less, errors are easy to catch, costs are low.

**In production:** latency matters — users will not wait 10 seconds. Cost scales with every request. Outputs need to be consistent and safe. You need logging, monitoring, and fallback handling.

Most LLM failures in production come from treating a development prototype as production-ready without addressing these gaps.

---

## Fine-Tuning vs Prompting

**Prompting** — write instructions and examples in the input text. No training needed. Works for most tasks.

**Fine-tuning** — continue training a pre-trained model on your own labelled examples. Better for consistent output format, specific tone, or domain knowledge not in the original training data.

Start with prompting. Fine-tune only when prompting consistently falls short.
