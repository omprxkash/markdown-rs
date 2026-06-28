# Neural Networks — How They Actually Learn

A neural network is a program that learns by adjusting numbers. That is the whole idea. The complexity comes from how many numbers there are and how the adjustments are calculated.

---

## What a Neuron Does

A neuron takes in a set of numbers, does a small calculation, and outputs a single number. The calculation has three steps:

1. Multiply each input by a **weight** (a number that says how important that input is)
2. Add a **bias** (a number that shifts the result up or down)
3. Pass the result through an **activation function** (which adds a nonlinearity — without this, stacking neurons would be pointless)

```
output = activation( (input1 × weight1) + (input2 × weight2) + bias )
```

Stack hundreds of neurons together and you get a **layer**. Stack multiple layers and you get a **neural network**.

---

## The Forward Pass — Making a Prediction

When you feed data into a neural network, it flows forward through each layer, one calculation at a time, until it produces an output. This is called the **forward pass**.

Example: a network trained to classify images. You feed in pixel values. The first layer detects basic edges. The second combines edges into shapes. The third recognises objects. The final layer outputs a score for each category — whichever is highest is the prediction.

The network does not know any of this upfront. It figures it out through training.

---

## Loss — How Wrong You Are

After the forward pass, you compare the prediction to the correct answer. The difference is the **loss**. A high loss means the network is way off. A loss of zero means perfect.

The goal of training is to make the loss as small as possible.

---

## The Backward Pass — Tracing the Error

Once you know the loss, you need to figure out which weights caused it and by how much. This is done by working **backwards** through the network — from the output, back through every layer, back to the inputs.

At each step, you calculate the **gradient** — a number that tells you: if this weight increases slightly, does the loss go up or down, and by how much?

This is called **backpropagation**. The error at the output is traced back through every connection to find what was responsible.

---

## Gradient Descent — Getting Better

Once you have the gradients, you update each weight slightly in the direction that reduces the loss.

```
new_weight = old_weight - (learning_rate × gradient)
```

The **learning rate** controls how big each step is. Too large and the network overshoots. Too small and training takes too long.

---

## The Training Loop

Training repeats this process thousands of times:

1. Feed in a batch of examples (forward pass)
2. Calculate the loss
3. Compute gradients (backward pass)
4. Update every weight slightly
5. Repeat

Each full pass through the training data is called an **epoch**. Over many epochs, the weights settle into values that produce accurate predictions on data the network has never seen.

---

## Why Depth Matters

A network with one layer can only learn simple patterns — like drawing a straight line through data. Add more layers and the network learns combinations of combinations, eventually capturing very complex patterns.

Early layers learn simple things (edges in an image, common word patterns in text). Later layers combine those into more abstract concepts (faces, sentence meaning). This is why deep networks are powerful — and why the field is called **deep learning**.

---

## What the Network Actually Learns

The weights are everything. Before training, they are random numbers. After training, they encode all the knowledge the network has absorbed from data.

When you download a pre-trained model, you are getting billions of weights already adjusted from training on massive datasets. Fine-tuning means adjusting them slightly on your own, smaller dataset.
