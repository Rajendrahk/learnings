Awesome! Welcome to **Lesson 10: Attributes (Properties)**.

This is one of the **most important topics in OOP**. Once you understand attributes, you'll see how objects can store their own information.

We'll follow the learning structure you requested.

---

# Lesson 10: Attributes (Properties)

## Step 1: Explain the idea in very simple words

Imagine you have three students.

Each student has:

* Name
* Age
* Grade

Although all of them are students, their information is different.

For example:

| Student   | Name  | Age | Grade |
| --------- | ----- | --- | ----- |
| Student 1 | Rahul | 20  | A     |
| Student 2 | Priya | 19  | B     |
| Student 3 | Amit  | 21  | A     |

The **name**, **age**, and **grade** are called **attributes** (or **properties**).

### Simple definition

> **An attribute is a piece of information that describes an object.**

Think of it like an adjective describing something.

Examples:

* A car has a **color**
* A phone has a **brand**
* A dog has a **name**
* A bank account has a **balance**

These are all attributes.

---

# Step 2: Two Real-Life Examples

## Example 1: Car 🚗

Imagine your car.

It has:

* Color = Red
* Brand = Toyota
* Year = 2023

These describe the car.

```text
Car

Color : Red
Brand : Toyota
Year  : 2023
```

Here,

* Color → Attribute
* Brand → Attribute
* Year → Attribute

---

## Example 2: Mobile Phone 📱

Your phone has:

* Brand = Samsung
* RAM = 8 GB
* Storage = 128 GB
* Battery = 5000 mAh

These are all attributes.

Notice something:

Your friend's phone may have different values.

Both are phones, but their attributes are different.

---

# Step 3: Simple Diagram

```text
                 Phone Class
                     |
         --------------------------
         |                        |
         ↓                        ↓

      phone1                  phone2

 Brand : Samsung          Brand : Apple
 Color : Black            Color : White
 RAM   : 8GB              RAM   : 6GB
```

The class says:

> "A phone should have these attributes."

Each object stores **its own values**.

---

# Step 4: Smallest Possible Code Example

```python
class Student:
    pass


student1 = Student()

student1.name = "Rahul"
student1.age = 20

print(student1.name)
print(student1.age)
```

---

# Step 5: Explain Every Line

## Line 1

```python
class Student:
```

Create a blueprint called `Student`.

---

## Line 2

```python
pass
```

Nothing inside the class yet.

---

## Line 5

```python
student1 = Student()
```

Create one student object.

Memory:

```text
Student Class
      |
      |
      ↓

student1
```

---

## Line 7

```python
student1.name = "Rahul"
```

We're creating an attribute called `name` **inside this object**.

Memory becomes:

```text
student1

name = Rahul
```

Notice:

The class didn't store "Rahul".

The object did.

---

## Line 8

```python
student1.age = 20
```

Now the object has another attribute.

Memory:

```text
student1

name = Rahul
age  = 20
```

---

## Line 10

```python
print(student1.name)
```

Python looks inside `student1`.

Finds:

```
name = Rahul
```

Prints:

```text
Rahul
```

---

## Line 11

```python
print(student1.age)
```

Output:

```text
20
```

---

# Step 6: Another Example

Let's create two cars.

```python
class Car:
    pass


car1 = Car()
car2 = Car()

car1.color = "Red"
car2.color = "Blue"

print(car1.color)
print(car2.color)
```

Output:

```text
Red
Blue
```

Memory:

```text
Car Class
      |
------------------------
|                      |
↓                      ↓

car1                 car2

color=Red           color=Blue
```

Each object has its own `color`.

---

# Important Observation

Look at this line:

```python
car1.color = "Red"
```

Break it into parts:

```
car1
```

Which object?

↓

```
color
```

Which attribute?

↓

```
=
```

Store a value.

↓

```
"Red"
```

The value.

Think of it like filling in a form.

---

# Common Beginner Mistakes

## Mistake 1

```python
print(car1.colour)
```

But you created:

