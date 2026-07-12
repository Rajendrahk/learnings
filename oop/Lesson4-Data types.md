Great! You have now learned that variables are **boxes that store information**.

But there is an important question:

> What kind of information can a box store?

A box can store many things:

* A number
* A person's name
* A yes/no answer
* A list of items

In programming, the **kind of information stored** is called a **data type**.

Let's begin.

---

# Lesson 4: Data Types

---

# Step 1: Explain the idea in very simple words

A **data type** tells Python what kind of value something is.

Think about different containers in your house.

You don't store everything in the same container.

Example:

```text
Kitchen shelf

+-------------+
| Rice Box    |  → Rice
+-------------+

+-------------+
| Water Bottle|  → Water
+-------------+

+-------------+
| Pencil Box  |  → Pencils
+-------------+
```

The containers are different because the things inside are different.

Data types work the same way.

A computer needs to know:

* Is this a number?
* Is this text?
* Is this true or false?
* Is this a collection of things?

---

## The main Python data types we will learn first:

| Data Type        | Stores          | Example   |
| ---------------- | --------------- | --------- |
| Integer (`int`)  | Whole numbers   | `25`      |
| Float (`float`)  | Decimal numbers | `5.5`     |
| String (`str`)   | Text            | `"Hello"` |
| Boolean (`bool`) | True/False      | `True`    |

Don't worry about the technical names yet. We will learn them slowly.

---

# Step 2: Two Real-Life Examples

## Example 1: Student Information

Imagine a student record.

```text
Student

Name: Rahul
Age: 20
Height: 5.8 feet
Passed Exam: Yes
```

Different information has different types:

```text
Name          → Text
Age           → Number
Height        → Decimal number
Passed Exam   → True/False
```

---

## Example 2: Shopping Cart

A shopping app stores:

```text
Product Name: "Laptop"
Quantity: 2
Price: 55000.50
Payment Completed: True
```

Different information:

```text
"Laptop"      → Text
2             → Whole number
55000.50      → Decimal number
True          → Yes/No answer
```

---

# Step 3: Simple Diagram

Think of variables as boxes.

Each box has a label and a type.

```text
+----------------+
| age            |
|----------------|
| 20             |
| Type: Number   |
+----------------+


+----------------+
| name           |
|----------------|
| "Rahul"        |
| Type: Text     |
+----------------+


+----------------+
| passed         |
|----------------|
| True           |
| Type: Boolean  |
+----------------+
```

---

# Step 4: Smallest Possible Code Examples

## 1. Integer (Whole Number)

```python
age = 20

print(age)
```

Output:

```text
20
```

---

## 2. Float (Decimal Number)

```python
height = 5.8

print(height)
```

Output:

```text
5.8
```

---

## 3. String (Text)

```python
name = "Rahul"

print(name)
```

Output:

```text
Rahul
```

---

## 4. Boolean (True/False)

```python
is_student = True

print(is_student)
```

Output:

```text
True
```

---

# Step 5: Explain Every Line of Code

Let's take this example:

```python
age = 20
```

Python sees:

* Variable name: `age`
* Value: `20`

It stores:

```text
Memory

age
 |
 ▼
20
```

Python understands:

> "This is a number."

---

Now:

```python
name = "Rahul"
```

Python sees quotation marks:

```python
"Rahul"
```

It understands:

> "This is text."

Memory:

```text
name
 |
 ▼
"Rahul"
```

---

Now:

```python
is_student = True
```

Python understands:

> "This is a yes/no value."

Memory:

```text
is_student
 |
 ▼
True
```

---

# Important Difference: 20 vs "20"

This is very important.

Look:

```python
age = 20
```

Here:

```text
20 → Number
```

Python can do mathematics:

```python
print(age + 5)
```

Output:

```text
25
```

---

But:

```python
age = "20"
```

Here:

```text
"20" → Text
```

Python sees it as words.

It is not a number.

It is like writing:

```text
"twenty"
```

The computer sees characters.

---

# Memory View

## Number:

