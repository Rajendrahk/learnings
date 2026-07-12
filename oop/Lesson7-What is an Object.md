Great! You have reached the first true OOP concept.

Before today, you learned that OOP combines:

```text
Data + Actions
```

Now we will learn the thing that holds both:

# Lesson 7: What is an Object?

---

# Step 1: Explain the idea in very simple words

An **object** is a thing that exists and has:

1. **Information about itself** (data)
2. **Things it can do** (actions)

In OOP language:

* Information is called **attributes**
* Actions are called **methods**

(We will study attributes and methods deeply in later lessons.)

For now:

```text
Object = Information + Actions
```

---

Think about a real-world object:

A **car**.

A car has information:

```text
Color: Red
Brand: Toyota
Speed: 80 km/h
```

A car can do things:

```text
Start
Stop
Accelerate
Brake
```

So a car is an object.

---

# Step 2: Two Real-Life Examples

## Example 1: Mobile Phone

A mobile phone is an object.

Information:

```text
Brand: Samsung
Color: Black
Battery: 75%
Storage: 128GB
```

Actions:

```text
Call()
SendMessage()
TakePhoto()
Charge()
```

Diagram:

```text
             Mobile Phone

        +----------------+
        | Information    |
        |----------------|
        | Brand          |
        | Battery        |
        | Storage        |
        +----------------+

        +----------------+
        | Actions        |
        |----------------|
        | Call()         |
        | Camera()       |
        | Charge()       |
        +----------------+
```

---

## Example 2: Student

A student is an object.

Information:

```text
Name: Rahul
Age: 18
Roll Number: 101
Marks: 90
```

Actions:

```text
Study()
AttendClass()
TakeExam()
```

Diagram:

```text
              Student

        +----------------+
        | Information    |
        |----------------|
        | Name           |
        | Age            |
        | Marks          |
        +----------------+

        +----------------+
        | Actions        |
        |----------------|
        | Study()        |
        | Exam()         |
        +----------------+
```

---

# Step 3: Object Diagram

A general object looks like this:

```text
              Object

        +----------------+
        |  Data          |
        |----------------|
        | value 1        |
        | value 2        |
        | value 3        |
        +----------------+

        +----------------+
        | Behaviors      |
        |----------------|
        | action 1()     |
        | action 2()     |
        +----------------+
```

---

# Very Important Idea

A **class** is a blueprint.

An **object** is the actual thing created from that blueprint.

Think about a house.

```text
Blueprint
    |
    |
    ▼
Actual House
```

The blueprint is not a house.

It is just a plan.

The actual house is the object.

We will learn classes in the next lesson.

---

# Step 4: Smallest Possible Python Example

Let's create a simple object.

```python
student = "Rahul"
```

Wait!

Is this an OOP object?

❌ No.

This is only a variable storing text.

It is a string object created by Python, but it is not our own custom object.

Now let's create our own object.

```python
class Student:
    pass

student1 = Student()
```

---

# Step 5: Explain Every Line

## Line 1

```python
class Student:
```

This creates a blueprint called `Student`.

Think:

```text
Student Blueprint

+----------------+
|                |
| Empty for now  |
|                |
+----------------+
```

It is not a student yet.

It is only a plan.

---

## Line 2

```python
    pass
```

Means:

> "There is nothing inside yet."

We use it because Python requires the class body to have something.

---

## Line 3

```python
student1 = Student()
```

This creates an actual object.

Now we have:

```text
Student Blueprint

        |
        |
        ▼

Actual Object

student1
```

---

# What Happens in Memory?

Before creating the object:

```text
Memory:

Student
 |
 ▼
Blueprint
```

After:

```python
student1 = Student()
```

Memory:

```text
Memory:

Student
 |
 ▼
Blueprint


student1
 |
 ▼
Object
```

The object gets its own space in memory.

---

# Step 6: Another Example

Imagine a game.

A game has a Player.

A player object:

```text
Player Object

Information:
--------------
Name = "Alex"
Health = 100
Score = 0


Actions:
--------------
jump()
run()
attack()
```

In Python:

```python
class Player:
    pass


player1 = Player()
player2 = Player()
```

Now we have two players.

Diagram:

```text
          Player Blueprint

                |
       ------------------
       |                |
       ▼                ▼

   player1          player2

   Object           Object
```

