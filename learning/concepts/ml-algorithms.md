# ML Algorithms

A ground-up guide to every major machine learning algorithm — what it does, why it works, and when to use it. Written to actually explain the intuition, not just list names.

---

## What is Machine Learning

Intelligence requires a model of the world — a compressed version of reality you can use to make predictions. If you see dark clouds, your mental model of weather tells you it will rain. You built that model from experience and from things people taught you.

Computers can do the same. Machine learning is the field that gets computers to learn from data rather than being explicitly programmed with step-by-step instructions.

**Two main branches:**

**Supervised learning** — you have a dataset with inputs (features) and a known correct output (label). The algorithm learns the relationship so it can predict outputs for new inputs. Examples: predicting house prices from square footage and location, classifying an email as spam or not spam.

**Unsupervised learning** — no labels, no known correct answer. The algorithm finds patterns or structure in the data on its own. Examples: grouping customers by purchase behaviour, reducing the number of features in a dataset.

---

## How Computers Actually Learn

Training a machine learning model is a two-phase process.

**Phase 1: Training** — you give the algorithm a training dataset (inputs + known outputs), and it adjusts its internal parameters to minimise the difference between its predictions and reality. This difference is called the **loss function**. The goal of training is to find the parameter values that make the loss as small as possible.

**Phase 2: Inference** — once trained, you give the model new data it hasn't seen, and it makes predictions.

For a simple linear model like predicting tomorrow's temperature from today's: the model is `y = mx + b`. Training means finding the right values of `m` and `b`. You do this by computing the gradient of the loss function with respect to the parameters and adjusting them step by step — this algorithm is called **gradient descent**.

---

## Supervised Learning: Regression

Regression means predicting a continuous numeric value.

### Linear Regression

The foundation of almost every machine learning algorithm. You fit a straight line (or a plane in higher dimensions) to a dataset by minimising the sum of squared distances between your predictions and the actual values.

**Example:** Predict the price of a house. Your features might be square footage, location, and year built. Linear regression finds the equation that best fits the training data — it might tell you that for every additional square metre, the price increases by $3,000, and that the year of construction has no significant effect on price.

### Logistic Regression

Despite the name, logistic regression is a classification algorithm. Instead of fitting a straight line, it fits an **S-shaped sigmoid curve** that outputs a probability between 0 and 1.

**Example:** Predict the probability that a person is male based on their height and weight. The output is a probability like "80% chance this is a man." You pick a threshold (say 0.5) to make the final classification call.

---

## Supervised Learning: Classification

### K-Nearest Neighbors (KNN)

To classify a new data point, look at the K data points nearest to it in the training set and take the majority class.

**Example:** Predict someone's gender based on height and weight. With K=5, find the 5 people in the training data closest to the new person and assign whichever gender appears most.

- Too small K: memorises training data, fails on new data — **overfitting**
- Too large K: predictions over-averaged, loses meaningful distinctions — **underfitting**

### Support Vector Machine (SVM)

SVMs find a **decision boundary** that separates classes with the **largest possible margin** between them. This makes it robust to noise and outliers.

**Example:** Classify cats vs elephants by weight and nose length. The SVM finds the line that maximises the gap between the two clusters. The data points on the edge of this gap are the **support vectors**.

Kernel functions let SVMs find highly complex non-linear boundaries without explicitly computing new features — the **kernel trick**.

### Naive Bayes

A fast probabilistic classifier based on Bayes' theorem. Assumes all features are independent of each other — rarely true, but works surprisingly well in practice.

**Example — spam filter:** Count how often words like "free" and "winner" appear in spam vs not-spam emails. For a new email, multiply together the probabilities of each word. If the product is high enough, it's spam.

### Decision Trees

A series of yes/no questions that partition your data until each group is as pure as possible.

**Example — heart attack risk:** "Is the patient over 55?" → "Does the patient smoke?" → leaf nodes of high-risk or low-risk. The algorithm finds splits that create the purest groups.

---

## Ensemble Methods

### Bagging & Random Forests

**Bagging** trains many models in parallel, each on a different random subset of the data, then combines their votes.

**Random Forest** applies this to decision trees with an extra twist: each tree only sees a random subset of features at each split. This removes correlation between trees and makes the forest much more robust.

### Boosting — AdaBoost, Gradient Boosting, XGBoost

Trains models **in sequence**. Each model focuses on the examples the previous model got wrong. Weak models combine into a strong model.

Boosted trees often reach higher accuracy than random forests but are more prone to overfitting and slower to train.

---

## Neural Networks & Deep Learning

### The Neuron

A neuron takes inputs, multiplies each by a weight, sums them, adds a bias, then passes the result through a nonlinear activation function. Without the nonlinearity, stacking layers is pointless — it all collapses to a single linear equation.

### Hidden Layers & Automatic Feature Engineering

Add hidden layers between input and output. The network discovers intermediate features automatically — things like "horizontal line detected" in an image, without you ever defining that concept.

```
raw pixels → edges → shapes → whole objects → complex concepts
```

This is deep learning: many layers of increasingly abstract features.

### Network Architectures

| Architecture | What it's for |
|---|---|
| Feedforward (MLP) | General-purpose |
| Recurrent (RNN / LSTM) | Sequential data — text, time series |
| Convolutional (CNN) | Images |
| Transformer | NLP, LLMs — uses attention layers |

### Training: Loss Landscape & Gradient Descent

The loss landscape for neural networks is jagged and complex. Gradient descent navigates it: compute gradient → step in opposite direction → repeat.

**Adam** is the most common optimizer today — adapts the learning rate per parameter and uses momentum to smooth updates.

| Hyperparameter | What it controls |
|---|---|
| Epochs | Passes through the full training dataset |
| Learning rate | Step size in gradient descent |
| Batch size | Examples per gradient update |
| Dropout rate | Fraction of neurons zeroed to prevent overfitting |

---

## Unsupervised Learning

### Clustering vs Classification

**Classification** — you know the categories and have labelled data.
**Clustering** — no labels exist. The algorithm finds natural groupings on its own.

### K-Means Clustering

1. Randomly place K cluster centres
2. Assign every data point to the nearest centre
3. Recalculate each centre as the mean of its assigned points
4. Repeat until centres stop moving

**Example:** Sort emails into 3 groups without saying what those groups are. The algorithm finds 3 natural clusters — you name them after inspecting.

---

## Dimensionality Reduction

### PCA — Principal Component Analysis

Finds the directions in your data with the most variance and projects everything onto those directions.

**Example:** Predicting fish species. Height and length are strongly correlated. PCA creates a single "shape" feature that captures most of the variance from both, dropping the redundant second dimension. In large datasets this can reduce dozens of correlated features to a handful.

---

## Reinforcement Learning

The model learns by interacting with an environment and receiving rewards or penalties:

1. Agent takes an action
2. Environment responds
3. Agent receives a reward signal
4. Parameters update based on that signal
5. Repeat

**AlphaGo** showed what RL can do: the supervised learning version trained on grandmaster games plateaued just below grandmaster level. The RL version — trained by playing itself millions of times — surpassed every human player and discovered moves grandmasters had never considered.

---

## Picking the Right Algorithm

| Problem type | Start with |
|---|---|
| Predict a number | Linear Regression |
| Binary yes/no | Logistic Regression or SVM |
| Multi-class classification | Decision Tree → Random Forest → Neural Network |
| Complex patterns, lots of data | Neural Network (deep learning) |
| No labels, find groups | K-Means Clustering |
| Too many correlated features | PCA first |
| Learning from interaction | Reinforcement Learning |

Start simple. Add complexity only when the simpler model is not good enough.
