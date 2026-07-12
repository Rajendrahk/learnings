Excellent! You've completed the first two lessons, and now we're reaching one of the most important concepts in programming.

> **If programming is like solving math problems, variables are like your notebook where you write down answers so you don't forget them.**

Variables are used in almost every Python program you'll ever write, including OOP.

---

# Lesson 3: Variables

---

# Step 1: Explain the idea in very simple words

Imagine you're in school.

Your teacher tells you:

> "Remember this number: **95**."

You can try to remember it in your head.

But what if she then says:

* Remember **87**
* Remember **63**
* Remember **42**

Soon, it gets difficult.

Instead, you write them in a notebook.

Your notebook **stores** the information.

A **variable** is like that notebook.

It stores information so the computer can use it later.

Think of a variable as a **labeled box**.

You put something inside the box, and later you can open the box and use what's inside.

---

# Step 2: Two Real-Life Examples

## Example 1: A Labeled Box

Imagine you have a box with a label:

```text
+------------------+
|      AGE         |
|                  |
|       25         |
+------------------+
```

The label is **AGE**.

The value inside is **25**.

Later, instead of remembering `25`, you simply say:

> "Look inside the AGE box."

That's exactly what a variable does.

---

## Example 2: Student Lockers

Every student has a locker.

```
Locker 101 → Alice's books
Locker 102 → Bob's books
Locker 103 → Charlie's books
```

You don't carry everything in your hands.

You store things in lockers and retrieve them later.

Variables are the computer's lockers.

---

# Step 3: Simple Diagram

```text
          Variable

      +-----------+
Name: |  age      |
      +-----------+
      |    25     |
      +-----------+

Variable Name = age

Stored Value = 25
```

Another example:

```text
      +--------------+
Name: | student_name |
      +--------------+
      |    "Alex"    |
      +--------------+
```

The **name** identifies the variable, and the **value** is what it stores.

---

# Step 4: Smallest Possible Code Example

```python
age = 25

print(age)
```

Output:

```text
25
```

---

# Step 5: Explain Every Single Line

## Line 1

```python
age = 25
```

This line does **not** mean "age equals 25" like in mathematics.

In Python, `=` means:

> **Store the value on the right inside the variable on the left.**

Think of it like this:

```text
        Put 25
           │
           ▼

+----------------+
|     age        |
|----------------|
|      25        |
+----------------+
```

Now the computer remembers that `age` contains `25`.

---

## Line 2

```python
print(age)
```

Python looks inside the variable named `age`.

It finds:

```text
25
```

Then it prints:

```text
25
```

Notice something important:

We wrote:

```python
print(age)
```

**Not:**

```python
print(25)
```

The computer replaced `age` with its stored value.

---

# What Happens in Memory?

Let's imagine the computer's memory.

Before running the program:

```text
Memory

(empty)
```

After this line:

```python
age = 25
```

Memory becomes:

```text
Memory

age
 │
 ▼
25
```

Then Python reaches:

```python
print(age)
```

It looks inside memory:

```text
age → 25
```

Then prints:

```text
25
```

This is a simplified view, but it's a good mental model for now.

---

# Common Beginner Mistakes

## Mistake 1: Thinking `=` means "equals"

In math:

```
x = 5
```

means "x equals 5."

In Python:

```python
x = 5
```

means:

> "Store `5` in the variable `x`."

It's an **assignment**, not a mathematical equation.

---

## Mistake 2: Using Quotes Around the Variable Name

Wrong:

```python
age = 25

print("age")
```

Output:

```text
age
```

Why?

Because `"age"` is just text.

Correct:

```python
age = 25

print(age)
```

Output:

```text
25
```

---

## Mistake 3: Using a Variable Before It Exists

Wrong:

```python
print(age)

age = 25
```

Python reads from top to bottom.

When it reaches `print(age)`, it asks:

> "What is `age`?"

It hasn't been created yet, so Python raises an error.

Correct:

```python
age = 25

print(age)
```

---

# Step 6: Another Example

```python
student = "Alice"

print(student)
```