Both come from the same blueprint.

---

# Why Objects Are Useful

Imagine creating 1,000 students.

Without objects:

```text
student1_name
student1_age
student1_marks

student2_name
student2_age
student2_marks

student3_name
student3_age
student3_marks
```

Very difficult.

With objects:

```text
Student Blueprint

       |
       |
       ▼

student1
student2
student3
...
student1000
```

Much cleaner.

---

# Common Beginner Mistakes

## Mistake 1: Thinking class and object are the same

Wrong:

> "A class is an object."

Correct:

```text
Class = Blueprint

Object = Thing created from blueprint
```

Example:

```text
Cookie recipe = Class

Actual cookie = Object
```

---

## Mistake 2: Thinking the object is just a variable

Example:

```python
name = "Rahul"
```

This stores text.

But:

```python
student1 = Student()
```

creates a Student object.

---

## Mistake 3: Creating a class but no object

Example:

```python
class Car:
    pass
```

You created the blueprint.

But no car exists yet.

You need:

```python
my_car = Car()
```

---

# Step 7: Questions

Answer these in your own words.

### Question 1

What is an object?

---

### Question 2

What two things does an object contain?

---

### Question 3

Which is the object?

A)

```python
class Car:
    pass
```

B)

```python
my_car = Car()
```

---

### Question 4

Explain the difference between a blueprint and the actual thing.

Use any example you like.

---

### Question 5

True or False:

> We can create many objects from one class.

---

# Step 8: Practice Exercise

Imagine a **Library System**.

Choose one object.

Example:

```text
Object: Book
```

Now identify:

### Information it has:

1. ---
2. ---
3. ---

### Actions it can do:

1. ---
2. ---

---

# Small Coding Exercise

Create a class called:

```python
Book
```

For now, leave it empty using `pass`.

Then create one object called:

```python
book1
```

Do not add attributes yet. We will learn that next.

---

Reply with:

1. Answers to the 5 questions.
2. Your Library object design.
3. Your Python code.

I'll review it, and then we'll move to **Lesson 8: What is a Class?** where we go deeper into the blueprint idea.

Excellent work! You are understanding the core OOP idea. Your answers show that you are already connecting **class → object → data/actions**, which is the foundation for everything we will learn next.

Let's review each answer carefully.

---

# Review of Your Answers

## Question 1

**Question:** What is an object?

Your answer:

> Object is the thing created from Class, an instance of the class

✅ **Excellent!**

This is exactly the correct definition.

A simple version:

> An object is a real thing created from a class blueprint.

Example:

```text id="6c8m7y"
Class:
Car Blueprint

        |
        ▼

Objects:
my_car
your_car
family_car
```

Each object is a separate car created from the same design.

---

# Question 2

**Question:** What two things does an object contain?

Your answer:

> Data & actions

✅ Correct!

In OOP language:

```text id="j5p7h4"
Data     = Attributes
Actions  = Methods
```

We will study both deeply later.

---

# Question 3

Which is the object?

A)

```python
class Car:
    pass
```

B)

```python
my_car = Car()
```

Your answer:

> B

✅ Correct!

Why?

Because:

```python id="6c6e6v"
class Car:
```

creates a blueprint.

But:

```python id="7l6d3s"
my_car = Car()
```

creates an actual object.

---

# Question 4

**Blueprint vs Actual Thing**

Your answer:

> Blueprint - Design of the car & actual Thing - Actual Car

✅ Perfect.

Example:

```text id="rj90tj"
Car Design
    |
    |
    ▼
Actual Car
```

The design tells us how to build the car.

The actual car is something we can drive.

---

# Question 5

> We can create many objects from one class.

Your answer:

> True

✅ Correct!

Example:

```python
class Student:
    pass
```

One blueprint:

```text id="4n8xgi"
Student Class
```

Many objects:

```text id="7m3r1c"
student1
student2
student3
student4
```

---

# Library Object Design Review

Your object:

> Book

Good choice! A book is a perfect object for a library system.

---

## Information (Attributes)

You wrote:

* Author
* Pages
* Title
* Chapters

✅ Good.

A slightly more complete Book object:

```text id="1z8qxn"
Book

Attributes:
-----------
Title
Author
Pages
ISBN
Category
```

---

## Actions (Methods)

You wrote:

