# Lesson 13: The `self` Keyword in Python

> **Goal:** Understand what `self` is, why Python needs it, and how it connects methods to the correct object.

---

# Step 1: Explain the Idea in Very Simple Words

Imagine you are in a classroom with three students:

* Raj
* Priya
* Amit

The teacher says:

> **"Raise your hand."**

Who raises the hand?

Each student raises **their own** hand, not someone else's.

In Python, `self` means:

> **"This particular object."**

Whenever an object calls a method, Python automatically tells the method **which object is calling it**. That object is received as `self`.

Think of `self` as saying:

> **"Me"** or **"Myself."**

---

## Why Do We Need `self`?

Suppose you have two cars:

```text
Car 1
Brand = Toyota

Car 2
Brand = Honda
```

If you ask:

```text
Start the engine.
```

How does Python know **which car** should start?

Answer:

The object itself is passed as `self`.

```text
Toyota.start()

↓

self = Toyota object
```

```text
Honda.start()

↓

self = Honda object
```

Without `self`, Python wouldn't know which object's data to use.

---

# Step 2: Two Real-Life Examples

## Example 1: Mobile Phone

You own a Samsung phone.

Your friend owns an iPhone.

When you open your gallery:

* You see **your** photos.
* Your friend sees **their** photos.

Each phone accesses **its own data**.

`self` means:

> "Use **my** data."

---

## Example 2: Bank Account

Imagine two bank accounts.

```text
Account 1
Balance = ₹10,000

Account 2
Balance = ₹25,000
```

When Account 1 checks its balance:

```text
self.balance

↓

₹10,000
```

When Account 2 checks its balance:

```text
self.balance

↓

₹25,000
```

Same code.

Different object.

Different result.

---

# Step 3: Simple Diagram

```text
          Laptop Class
               │
      ┌────────┴────────┐
      │                 │
      ▼                 ▼

 Laptop1           Laptop2

 Brand=Dell        Brand=HP

      │                 │
      ▼                 ▼

 show_brand()      show_brand()

      │                 │
      ▼                 ▼

self = Laptop1    self = Laptop2
```

---

# Step 4: Smallest Possible Code Example

```python
class Laptop:

    def __init__(self, brand):
        self.brand = brand

    def show_brand(self):
        print(self.brand)


laptop1 = Laptop("Dell")
laptop2 = Laptop("HP")

laptop1.show_brand()
laptop2.show_brand()
```

Output

```text
Dell
HP
```

---

# Step 5: Explain Every Line

## Line 1

```python
class Laptop:
```

Creates the blueprint.

---

## Line 3

```python
def __init__(self, brand):
```

`self` refers to the object being created.

`brand` is the value passed by the user.

---

## Line 4

```python
self.brand = brand
```

Stores the value inside the object.

If we create:

```python
Laptop("Dell")
```

then Python does:

```text
self.brand = "Dell"
```

---

## Line 6

```python
def show_brand(self):
```

Again, `self` refers to the object calling the method.

---

## Line 7

```python
print(self.brand)
```

Print the brand stored inside **this object**.

---

## Line 10

```python
laptop1 = Laptop("Dell")
```

Creates first object.

---

## Line 11

```python
laptop2 = Laptop("HP")
```

Creates second object.

---

## Line 13

```python
laptop1.show_brand()
```

Python secretly changes this into:

```python
Laptop.show_brand(laptop1)
```

Notice?

Python automatically passes:

```text
self = laptop1
```

---

Similarly,

```python
laptop2.show_brand()
```

becomes

```python
Laptop.show_brand(laptop2)
```

Now

```text
self = laptop2
```

This is the most important idea of today's lesson.

---

# Step 6: Another Example

```python
class Student:

    def __init__(self, name):
        self.name = name

    def greet(self):
        print("Hello,", self.name)


s1 = Student("Raj")
s2 = Student("Anita")

s1.greet()
s2.greet()
```

Output

```text
Hello, Raj
Hello, Anita
```

The same `greet()` method works for both students because `self` points to the correct object.

---

# What Happens in Memory?

After:

```python
s1 = Student("Raj")
s2 = Student("Anita")
```

Memory:

```text
s1                     s2

│                      │

▼                      ▼

+-----------+      +-----------+
| name=Raj  |      | name=Anita|
+-----------+      +-----------+
```

When:

```python
s1.greet()
```

```text
self

│

▼

+-----------+
| name=Raj  |
+-----------+
```

When:

```python
s2.greet()
```

```text
self

│

▼

+-------------+
| name=Anita  |
+-------------+
```

---

# Is `self` a Keyword?

Surprisingly...

**No!**

Python doesn't treat `self` as a reserved keyword.

You could write:

```python
def __init__(myself, name):
    myself.name = name
```

It works.

But...

**Never do this.**

The Python community always uses `self`.

Using another name will confuse everyone reading your code.

---

# Common Beginner Mistakes

## Mistake 1: Forgetting `self`

Wrong:

```python
class Car:

    def show():
        print("Hello")
```

Calling:

```python
car.show()
```

Error:

```text
TypeError:
show() takes 0 positional arguments but 1 was given
```

Why?

Python automatically passes the object, but your method doesn't accept it.

Correct:

```python
def show(self):
```

---

## Mistake 2: Using `brand` Instead of `self.brand`

Wrong:

```python
def show_brand(self):
    print(brand)
```

Error:

```text
NameError
```

Correct:

```python
print(self.brand)
```

Because the brand belongs to the object.

---

## Mistake 3: Confusing `brand` with `self.brand`

```python
brand
```

Temporary parameter.

```python
self.brand
```

Object attribute.

Remember:

```text
brand
↓

Input

self.brand

↓

Stored inside object
```

---

# Memory Trick 🧠

Think of `self` as saying:

> **"Me"**

```text
self.name

↓

My name

self.age

↓

My age

self.salary

↓

My salary
```

Whenever you see `self`, mentally read it as:

> **"This object."**

---

# Step 7: Check Your Understanding

Answer these without looking back.

### Q1

What does `self` represent in Python?

---

### Q2

Who passes the `self` argument?

* A. Programmer
* B. Python automatically

---

### Q3

What is the difference between:

```python
name
```

and

```python
self.name
```

---

### Q4

What does Python secretly do when you write:

```python
student.greet()
```

---

### Q5

True or False

`self` is a reserved keyword in Python.

---

# Step 8: Practice Exercise

Create a class called `Employee`.

### Requirements

1. Constructor accepts:

* `name`
* `salary`

2. Store them using `self`.

3. Create a method named `display()` that prints:

```text
Employee Name: Raj
Salary: 50000
```

4. Create two employees:

```text
Employee 1

Raj
50000

Employee 2

Anita
65000
```

5. Call:

```python
emp1.display()
emp2.display()
```

---

## 💡 Hints (Don't Read Unless You Need Them)

### Hint 1

Start with:

```python
class Employee:
```

---

### Hint 2

Your constructor:

```python
def __init__(self, name, salary):
```

---

### Hint 3

Store the values:

```python
self.name = name
self.salary = salary
```

---

### Hint 4

Inside `display()`:

```python
print("Employee Name:", self.name)
print("Salary:", self.salary)
```

---

## What We'll Do Next

Reply with:

1. Your answers to the **5 questions**.
2. Your code for the **Employee** exercise.

I'll review both carefully, explain any mistakes if there are any, and only then we'll move to **Lesson 14: Encapsulation**, where you'll learn how to protect an object's data from accidental misuse.