```python
car1.color
```

❌ Error.

Python treats `color` and `colour` as different names.

---

## Mistake 2

```python
print(car2.color)
```

without first doing:

```python
car2.color = "Blue"
```

❌ Error.

Why?

Because `car2` doesn't have a `color` attribute yet.

---

## Mistake 3

Thinking attributes belong to all objects automatically.

Example:

```python
car1.color = "Red"
```

does **not** mean

```text
car2.color = "Red"
```

Each object has its own attributes.

---

# Memory Diagram

```text
               Car Class

                    |

        ------------------------

        |                      |

      car1                  car2

 color = Red          color = Blue
```

The class created the objects.

The objects store the values.

---

# Step 7: Questions

Answer these before we move on.

### Question 1

What is an **attribute** in your own words?

---

### Question 2

Which of these are attributes of a book?

A. Title

B. Read()

C. Author

D. Pages

---

### Question 3

Predict the output:

```python
class Dog:
    pass

dog1 = Dog()
dog2 = Dog()

dog1.name = "Buddy"
dog2.name = "Max"

print(dog1.name)
print(dog2.name)
```

---

### Question 4

Where is `"Buddy"` stored?

A. Inside the `Dog` class

B. Inside the `dog1` object

C. Inside every object

---

### Question 5

If you write:

```python
car1.color = "Red"
```

Does `car2.color` automatically become `"Red"`?

Why?

---

# Step 8: Practice Exercise

Create a class called `Laptop`.

Then create **two objects**:

* `laptop1`
* `laptop2`

Add these attributes:

For `laptop1`

* brand = "Dell"
* ram = 16

For `laptop2`

* brand = "HP"
* ram = 8

Finally print:

* `laptop1.brand`
* `laptop2.brand`
* `laptop1.ram`
* `laptop2.ram`

**Don't use a constructor (`__init__`) yet.** We'll learn that in Lesson 12.

---

## 📌 A Small Thought Before You Code

You've already noticed that we keep writing:

```python
laptop1.brand = "Dell"
laptop1.ram = 16
```

Imagine a `Laptop` has **20 attributes**.

Would it be convenient to set them one by one after creating the object?

Keep that question in mind. The answer will lead us naturally to **constructors (`__init__`)** in a later lesson.

For now, reply with:

1. Your answers to the 5 questions.
2. Your Python code for the `Laptop` exercise.

I'll review your work, point out any mistakes, and then we'll continue.


Fantastic! 👏 You're starting to **reason** about OOP instead of just remembering definitions. That's exactly what I want to see.

Let's review everything carefully.

---

# Review of Questions

## Q1. What is an attribute?

Your answer:

> Attributes are properties of the object.

✅ Correct.

I would expand it slightly:

> **An attribute is a property or piece of information that belongs to an object.**

Examples:

```text
Student
--------
name
age
grade
```

Here:

* `name` → Attribute
* `age` → Attribute
* `grade` → Attribute

---

## Q2. Which of these are attributes of a book?

Options:

* A. Title
* B. Read()
* C. Author
* D. Pages

Your answer:

> Read()

❌ Not quite.

This is a very common beginner mistake, so don't worry.

Let's think about it.

Imagine a real book.

It has:

* Title = "Python Basics"
* Author = "John"
* Pages = 350

These are **information about the book**.

So they are **attributes**.

Now think about **Read()**.

Is it information?

No.

It is **something the book can do** (or more accurately, an action associated with it).

That makes it a **method**, not an attribute.

### Correct answer:

✅ A. Title

✅ C. Author

✅ D. Pages

❌ B. Read()

---

### A Simple Trick

Ask yourself:

> "Is this **information** about the object?"

If yes → **Attribute**

If it's something the object **does** → **Method**

Examples:

```text
Car

Color        ← Attribute
Brand        ← Attribute
Start()      ← Method
Stop()       ← Method
```

---

## Q3. Predict the output

Your answer:

> Buddy & Max

✅ Correct.

Output:

```text
Buddy
Max
```

---

## Q4. Where is `"Buddy"` stored?

Your answer:

> Inside dog1 object

✅ Perfect.

Memory:

```text
Dog Class
      |
      |
 ---------------------
 |                   |
 ↓                   ↓

dog1              dog2

name=Buddy      name=Max
```

---

## Q5.

Will `car2.color` automatically become `"Red"`?

Your answer:

> No, because you have assigned only for car1, each object will have its own properties.

✅ Excellent explanation.

You now understand one of the most important principles of OOP:

> **Each object has its own attributes and values.**

---

# Practice Exercise Review

You wrote:

```python
class Laptop():
	pass
	
laptop1.brand = "Dell"
laptop1.ram = 16

laptop2.brand = "HP"
laptop1.ram = 8

print(laptop1.brand)
print(laptop2.brand)
print(laptop1.ram)
print(laptop2.ram)
```

I can see you understand **attributes**, but there are **three mistakes**.

Let's find them together.

---

## Mistake 1: You forgot to create the objects

Before using `laptop1`, Python needs to know what it is.

Right now, `laptop1` doesn't exist.

You need to create the objects first.

**Hint:** Think back to Lesson 9.

What line do we write after defining a class to create an object?

It starts like this:

```python
laptop1 = ...
```

---

## Mistake 2: `laptop2` was never created

You used:

```python
laptop2.brand = "HP"
```

But where did `laptop2` come from?

It also needs to be created.

---

## Mistake 3: Small typing mistake

You wrote:

```python
laptop2.brand = "HP"
laptop1.ram = 8
```

Look carefully.

Which laptop should have `ram = 8`?

It should be:

```python
laptop2.ram = 8
```

---

# 🎯 Your Challenge (Don't Scroll Further Yet)

Try fixing the code yourself.

You need to:

1. Create `laptop1`.
2. Create `laptop2`.
3. Assign the correct attributes.
4. Print the values.

Take a minute and write the corrected version.

---

## 💡 One Small Preview

You may be wondering:

```python
laptop1.brand = "Dell"
laptop1.ram = 16
```

What if a laptop has:

* brand
* ram
* storage
* processor
* battery
* screen size
* operating system
* graphics card

Writing all of those after creating every object would become repetitive.

That's exactly why Python has **constructors (`__init__`)**, which we'll learn in Lesson 12.

But before we get there, we'll first understand **methods (behaviors)**, because objects don't just **have data**—they also **do things**.

---

## ⭐ Progress Report

| Topic           | Status                                                                |
| --------------- | --------------------------------------------------------------------- |
| Class           | ✅ Mastered                                                            |
| Object          | ✅ Mastered                                                            |
| Class vs Object | ✅ Mastered                                                            |
| Attributes      | ✅ Almost mastered (just one confusion between attributes and methods) |

You're progressing really well. The only concept to reinforce is:

* **Attributes = information/data**
* **Methods = actions/behaviors**

Once you correct the `Laptop` code, we'll move on with confidence.


Excellent! 🎉 This is **100% correct**.

Let's go through it line by line, just like a software developer would.

---

# Your Code

```python
class Laptop():
    pass

# create objects
laptop1 = Laptop()
laptop2 = Laptop()

laptop1.brand = "Dell"
laptop1.ram = 16

laptop2.brand = "HP"
laptop2.ram = 8

print(laptop1.brand)
print(laptop2.brand)
print(laptop1.ram)
print(laptop2.ram)
```

---

# Line-by-Line Explanation

## 1. Create the class

```python
class Laptop():
```

You are creating a **blueprint** named `Laptop`.

At this moment, there are **no actual laptops**.

Think of it like an architect drawing a laptop design.

---

## 2. `pass`

```python
pass
```

The class doesn't contain anything yet.

Python allows this by using `pass`.

---

## 3. Create the first object

```python
laptop1 = Laptop()
```

Python creates a new `Laptop` object in memory.

Memory:

```text
Laptop Class
      |
      |
      ↓
  laptop1
```