* open
* close
* turn
* issue

Good thinking.

Let's adjust them for a library system:

```text id="kmz2jb"
Methods:
-----------
open_book()
close_book()
issue_book()
return_book()
```

Why?

Because in software design, we think about actions the system needs.

A user doesn't usually ask a book to "turn pages"; they turn pages themselves. But the library system does need to issue and return books.

Your thinking is still correct.

---

# Coding Exercise Review

You wrote:

```python
class Book:
pass:
```

Almost there! Just a few Python syntax fixes.

Correct:

```python
class Book:
    pass
```

Two important things:

## 1. Indentation

Python needs the inside of the class to be indented:

Wrong:

```python
class Book:
pass
```

Correct:

```python
class Book:
    pass
```

---

## 2. Colon placement

You wrote:

```python
pass:
```

The colon belongs after the class name:

Correct:

```python
class Book:
    pass
```

---

You wrote:

```python
book1.Book
```

Almost!

To create an object, we use parentheses:

Correct:

```python
book1 = Book()
```

Let's break it down:

```text id="a7m5up"
Book
 |
 |  create an object
 ▼

book1
```

---

# Final Correct Code

```python
class Book:
    pass

book1 = Book()
```

What happens:

```text id="x8m5yq"
Step 1:

Create Book blueprint


Step 2:

Create book1 object from Book


Memory:

Book
 |
 ▼
Blueprint


book1
 |
 ▼
Book Object
```

---

# Very Important Progress

You now understand:

```text id="m7w2dd"
Class
  |
  | creates
  ▼
Object
  |
  | contains
  ▼
Attributes + Methods
```

This is the heart of OOP.

---

# Quick Revision Quiz (Lessons 6 & 7)

Answer these:

### 1.

A class is like a ______.

A) Real object
B) Blueprint
C) Function

---

### 2.

A real student created from a Student class is called what?

---

### 3.

Identify the object:

```python
class Phone:
    pass

my_phone = Phone()
```

---

### 4.

What is the difference between:

```python
Car
```

and

```python
my_car = Car()
```

---

### 5.

A Bank Account object has:

Information:

* Account number
* Balance

Actions:

* Deposit
* Withdraw

Which are attributes and which are methods?

---

# Next Lesson Preview

## Lesson 8: What is a Class?

You already know the basic idea.

Next we will go deeper:

* Why classes are called blueprints
* How classes are designed
* Creating better Python classes
* How classes help us build real applications
* More memory diagrams

Then we will combine:

```text
Class + Object + Attributes + Methods
```

to start building real OOP programs.

Excellent! 🎉 You have understood the foundation of OOP very well. Your answers are all correct. Let's review them carefully and strengthen the concepts.

---

# Review of Quick Revision Quiz

## Question 1

**A class is like a ______.**

Options:

A) Real object
B) Blueprint
C) Function

Your answer:

> B

✅ Correct!

A class is a blueprint.

Example:

```text
id="6u8y4m"
House Blueprint (Class)

        |
        ▼

Actual House (Object)
```

The blueprint describes how to make houses, but it is not a house itself.

---

# Question 2

**A real student created from a Student class is called what?**

Your answer:

> Object

✅ Correct!

More specifically:

> It is an object (also called an instance) of the class.

Example:

```python
id="n8d1xw"
class Student:
    pass

student1 = Student()
```

Here:

```text
Student  → Class
student1 → Object
```

---

# Question 3

Identify the object:

```python
id="p5v8j2"
class Phone:
    pass

my_phone = Phone()
```

Your answer:

> my_phone

✅ Correct!

Let's see why:

```text
id="m9q3zx"
Phone

↓
Blueprint


my_phone

↓
Actual Object
```

`Phone` describes what a phone object should look like.

`my_phone` is the created phone.

---

# Question 4

Difference between:

```python
id="x8w2ak"
Car
```

and

```python
id="c4j7pk"
my_car = Car()
```

Your answer:

> car is just a name, my_car is the object

🟡 Almost correct. Let's make it more precise.

`Car` is not just a name. It is the **class name (blueprint)**.

`my_car` is the **object created from that blueprint**.

Think:

```text
id="w4z9cp"
Car
 |
 |  creates
 ▼
my_car
```

Example:

```text
Class:
Car Blueprint

Object:
My red Toyota car
```

---