Output:

```text
Alice
```

Let's follow it:

```text
student = "Alice"

Memory

student
   │
   ▼
"Alice"
```

Then:

```python
print(student)
```

Python looks inside `student`, finds `"Alice"`, and prints:

```text
Alice
```

---

Another example:

```python
city = "Mumbai"

print(city)
```

Output:

```text
Mumbai
```

Again, Python prints the **value stored in the variable**, not the variable's name.

---

# Naming Variables

Variable names should describe what they store.

Good names:

```python
age = 25
name = "Rahul"
salary = 50000
country = "India"
```

Not-so-good names:

```python
a = 25
x = "Rahul"
q = 50000
```

These work, but they don't tell you what the values represent. Descriptive names make your code easier to read.

---

# Step 7: Questions

Answer these in your own words.

### Question 1

What is a variable?

---

### Question 2

What does this line do?

```python
age = 25
```

---

### Question 3

What will this program print?

```python
name = "Riya"

print(name)
```

---

### Question 4

What will this program print?

```python
city = "Delhi"

print("city")
```

Be careful—this is a common beginner mistake.

---

### Question 5

Which is correct?

A)

```python
print(age)

age = 20
```

B)

```python
age = 20

print(age)
```

---

# Step 8: Practice Exercise

## Exercise 1

Create a variable called `fruit` and store your favorite fruit in it.

Then print the variable.

For example (don't copy this unless your favorite fruit is Mango):

```python
fruit = "Mango"

print(fruit)
```

---

## Exercise 2

Create **three variables**:

* `name`
* `age`
* `country`

Store your own information in them.

Then print each one on a separate line.

**Hint:** Use three `print()` statements.

---

## A Small Challenge (No Hints Yet!)

Without running the code, tell me what this prints:

```python
number = 50

print(number)

print(100)

print("number")
```

Write the output line by line.

---

Once you answer these questions and complete the exercises, I'll review everything carefully. After you're comfortable with variables, we'll move on to **Lesson 4: Data Types**, where you'll learn that not all data is the same—numbers, text, and true/false values are all handled differently by Python. This understanding is essential before we start writing more powerful programs.


Fantastic! You're doing well, and I also noticed that you're starting to use more precise programming language like **"named storage location in memory."** That's a great sign that you're understanding the concepts, not just memorizing them.

Let's review everything carefully.

---

# Review of Your Answers

## Question 1

**Question:** What is a variable?

**Your answer:**

> A variable is a named storage location in a computer's memory that holds a value.

✅ **Excellent!**

That's a very good definition.

For a beginner, I'd also keep this simple version in mind:

> A variable is a named box that stores a value.

Both definitions describe the same idea. As you progress, you'll naturally use the more technical one.

---

## Question 2

**Question:**

```python
age = 25
```

What does this line do?

**Your answer:**

> age variable stores 25

✅ Correct!

A slightly more complete explanation would be:

> It creates a variable named `age` and stores the value `25` in it.

---

## Question 3

```python
name = "Riya"

print(name)
```

Your answer:

> Riya

✅ Correct!

Python looks inside the variable `name` and prints its value.

---

## Question 4

This one is interesting!

The code was:

```python
city = "Delhi"

print("city")
```

Your answer:

> Delhi

❌ **Not quite.**

This is one of the most common beginner mistakes.

Let's think about it carefully.

There are **two different things** here:

```python
city
```

and

```python
"city"
```

They are **not the same**.

### `city`

This is a **variable**.

Python looks inside it.

```
city
 ↓
"Delhi"
```

So:

```python
print(city)
```

prints:

```
Delhi
```

---

### `"city"`

This is **just text**.

Python does **not** look inside a variable.

It prints exactly what is written.

```python
print("city")
```

Output:

```
city
```

Notice the difference:

```python
city = "Delhi"

print(city)
```

Output:

```
Delhi
```

But:

```python
city = "Delhi"

print("city")
```

Output:

```
city
```

### Memory Trick

Think of it this way:

* **Without quotes** → "Look inside the box."
* **With quotes** → "Print these letters exactly."

---

## Question 5

You answered:

> Option B

✅ Correct!

Because Python executes code from top to bottom.

---

# Exercise 1

```python
fruit = "Guava"

print(fruit)
```

✅ Perfect!

Output:

```
Guava
```

---

# Exercise 2

```python
name = "raj"
age = "20"
country = "India"

print(name)
print(age)
print(country)
```

✅ Almost perfect.

Output:

```
raj
20
India
```

However, there's one small thing I'd like to discuss.

You wrote:

```python
age = "20"
```

Notice the quotation marks.

That means `"20"` is **text**, not a number.

Later, when we learn **data types**, you'll understand why this matters.

If you want `age` to be a number, you would write:

```python
age = 20
```

without quotes.

For now, don't worry too much—we'll cover this in the next lesson.

---

# Challenge Question

The code was:

```python
number = 50

print(number)

print(100)

print("number")
```

Your answer:

```
50
100
number
```

✅ Excellent!

Let's explain each line:

```python
number = 50
```

Store `50` in the variable `number`.

---

```python
print(number)
```

Look inside the variable.

Output:

```
50
```

---

```python
print(100)
```

Print the number directly.

Output:

```
100
```

---

```python
print("number")
```

Print the text `"number"`.

Output:

```
number
```

---

# What Happens in Memory?

Let's visualize your program:

```python
name = "raj"
age = 20
country = "India"
```

Memory:

```text
+----------------------+
| name    →  "raj"     |
| age     →   20       |
| country → "India"    |
+----------------------+
```

Now imagine Python sees:

```python
print(country)
```

It does this:

```text
country
    │
    ▼
"India"

↓

Display:

India
```

This is exactly how variables work.

---

# Common Beginner Mistakes (Based on Today's Lesson)

### Mistake 1: Confusing variables with strings

```python
print(name)      # Uses the variable
print("name")    # Prints the word "name"
```

Remember:

* No quotes → Variable
* Quotes → Text

---

### Mistake 2: Using unclear variable names

Instead of:

```python
x = 20
```

Prefer:

```python
age = 20
```

Your future self (and other programmers) will thank you.

---

# Quick Revision Quiz (Lessons 1–3)

Answer these without running the code.

### 1.

What is a variable in your own words?

---

### 2.

What is the difference between:

```python
print(city)
```

and

```python
print("city")
```

---

### 3.

What will this print?

```python
country = "India"

print(country)
```

---

### 4.

What will this print?

```python
country = "India"

print("country")
```

---

### 5.

Which one stores the number `10`?

A)

