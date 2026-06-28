# AI — The Big Picture

AI gets talked about as one thing, but it is a hierarchy of fields — each one sitting inside the one above it. Understanding the hierarchy clears up most of the confusion people have about what these terms actually mean.

---

## The Hierarchy

```
Artificial Intelligence
└── Machine Learning
    └── Deep Learning
        ├── Discriminative models  (classify things)
        └── Generative models      (create new things)
            ├── Large Language Models
            └── Other types — image, video, 3D, task
```

**Artificial Intelligence** — the field of building systems that can do things requiring human-like intelligence.

**Machine Learning** — a subfield of AI. Instead of writing explicit rules, you give the system data and let it find the rules on its own.

**Deep Learning** — a type of machine learning using artificial neural networks. Layers of connected nodes, loosely inspired by how the brain works. More layers means more complex patterns.

**Generative AI** — sits inside deep learning. These models produce new content (text, images, video) rather than just classifying existing things.

**Large Language Models** — also inside deep learning. ChatGPT, Gemini, and similar tools are LLMs. They overlap with generative AI but are specifically built around language.

---

## Machine Learning — Programs That Learn from Data

Machine learning is a program that uses input data to train a model. Once trained, that model makes predictions on data it has never seen before.

**Supervised learning** — the training data is labelled. You tell the model what each example is.

Example: restaurant order data. Each row shows the bill amount and pick-up vs delivery, with the actual tip labelled. A supervised model learns the patterns and predicts what tip to expect on the next order.

**Unsupervised learning** — no labels. The model finds natural patterns on its own.

Example: employee data with tenure and income, but no categories. The model finds two natural clusters on its own — employees on a fast track and those who are not. The groups were never defined; the model discovered them.

Key difference: supervised models compare predictions to the correct labels and adjust. Unsupervised models have no labels to compare against — they just find structure.

---

## Deep Learning — Neural Networks

Deep learning uses artificial neural networks — layers of nodes that pass information through each other. The more layers, the more complex the patterns the model can learn.

This also enables **semi-supervised learning** — train on a small amount of labelled data and a large amount of unlabelled data.

Example: a bank needs to detect fraudulent transactions. Labelling every transaction is too slow and expensive. So they label 5% of transactions and leave the other 95% unlabelled. A deep learning model learns from the 5%, applies those patterns across the rest, and improves predictions on future transactions.

---

## Discriminative vs Generative Models

**Discriminative models** classify. Show it labelled images of cats and dogs — it learns the difference. Give it a new image — it outputs a label or a probability.

Simple test: if the output is a number, a label, or a probability — it is discriminative, not generative.

**Generative models** create. They learn patterns without labels, then use those patterns to generate something new.

Example: show a generative model thousands of animal images with no labels. It learns: four legs, a tail, fur, barks. Ask it to generate a dog — it produces a new image that matches those patterns.

If the output is natural language, an image, audio, or video — it is generative AI.

---

## Types of Generative AI

| Type | Output | Examples |
|---|---|---|
| Text-to-text | Written language | ChatGPT, Google Gemini |
| Text-to-image | Images | Midjourney, DALL·E, Stable Diffusion |
| Text-to-video | Video footage | Google Imagen Video |
| Text-to-3D | 3D objects, game assets | OpenAI Shap-E |
| Text-to-task | Performs an action | Gemini summarising your Gmail inbox |

---

## Large Language Models — Pre-trained, Then Fine-tuned

LLMs are first trained on massive amounts of text to get good at general language tasks: summarising, classifying, answering questions, generating text. This is **pre-training**.

Then, using a smaller domain-specific dataset, they are **fine-tuned** for a specific purpose.

Think of training a dog. A dog first learns general commands — sit, stay, come. Then it specialises: police dog, guide dog, hunting dog. Each role needs specific additional training on top of the general foundation.

LLMs work the same way. A large company spends billions pre-training a general-purpose model. A hospital takes that model and fine-tunes it on their own medical records to improve diagnostic accuracy. The large company builds the base. The hospital brings the domain expertise.
