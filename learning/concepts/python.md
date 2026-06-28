# Python — The Basics

Python is a programming language, which is just a way to give instructions to a computer. What makes Python stand out is that it reads close to plain English — you can look at most Python programs and roughly understand what they are doing, even without knowing the language.

Python runs the majority of AI tools, data pipelines, and web backends built today. It is also where most people start when learning to code.

---

## Variables and Functions

A **variable** is a name you attach to a piece of information so you can use it later.

```python
name = "Omprakash"
age = 23
```

Now whenever you write `name`, the computer knows you mean "Omprakash."

A **function** is a reusable block of instructions. Instead of writing the same ten lines in multiple places, you write a function once and call it whenever you need it.

```python
def greet(name):
    print("Hello, " + name)

greet("Omprakash")  # Hello, Omprakash
```

Functions are the single most important concept in programming. Everything else builds on top of them.

---

## Conditions — Making Decisions

Code needs to make choices. Show a dashboard if logged in. Reject a form if a field is empty. Conditions handle this.

```python
age = 20

if age >= 18:
    print("You can vote")
else:
    print("Too young to vote")
```

You can check multiple possibilities with `elif`:

```python
score = 75

if score >= 90:
    print("A")
elif score >= 75:
    print("B")
else:
    print("C")
```

---

## Loops — Doing Things Repeatedly

A **loop** runs a block of code multiple times without you writing it out each time.

**For loop** — when you know how many times:

```python
for i in range(5):
    print(i)  # prints 0, 1, 2, 3, 4
```

**While loop** — when you repeat until something changes:

```python
password = ""
while password != "open123":
    password = input("Enter password: ")
print("Access granted")
```

---

## Exceptions — Handling When Things Go Wrong

Users do unexpected things. A file might be missing. A number might be divided by zero. **Exceptions** let your program respond to these situations gracefully instead of crashing.

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)
except ValueError:
    print("That is not a number")
except ZeroDivisionError:
    print("Cannot divide by zero")
```

Without this, any unexpected input crashes the program. With it, you can show a clear message and keep running.

---

## Libraries — Using Code Others Already Wrote

A **library** is a collection of pre-written code you can pull into your program. Instead of building everything from scratch, you import what you need.

```python
import random
print(random.choice(["heads", "tails"]))
```

Python has thousands of libraries for everything from making web servers to processing images to building AI models. This is a big reason why Python is so widely used — most things you want to do, someone has already built the hard parts.

---

## File I/O — Reading and Writing Files

Programs often need to save information between sessions or process data stored in files.

```python
# Writing
with open("notes.txt", "w") as file:
    file.write("First note")

# Reading
with open("notes.txt", "r") as file:
    print(file.read())
```

The `with` keyword handles closing the file automatically, even if something goes wrong partway through.

---

## Regular Expressions — Finding Patterns in Text

Regular expressions (regex) let you search for patterns rather than exact words — useful for validating emails, phone numbers, extracting data from documents.

```python
import re

email = "user@example.com"
if re.match(r"[\w.]+@[\w.]+\.[a-z]+", email):
    print("Valid email")
```

Once you know how to read them, regex can do in one line what would otherwise take twenty.

---

## Object-Oriented Programming — Organising Code

As programs grow, keeping all data and logic in loose variables and functions becomes messy. **Object-oriented programming** groups related things into objects using a blueprint called a **class**.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hi, I am {self.name} and I am {self.age} years old")

p = Person("Omprakash", 23)
p.greet()
```

Instead of separate variables for each person's name and age scattered across the codebase, they are bundled together in one object. This makes large programs much easier to build and change over time.
