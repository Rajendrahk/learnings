Great! You now know how to store information using **variables** and how Python understands different kinds of information using **data types**.

Now we learn one of the most important ideas in programming:

> **How do we avoid writing the same instructions again and again?**

The answer is: **Functions**.

Functions are used everywhere in Python and are the foundation for understanding **methods** later in OOP.

---

# Lesson 5: Functions

---

# Step 1: Explain the idea in very simple words

A **function** is a group of instructions that performs a specific task.

Think of a function as a **machine**.

You give something to the machine.

The machine does some work.

It gives you a result.

Example:

A juice machine:

```text id="p5p6kz"
       Input
         |
         ▼
 +---------------+
 | Juice Machine |
 +---------------+
         |
         ▼
      Output
       Juice
```

You don't need to know how the machine makes juice.

You only need to know:

* What to give it.
* What it gives back.

Functions work the same way.

---

# Step 2: Two Real-Life Examples

## Example 1: Washing Machine

You don't manually:

* Add water.
* Spin clothes.
* Remove dirt.
* Dry clothes.

You press a button:

> "Start Wash"

The washing machine performs many steps internally.

The button is like calling a function.

```text id="wz9e9r"
Press Start
     |
     ▼
Washing Machine
     |
     ▼
Clean Clothes
```

---

## Example 2: ATM Machine

When you choose:

> Withdraw Money

The ATM performs many hidden steps:

1. Check your card.
2. Verify your PIN.
3. Check balance.
4. Give money.
5. Update account.

You only request the action.

The ATM handles the details.

A function works similarly.

---

# Step 3: Simple Diagram

A function looks like this:

```text id="f0dr5n"
              Function

Input
  |
  ▼
+----------------+
|                |
|  Instructions  |
|                |
+----------------+
  |
  ▼
Output
```

Example:

```text id="0oz2pj"
Numbers
   |
   ▼
+-------------+
| Add Function|
+-------------+
   |
   ▼
Answer
```

---

# Why Do We Need Functions?

Imagine you need to print this message 100 times:

```python
print("Welcome to Python")
```

Without functions:

```python
print("Welcome to Python")
print("Welcome to Python")
print("Welcome to Python")
...
```

This becomes messy.

Instead, create a function:

```text id="pxw7lo"
Create once
     |
     ▼
Use many times
```

This saves:

* Time
* Effort
* Mistakes

---

# Step 4: Smallest Possible Code Example

Creating a function:

```python id="9lh4a5"
def greet():
    print("Hello")
```

Using the function:

```python id="09vquf"
greet()
```

Output:

```text id="s7n1hl"
Hello
```

---

# Step 5: Explain Every Single Line

Let's understand:

```python id="4j3g8w"
def greet():
```

### `def`

`def` means:

> "I am creating a function."

It tells Python:

"Create a reusable block of instructions."

---

### `greet`

This is the function's name.

Like a button label:

```text id="6h0l3p"
Button name:

GREETING
```

When we press this button, the function runs.

---

### `()`

These parentheses are where we can give information to the function.

For now, they are empty.

Later, we will put values inside them.

---

### `:`

The colon tells Python:

> "The instructions for this function start now."

---

Now:

```python id="oqs3tj"
    print("Hello")
```

This is the instruction inside the function.

Important:

The spaces before `print` are called **indentation**.

Python uses indentation to know which code belongs to the function.

---

Calling the function:

```python id="h7r2vh"
greet()
```

means:

> "Run the instructions inside greet."

Python jumps to:

```python id="1a3i2d"
print("Hello")
```

and executes it.

---

# What Happens in Memory?

When Python sees:

```python id="1yl5qa"
def greet():
    print("Hello")
```

Python creates a function:

```text id="q8em5b"
Memory

greet
 |
 ▼
Instructions:
 print("Hello")
```

But notice:

It does NOT print anything yet.

The function is only created.

---

When Python sees:

```python id="8f8ih8"
greet()
```

Python says:

> "Run the instructions stored in greet."

Then:

```text id="m9j1o5"
greet()
   |
   ▼
print("Hello")
   |
   ▼
Screen:
Hello
```

---

# Important Difference

Creating a function:

```python id="2v2m9p"
def greet():
    print("Hello")
```

does not execute it.

Calling a function:

```python id="0w8lqa"
greet()
```

executes it.

Think:

```text id="y8d3f1"
Recipe ≠ Eating food

Function creation ≠ Running function
```

---

# Step 6: Another Example

Let's create a function for adding numbers.

```python id="f3m9a7"
def add():
    print(5 + 3)

add()
```

Output:

```text id="jcn3b0"
8
```

Flow:

```text id="o0v8pz"
Create add function

        ↓

Call add()

        ↓

Run print(5 + 3)

        ↓

Display 8
```

---

# Functions with Input

Now let's make our function more useful.

Example:

```python id="9cc6eq"
def greet(name):
    print("Hello", name)

greet("Ravi")
```

Output:

```text id="1c9yko"
Hello Ravi
```

---

What happened?

We gave information to the function:

```python
greet("Ravi")
```

The function receives it:

```python
name = "Ravi"
```

Then:

```python
print("Hello", name)
```

becomes:

```python
print("Hello", "Ravi")
```

Output:

```text
Hello Ravi
```

---

# Common Beginner Mistakes

## Mistake 1: Forgetting to call the function

Wrong:

```python id="g6p2tb"
def hello():
    print("Hi")
```

Output:

Nothing.

Why?

Because you only created the function.

You didn't run it.

Correct:

```python id="b7b6g8"
hello()
```

---

## Mistake 2: Wrong indentation

Wrong:

```python id="m1vw52"
def hello():
print("Hi")
```

Python doesn't know the `print` belongs to the function.

Correct:

```python id="6f1g2t"
def hello():
    print("Hi")
```

---

## Mistake 3: Wrong number of inputs

Example:

```python id="4h4q9d"
def greet(name):
    print(name)
```

Calling:

```python id="v2s3j9"
greet()
```

Python says:

> "You created a function that needs a name, but you didn't provide one."

Correct:

```python id="av5g2h"
greet("Raj")
```

---

# Step 7: Questions

Answer in your own words.

### Question 1

What is a function?

---

### Question 2

Why do programmers use functions?

---

### Question 3

What is the difference between:

```python id="q8z3vh"
def hello():
```

and

```python id="91h9ks"
hello()
```

---

### Question 4

What will this print?

```python id="2m2y6m"
def say_hi():
    print("Hi")

say_hi()
```

---

### Question 5

What is the mistake here?

```python id="1s1o0z"
def greet(name):
    print(name)

greet()
```

---

# Step 8: Practice Exercises

## Exercise 1: Create a Greeting Function

Create a function called:

```python
greet
```

It should print:

```
Welcome to Python
```

Then call the function.

---

## Exercise 2: Create a Student Function

Create a function called:

```python
student_info
```

It should print:

```
Name: Ravi
Age: 18
```

Then call the function.

---

## Exercise 3: Thinking Exercise

No code.

Imagine you are creating a food delivery app.

Name three tasks that could become functions.

Example:

```
calculate_bill()
```

Your tasks:

1. ---
2. ---
3. ---

---

Reply with your answers and code. I'll review them, explain mistakes, and then we'll continue.

After functions, we will learn **"Why OOP exists"** — where you will discover why simple functions and variables are sometimes not enough for large programs, and why we need objects and classes.