```text
age = 20


+-------+
| age   |
+-------+
|  20   |
+-------+
Type: Number
```

---

## Text:

```text
age = "20"


+-------+
| age   |
+-------+
| "20"  |
+-------+
Type: Text
```

They look similar to humans.

But Python treats them differently.

---

# Step 6: Another Example

Let's create a small person profile:

```python
name = "Amit"
age = 22
height = 5.9
is_employed = False

print(name)
print(age)
print(height)
print(is_employed)
```

Output:

```text
Amit
22
5.9
False
```

Let's identify the types:

```text
name
 |
 └── Text


age
 |
 └── Whole Number


height
 |
 └── Decimal Number


is_employed
 |
 └── True/False
```

---

# A Useful Python Tool: Checking Data Type

Python has a function called `type()`.

It tells us the data type.

Example:

```python
age = 20

print(type(age))
```

Output:

```text
<class 'int'>
```

Meaning:

Python says:

> "This is an integer (whole number)."

Another:

```python
name = "Raj"

print(type(name))
```

Output:

```text
<class 'str'>
```

Meaning:

> "This is a string (text)."

We will use `type()` often while learning.

---

# Common Beginner Mistakes

## Mistake 1: Putting quotes around numbers

Wrong:

```python
price = "500"
```

This is text.

Correct:

```python
price = 500
```

This is a number.

---

## Mistake 2: Forgetting quotes for text

Wrong:

```python
name = Rahul
```

Python asks:

> "What is Rahul? A variable?"

Correct:

```python
name = "Rahul"
```

Now Python knows it is text.

---

## Mistake 3: Confusing True and "True"

These are different:

```python
is_open = True
```

Boolean.

But:

```python
is_open = "True"
```

Text.

---

# Step 7: Questions

Answer in your own words.

### Question 1

What is a data type?

---

### Question 2

What is the difference between:

```python
age = 20
```

and

```python
age = "20"
```

---

### Question 3

Identify the data type:

```python
name = "Apple"
```

---

### Question 4

Identify the data type:

```python
price = 99.99
```

---

### Question 5

What will this print?

```python
is_ready = True

print(is_ready)
```

---

# Step 8: Practice Exercises

## Exercise 1

Create variables for:

* Your name
* Your age
* Your height
* Whether you are a student or not

Example structure:

```python
name = "..."
age = ...
height = ...
is_student = ...
```

Then print all four.

---

## Exercise 2

Look at these and tell me the data type:

```python
a = 100

b = 10.5

c = "Python"

d = False
```

Answer like:

```
a = ?
b = ?
c = ?
d = ?
```

---

## Challenge

Without running the code, predict the output:

```python
x = 10

y = "10"

print(x)
print(y)
```

---

Reply with your answers and exercises. I'll review them, correct mistakes, and then we'll move to **Lesson 5: Functions**.

After Variables + Data Types + Functions, you'll have the basic programming foundation needed to understand **why OOP was created**.


Excellent work! Your understanding of variables and data types is becoming stronger. You are also using more accurate programming vocabulary now, which is a good sign.

Let's review each answer carefully.

---

# Review of Your Answers

## Question 1

**Question:** What is a data type?

**Your answer:**

> A data type is a classification that tells the computer what kind of value a variable contains.

✅ **Excellent!**

This is a technically correct definition.

A simpler version to remember:

> A data type tells Python what kind of thing is stored inside a variable.

Example:

```python
age = 18
```

Python thinks:

> "This is a number."

```python
name = "Ravi"
```

Python thinks:

> "This is text."

---

# Question 2

**Question:**

Difference between:

```python
age = 20
```

and

```python
age = "20"
```

Your answer:

> a number & string

✅ Correct!

Let's make it clearer:

```python
age = 20
```

means:

```
age → Number
```

Python can do calculations:

```python
age + 5
```

Result:

```
25
```

---

```python
age = "20"
```

means:

```
age → Text
```

Python sees characters:

```
"2" and "0"
```

not a mathematical number.

---