# Question 5

Bank Account:

Information:

* Account number
* Balance

Actions:

* Deposit
* Withdraw

Your answer:

> information is the attribute and Actions are Methods

✅ Perfect!

OOP terminology:

```text
id="j2y8pm"
Information
      |
      ▼
Attributes


Actions
      |
      ▼
Methods
```

So:

```text
id="a7r5qn"
BankAccount

Attributes:
- account_number
- balance

Methods:
- deposit()
- withdraw()
```

---

# Your Current OOP Understanding

You now understand this structure:

```text
id="o3m8zy"
             CLASS

          Blueprint

              |
              |
              ▼

            OBJECT

        Real created thing

              |
              |
      -----------------

      Attributes     Methods

       Data          Actions
```

Example:

```text
id="v7k2md"
          Student Class

              |
              ▼

          Rahul Object

              |
      -----------------

      name = Rahul     study()
      age = 18         attend_class()
```

---

# Small Thinking Exercise Before Lesson 8

Let's prepare your brain for **Classes**.

Imagine you are creating a **Car Manufacturing System**.

Answer:

## 1. What would be the class name?

Example:

```text
Class: _______
```

---

## 2. What attributes would every car have?

Write 3:

1. ---
2. ---
3. ---

---

## 3. What methods can every car perform?

Write 3:

1. _______()
2. _______()
3. _______()

---

## 4. If we create:

```python
id="r2v6kx"
car1 = Car()
car2 = Car()
```

Are `car1` and `car2` the same object or two different objects?

Explain why.

---

After this, we will move to:

# Lesson 8: What is a Class?

We will learn:

* How to design a class
* Why classes are useful
* How Python stores classes in memory
* How classes become templates for many objects
* Creating our first meaningful class with attributes and methods 🚗

Excellent! You are thinking like an OOP designer now. Your answers are mostly correct. Let's review and improve them.

---

# Review: Car Manufacturing System

## Question 1

**What would be the class name?**

Your answer:

> car

✅ Correct idea.

In Python, class names are usually written with the first letter capitalized.

Better:

```python
Car
```

Why?

Because a class represents a general blueprint.

Example:

```text id="4x8m2a"
Car Class

   |
   | creates
   ▼

car1
car2
car3
```

---

# Question 2

**What attributes would every car have?**

Your answer:

> color, brand name

✅ Correct!

You provided two good attributes.

We need one more:

Example:

```text id="8p2l3z"
Car Attributes:

- color
- brand_name
- model
```

Other examples:

```text id="v4c7qm"
speed
fuel_type
price
```

Attributes describe the car.

---

# Question 3

**What methods can every car perform?**

Your answer:

> start(), stop()

✅ Correct!

You identified behaviors.

A more complete list:

```text id="u1m8k9"
Car Methods:

- start()
- stop()
- accelerate()
```

Methods are actions the object can perform.

---

# Question 4

Given:

```python id="b5q0xm"
car1 = Car()
car2 = Car()
```

Are they the same object?

Your answer:

> two different objects

✅ Correct!

Very important concept.

Even though they come from the same class:

```text id="c8n2ww"
          Car Class
       (Blueprint)

          |
     -------------
     |           |
     ▼           ▼

   car1        car2

  Object      Object
```

They are separate objects.

Think about a car factory:

```text id="m3z7hj"
Car Design

    |
    |
    ▼

Red Toyota Car     Blue Toyota Car

Different cars, same design
```

---

# Small Correction

You wrote:

> brand name

In programming, we usually avoid spaces in variable names.

Instead of:

```python
brand name
```

we write:

```python
brand_name
```

Python uses underscores for multi-word names.

Examples:

```python
car_color
phone_number
student_name
```

---

# Your OOP Thinking Score ⭐

You are now able to identify:

✅ Classes
✅ Objects
✅ Attributes
✅ Methods
✅ Object differences

This is the foundation needed before writing bigger OOP programs.

---

# Lesson 8: What is a Class?

Now we move deeper into classes.

A class is the **blueprint that creates objects**.

Next lesson we will learn:

1. What exactly a class stores
2. How classes are designed
3. How to create useful classes in Python
4. How a class differs from an object
5. How Python remembers classes in memory

We will also create our first proper class:

```python
class Car:
    ...
```

and slowly build it into a real object. 🚗
