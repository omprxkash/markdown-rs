# Data Structures and Algorithms

Data structures are how you organise information inside a program. Algorithms are the steps you follow to work with that information. Together they determine how fast and efficient your code is — and whether it holds up when the scale goes from 100 users to 10 million.

Choosing the wrong data structure often means the difference between code that works and code that grinds to a halt.

---

## Arrays — Items in Order

An array (called a list in Python) holds items in a fixed sequence. Each item has a position number starting at zero.

```python
fruits = ["apple", "banana", "mango"]
print(fruits[0])  # apple
print(fruits[2])  # mango
```

Fast for: accessing any item directly by its position, adding to the end.
Slow for: finding something by value (every item has to be checked), inserting in the middle.

Most other data structures are built from or compared to arrays.

---

## Linked Lists — A Chain of Nodes

Each item in a linked list stores its value and a pointer to the next item. Like train cars — each car knows which car comes after it, but to reach car 50 you have to travel through all 49 before it.

Unlike arrays, items do not need to sit next to each other in memory, so inserting or removing from the middle is much faster.

Fast for: adding or removing items anywhere in the structure.
Slow for: jumping to a specific position — you always start from the beginning.

---

## Stacks — Last In, First Out

A stack works like a pile of plates. You add to the top and take from the top. Whatever went in last comes out first.

Real uses: undo in a text editor, the browser back button, tracking function calls.

```python
stack = []
stack.append("page 1")
stack.append("page 2")
stack.append("page 3")
print(stack.pop())  # page 3 — came in last, leaves first
```

---

## Queues — First In, First Out

A queue is like a line at a ticket counter. First person in line is first to be served.

Real uses: background job processing, print queues, message delivery between services.

```python
from collections import deque
queue = deque()
queue.append("task 1")
queue.append("task 2")
print(queue.popleft())  # task 1 — first in, first out
```

---

## Hash Maps — Instant Lookup by Name

A hash map (called a dictionary in Python) stores key-value pairs. You find something not by searching through every item but by going directly to the key.

Real-world analogy: a phone book. You do not scan every name — you open to the right letter and go straight there. A hash map is even faster.

```python
contacts = {
    "Omprakash": "9876543210",
    "Ananya": "9123456789"
}
print(contacts["Omprakash"])  # instant
```

Fast for: looking up, inserting, and deleting — all near-instant regardless of how many items are stored.

**Two Sum** — a classic interview problem: given a list of numbers, find which two add up to a target. Checking every possible pair is slow. Storing each number in a hash map as you scan and checking whether its complement already exists is fast — and that is the intended solution.

---

## Trees — Hierarchy

A tree organises items in parent-child relationships. The top is the root. Every item can have children below it, but only one parent above it.

Real-world examples: your computer's file system (folders inside folders), an organisation chart, a family tree.

A **binary search tree** keeps items sorted so that finding any value takes far fewer steps than scanning a flat list — at each node you go left (smaller) or right (larger) and halve the remaining search space each time.

---

## Graphs — Connections

A graph is a collection of items (nodes) connected by links (edges). Unlike trees, connections can go in any direction and loops are allowed.

Real-world examples: maps and routes (Google Maps finds the shortest path using graph algorithms), social networks (people are nodes, friendships are edges), recommendation systems.

---

## Sorting — Arranging in Order

Two algorithms worth understanding:

**Quick sort** — picks a pivot value, places everything smaller to its left and everything larger to its right, then repeats on each side. Fast on average and works without needing extra memory.

**Merge sort** — splits the list in half repeatedly until each piece has one item, then merges them back in sorted order. Consistently fast but uses additional memory for the merge step.

Python's built-in `sorted()` uses a hybrid approach called Timsort under the hood, which is why you rarely need to implement these yourself in practice.

---

## Why This Matters

Most real engineering problems map directly to a data structure:

| Problem | Structure to reach for |
|---|---|
| Store user sessions | Hash map |
| Track undo history | Stack |
| Process tasks in order | Queue |
| Find the shortest path | Graph algorithm |
| Search sorted data quickly | Binary search tree |
| Store items in sequence | Array |

Learning to recognise which structure fits which problem is the core skill. The actual implementation comes naturally after.