# Question 3

```python
name = "Apple"
```

Your answer:

> String

✅ Correct!

Because anything inside quotes is text.

---

# Question 4

```python
price = 99.99
```

Your answer:

> Float

✅ Correct!

A number with decimal points is a float.

Examples:

```python
5.5
10.25
99.99
```

---

# Question 5

```python
is_ready = True

print(is_ready)
```

Your answer:

> True

✅ Correct!

`True` is a Boolean value.

It represents:

```
Yes
```

or

```
No
```

Example:

```python
is_logged_in = True
```

means:

> The user is logged in.

---

# Exercise 1 Review

Your code:

```python
name = "Ravi"
age = 18
height = 5.8
is_student = True
```

✅ Perfect!

You correctly used:

```text
name → String
age → Integer
height → Float
is_student → Boolean
```

This is exactly how a programmer might store information about a person.

If we visualize memory:

```
+----------------+
| name           |
|----------------|
| "Ravi"         |
| String         |
+----------------+

+----------------+
| age            |
|----------------|
| 18             |
| Integer        |
+----------------+

+----------------+
| height         |
|----------------|
| 5.8            |
| Float          |
+----------------+

+----------------+
| is_student     |
|----------------|
| True           |
| Boolean        |
+----------------+
```

---

# Exercise 2 Review

You answered:

```
a = Integer (int)
b = Float (float)
c = String (str)
d = Boolean (bool)
```

✅ Perfect!

Let's connect them with code:

```python
a = 100
```

Whole number → `int`

---

```python
b = 10.5
```

Decimal number → `float`

---

```python
c = "Python"
```

Text → `str`

---

```python
d = False
```

True/False → `bool`

---

# Challenge Review

Code:

```python
x = 10

y = "10"

print(x)
print(y)
```

Your answer:

> It prints number 10
> It prints string 10

✅ Correct!

The output looks similar:

```
10
10
```

But internally they are different.

Memory:

```
x
|
└── 10
    Type: int


y
|
└── "10"
    Type: str
```

A human sees:

```
10
10
```

Python sees:

```
Number
Text
```

---

# Important Lesson Learned 🧠

The same-looking value can have different meanings.

Example:

```python
age = 20
```

means:

> I can calculate with this.

But:

```python
age = "20"
```

means:

> This is just a piece of text.

This difference will become very important when we build programs.

---

# Quick Revision Quiz (Lessons 1–4)

Answer these:

### 1.

What is the difference between a variable and a data type?

---

### 2.

What data type is this?

```python
temperature = 36.5
```

---

### 3.

What data type is this?

```python
is_available = False
```

---

### 4.

What will this print?

```python
name = "Sam"

print(name)
```

---

### 5.

Will this work? Why or why not?

```python
age = "20"

print(age + 5)
```

---

# Flashcards

**Q:** What are the four basic Python data types we learned?

**A:**

* Integer (`int`) → Whole numbers
* Float (`float`) → Decimal numbers
* String (`str`) → Text
* Boolean (`bool`) → True/False

---

**Q:** How do we recognize a string?

**A:** It is usually written inside quotes.

Example:

```python
"Hello"
```

---

**Q:** How do we recognize a float?

**A:** It has a decimal point.

Example:

```python
5.8
```

---

# Summary Table

| Data Type | Meaning        | Example   |
| --------- | -------------- | --------- |
| int       | Whole number   | `25`      |
| float     | Decimal number | `5.5`     |
| str       | Text           | `"Hello"` |
| bool      | True/False     | `True`    |

---

# Progress Tracker

✅ 1. What is programming?
✅ 2. What is a problem and how code solves it?
✅ 3. Variables
✅ 4. Data Types
⏳ 5. Functions
⏳ 6. Why OOP exists
⏳ 7. Objects
⏳ 8. Classes
...and beyond

You have completed the basic building blocks. Next is **Lesson 5: Functions**.

Functions are important because they teach you how to **reuse code**, and later in OOP, methods (object behaviors) are built on the same idea.