```python
age = "10"
```

B)

```python
age = 10
```

---

# Flashcards

**Flashcard 1**

**Q:** What is a variable?

**A:** A named place in memory that stores a value.

---

**Flashcard 2**

**Q:** What does `=` mean in Python?

**A:** Assign (store) the value on the right to the variable on the left.

---

**Flashcard 3**

**Q:** What is the difference between `city` and `"city"`?

**A:**

* `city` → Variable
* `"city"` → Text (a string)

---

# Summary Table

| Concept          | Meaning                      | Example        |
| ---------------- | ---------------------------- | -------------- |
| Variable         | A named storage location     | `age = 20`     |
| Assignment (`=`) | Stores a value in a variable | `name = "Raj"` |
| Variable         | Accesses the stored value    | `print(name)`  |
| String           | Text inside quotes           | `"Hello"`      |
| Number           | Numeric value without quotes | `25`           |

---

# Progress Tracker

* ✅ 1. What is Programming?
* ✅ 2. Problems and Solutions
* ✅ 3. Variables
* ⏳ 4. Data Types
* ⏳ 5. Functions
* ⏳ 6. Why OOP Exists
* ⏳ ...and many more to come.

You're making steady progress. I especially like that you're explaining concepts in your own words—that's one of the best ways to learn. In the next lesson, **Data Types**, you'll discover why `20` and `"20"` are not the same thing, even though they look similar. That lesson will also explain why I pointed out the difference in your `age` variable today.