---

## 4. Create the second object

```python
laptop2 = Laptop()
```

Now memory becomes:

```text
Laptop Class
      |
-------------------
|                 |
↓                 ↓

laptop1       laptop2
```

Notice:

* Same class
* Two different objects

---

## 5. Add attributes to `laptop1`

```python
laptop1.brand = "Dell"
```

Memory:

```text
laptop1

brand = Dell
```

Then:

```python
laptop1.ram = 16
```

Memory:

```text
laptop1

brand = Dell
ram = 16
```

---

## 6. Add attributes to `laptop2`

```python
laptop2.brand = "HP"
laptop2.ram = 8
```

Memory:

```text
laptop2

brand = HP
ram = 8
```

Now the complete picture is:

```text
                 Laptop Class
                      |
          --------------------------
          |                        |
          ↓                        ↓

      laptop1                 laptop2

   brand = Dell            brand = HP
   ram   = 16              ram   = 8
```

---

## 7. Print the values

```python
print(laptop1.brand)
```

Python looks inside `laptop1` and finds:

```
brand = "Dell"
```

Output:

```
Dell
```

The same process happens for the remaining `print()` statements.

Final output:

```text
Dell
HP
16
8
```

---

# 🧠 What Happens in Memory?

This is a question beginners often overlook, but understanding it will make OOP much easier.

When Python runs:

```python
laptop1 = Laptop()
```

It creates a new object in memory.

Think of memory as a collection of boxes.

Initially:

```text
laptop1

(empty)
```

After:

```python
laptop1.brand = "Dell"
```

the box becomes:

```text
laptop1

brand
------
Dell
```

After:

```python
laptop1.ram = 16
```

it becomes:

```text
laptop1

brand ---> Dell
ram   ---> 16
```

The same happens for `laptop2`.

Each object has its **own box**.

---

# 🎯 One Important Question

Look at this code:

```python
laptop1.brand = "Dell"
laptop2.brand = "HP"

laptop1.brand = "Lenovo"
```

What will happen?

Will it change:

* Only `laptop1`?
* Only `laptop2`?
* Both?

### Think before answering.

---

# 🚀 A Better Way Is Coming

Right now, we're doing this:

```python
laptop1 = Laptop()

laptop1.brand = "Dell"
laptop1.ram = 16
```

Imagine creating **500 laptops**.

You'd have to repeat these assignments over and over.

That's tedious.

A better way would be:

```python
laptop1 = Laptop("Dell", 16)
laptop2 = Laptop("HP", 8)
```

Python can do that—and it's much cleaner.

To make that possible, we'll learn **constructors (`__init__`)** in Lesson 12.

But before that, there's one missing piece:

An object doesn't just **have attributes**.

It also **performs actions**.

For example:

* A car can **start**.
* A bank account can **deposit money**.
* A student can **study**.
* A phone can **make a call**.

Those actions are called **methods**.

---

# 📚 Quick Revision (Lessons 9 & 10)

| Concept   | Meaning                         | Example                                |
| --------- | ------------------------------- | -------------------------------------- |
| Class     | Blueprint                       | `Laptop`                               |
| Object    | Real thing created from a class | `laptop1`                              |
| Attribute | Data that belongs to an object  | `brand`, `ram`                         |
| Method    | Action an object performs       | `start()`, `deposit()` *(coming next)* |

---

## 🧠 Memory Trick

When you see an object, ask two questions:

1. **What does it have?** → Attributes (data)
2. **What can it do?** → Methods (behavior)

Example:

```text
Dog

Has:
✔ name
✔ age
✔ color

Can:
✔ bark()
✔ eat()
✔ run()
```

The first list is **attributes**.

The second list is **methods**.

---

You're building a solid foundation. I especially like that you're fixing your own mistakes after hints—that's exactly how strong programmers learn.

**Next lesson:** **Lesson 11 – Methods (Behaviors)**, where you'll learn how to make objects *do* things, not just *store* information.
