# Lesson 9: Difference Between Class and Object in Python

Great. We will start from **Class vs Object**, assuming you already have a basic idea that objects and classes exist. Today we will make the difference crystal clear.

---

# Step 1: Explain the idea in very simple words

Imagine you want to build many cars.

Before making cars, a company creates a **design/blueprint**.

The blueprint says:

* A car has a color
* A car has a model name
* A car can start
* A car can stop

The blueprint itself is **not a real car**.

It is only an instruction sheet.

```
Blueprint
    |
    |
    ↓
Creates real cars
```

In OOP:

* **Class = Blueprint / Design**
* **Object = Real thing created from that blueprint**

A class describes what something should have and what it can do.

An object is the actual thing that exists in memory.

---

## Simple comparison

| Real World          | OOP    |
| ------------------- | ------ |
| House blueprint     | Class  |
| Actual house        | Object |
| Recipe              | Class  |
| Actual cake         | Object |
| Mobile phone design | Class  |
| Your actual phone   | Object |

---

# Step 2: Two real-life examples

## Example 1: Mobile phones

A company designs a phone model.

The design contains:

```
Phone Model
------------
Color
Storage
Camera
Battery
Call()
TakePhoto()
```

This is like a **class**.

Then millions of phones are created:

```
My iPhone
Your iPhone
Friend's iPhone
```

Each phone is an **object**.

They follow the same design but are separate things.

---

## Example 2: Students

A school needs student records.

The school decides every student should have:

```
Student
---------
Name
Age
Roll number
Study()
Attend class()
```

This is the class.

Then:

```
Student Class
      |
      |
      +------> Rahul object
      |
      +------> Priya object
      |
      +------> Amit object
```

Each student object has its own information.

---

# Step 3: Simple diagram

```
             CLASS
        (Blueprint)

        Student
       ----------
       name
       age
       study()


            |
            |
            ↓


          OBJECTS
     (Real Students)


    Rahul
    -----
    age = 12


    Priya
    -----
    age = 13


    Amit
    -----
    age = 12
```

The class is one idea.

Objects are the actual copies.

---

# Step 4: Smallest possible Python example

Let's create a Student class.

```python
class Student:
    pass


student1 = Student()
student2 = Student()
```

---

# Step 5: Explain every line

## Line 1

```python
class Student:
```

We are creating a class called `Student`.

Think:

"Create a blueprint for students."

---

## Line 2

```python
pass
```

`pass` means:

"Do nothing for now."

Python needs something inside the class, so we use `pass` when we have not added details yet.

---

## Line 4

```python
student1 = Student()
```

We create an object from the Student class.

Meaning:

"Make one real student using the Student blueprint."

Memory looks like:

```
Student Class
      |
      |
      ↓

student1 Object
```

---

## Line 5

```python
student2 = Student()
```

We create another object.

Now memory has:

```
Student Class
      |
      +------ student1
      |
      +------ student2
```

Important:

`student1` and `student2` are different objects.

Changing one will not automatically change the other.

---

# Step 6: Another example

Let's create a simple Car.

```python
class Car:
    pass


car1 = Car()
car2 = Car()
```

Here:

```
Car
(Class)
 |
 |
 +------ car1
 |
 +------ car2
```

The class is the idea of a car.

The objects are actual cars.

---

Now let's add information:

```python
class Car:
    pass


car1 = Car()
car1.color = "Red"

car2 = Car()
car2.color = "Blue"


print(car1.color)
print(car2.color)
```

Output:

```
Red
Blue
```

Why?

Because each object has its own data.

Memory:

```
Car Class

     |
     |
     +----------------+
                      |
                      |

                car1 Object
                color = Red


                car2 Object
                color = Blue
```

---

# Important Difference: Class vs Object

| Class                               | Object                      |
| ----------------------------------- | --------------------------- |
| Blueprint                           | Real thing                  |
| Design                              | Actual item                 |
| Created once                        | Many objects can be created |
| Does not represent a specific thing | Represents a specific thing |
| Example: Car design                 | Example: My red Toyota      |

---

# Common Beginner Mistakes

## Mistake 1:

Thinking a class is an object.

Wrong:

```
Car class = my car
```

Correct:

```
Car class = design of cars

My Toyota = object
```

---

## Mistake 2:

Thinking objects are copies of code.

They are not.

The class contains the instructions.

Objects contain their own data.

---

# Memory Trick

Remember:

**C = Class = Construction plan**

**O = Object = One real thing**

Example:

```
Class → Cookie cutter

Object → Actual cookies
```

One cookie cutter can make many cookies.

---

# Step 7: Questions (Answer these before moving ahead)

### Question 1:

A blueprint of a house is an example of what?

A) Object
B) Class

---

### Question 2:

Your personal mobile phone is an example of what?

A) Class
B) Object

---

### Question 3:

Can one class create many objects?

Yes or No?

Explain why.

---

### Question 4:

Look at this code:

```python
class Dog:
    pass

dog1 = Dog()
dog2 = Dog()
```

How many classes are created?

How many objects are created?

---

### Question 5:

Explain the difference between a class and an object using your own real-life example.

---

# Step 8: Practice Exercise

Create a class called `Book`.

For now, do not add any properties.

Your goal:

1. Create the class.
2. Create two book objects.

Example idea:

```
Book
 |
 +---- book1
 |
 +---- book2
```

Do not worry about adding titles or authors yet. We will learn that in the next lesson: **Attributes (Properties).**

---

Reply with:

1. Answers to the 5 questions
2. Your small Python exercise code

I will review it, correct mistakes, and only then move to the next topic.


Great work. You understood the main idea of **Class vs Object** very well. Let's review each answer carefully.

---

# Review of Questions

## Q1. A blueprint of a house is an example of what?

Your answer:

> Class

✅ Correct.

A blueprint is a plan that tells us how to create houses.

In OOP:

```
House Blueprint = Class
Actual House = Object
```

---

## Q2. Your personal mobile phone is an example of what?

Your answer:

> Object

✅ Correct.

Your phone is a real, existing thing.

Example:

```
MobilePhone Class
        |
        |
        ↓
My Samsung Phone Object
```

---

## Q3. Can one class create many objects?

Your answer:

> Yes

✅ Correct.

A class is like a factory design.

One design can create many things.

Example:

```
Car Class
   |
   +---- Car Object 1 (Red Toyota)
   |
   +---- Car Object 2 (Blue Honda)
   |
   +---- Car Object 3 (Black BMW)
```

---

## Q4. Code:

```python
class Dog:
    pass

dog1 = Dog()
dog2 = Dog()
```

Your answer:

> one class & two objects

✅ Perfect.

Memory:

```
Dog Class
    |
    +------ dog1 Object
    |
    +------ dog2 Object
```

---

## Q5. Your example:

> Me - Class, my Kids - Objects

You are thinking in the right direction: one template and multiple real things.

However, this example needs a small correction.

A **person cannot be a class**, because "Me" is already a real individual.

A better example:

```
Human Class
    |
    +------ My Kid 1 Object
    |
    +------ My Kid 2 Object
```

The class should be the general design, not one specific person.

Other examples:

```
Student Class
    |
    +------ Rahul Object
    +------ Priya Object
```

```
Car Class
    |
    +------ My Car Object
    +------ Your Car Object
```

Your idea was close — you just confused a specific person with the general blueprint.

---

# Practice Exercise Review

You wrote:

```python
Class Book:
     pass

book1.Book()
book1.Book()
```

Good attempt. You understood that we need a class and objects.

There are two small Python syntax mistakes.

---

## Mistake 1: Python uses lowercase `class`

You wrote:

```python
Class Book:
```

Python keywords are lowercase.

Correct:

```python
class Book:
```

---

## Mistake 2: Creating an object

You wrote:

```python
book1.Book()
```

This is not how we create an object.

Think of it like this:

```
Class name → creates object

Book() → create a Book object
```

We store it inside a variable:

```python
book1 = Book()
```

The `=` means:

"Put this created object into this name."

---

Your corrected exercise:

```python
class Book:
    pass


book1 = Book()
book2 = Book()
```

Now the memory looks like:

```
Book Class
    |
    +------ book1 Object
    |
    +------ book2 Object
```

---

# Score: 9/10 ⭐

You have a good understanding of:

✅ Class = blueprint
✅ Object = real thing
✅ One class can create many objects
✅ Objects are separate from each other

The only thing to remember:

**A class is general. An object is specific.**

---

# Quick Memory Card

```
CLASS
= Plan
= Design
= Template

OBJECT
= Actual thing
= Created from class
= Lives in memory
```

Example:

```
Class: Student

Objects:
- Rahul
- Priya
- Amit
```

---

Before moving to the next topic (**Attributes / Properties**), answer these slightly harder questions:

### 1.

If `Car` is a class, which of these are objects?

A) Car
B) My red Honda
C) Car design
D) Your blue BMW

---

### 2.

Can two objects from the same class have different values?

Example:

```
Student 1 → age 12
Student 2 → age 15
```

Yes or No? Explain.

---

### 3.

What is wrong with this code?

```python
class Laptop:
    pass

Laptop1 = Laptop
```

Is `Laptop1` an object? Why or why not?

---

### 4.

Create a class called `Animal` and create three objects from it.

(Just write the code.)

---

### 5.

Explain this sentence in your own words:

"An object is an instance of a class."

(Do not worry about the word "instance" — explain what you think it means.)

---

Answer these, and then we will begin **Lesson 10: Attributes (Properties)**.


Excellent progress. Your answers show that the **class vs object idea is becoming clear**. Let's review each one.

---

# Question 1

**If `Car` is a class, which are objects?**

Options:

A) Car
B) My red Honda
C) Car design
D) Your blue BMW

Your answer:

> B & D

✅ Correct.

Why?

`My red Honda` and `Your blue BMW` are actual cars.

They are specific things.

```text
Car Class
   |
   +---- My red Honda Object
   |
   +---- Your blue BMW Object
```

A and C are the design/idea, so they represent the class.

---

# Question 2

**Can two objects from the same class have different values?**

Example:

```text
Student 1 → age 12
Student 2 → age 15
```

Your answer:

> Yes

✅ Correct.

This is one of the most important ideas in OOP.

The class gives the structure, but each object keeps its own information.

Example:

```text
Student Class

        |
        |
 ----------------
 |              |
 ↓              ↓

Rahul          Priya
age = 12       age = 15
```

Both are Students, but their data is different.

---

# Question 3

Code:

```python
class Laptop:
    pass

Laptop1 = Laptop
```

Your answer:

> it can become object if we use Laptop1 = Laptop()

✅ Excellent.

You found the mistake.

Currently:

```python
Laptop1 = Laptop
```

means:

"Laptop1 is another name pointing to the class."

It does **not create an object**.

To create an object:

```python
Laptop1 = Laptop()
```

The parentheses `()` are important.

Think:

```text
Laptop     → Blueprint
Laptop()   → Make a real laptop object
```

---

# Question 4

Your code:

```python
class Animal():
    pass

dog = Animal()
cat = Animal()
horse = Animal()
```

✅ Correct.

Small note:

The parentheses after the class name are optional when creating a class.

Both work:

```python
class Animal:
    pass
```

and

```python
class Animal():
    pass
```

The first style is more common in Python.

Your objects:

```text
Animal Class
     |
     +------ dog Object
     |
     +------ cat Object
     |
     +------ horse Object
```

Perfect.

---

# Question 5

Sentence:

"An object is an instance of a class."

Your answer:

> objects are created from class

✅ Correct.

The word **instance** simply means:

"one real example created from something."

Example:

```text
Cookie cutter = Class

Cookie = Object / Instance
```

One cookie is an instance of the cookie cutter design.

---

# Final Score: 10/10 ⭐

You are ready to move forward.

Before Lesson 10, remember this:

```
CLASS
------
A blueprint
A design
A plan


OBJECT
------
A real thing
Created from a class
Has its own data
```

Example:

```
Class:       Student

Objects:
           Rahul
           Priya
           Amit
```

---

# Tiny Challenge Before Next Lesson

Predict what this code does:

```python
class Phone:
    pass

phone1 = Phone()
phone2 = Phone()

phone1.brand = "Samsung"
phone2.brand = "Apple"

print(phone1.brand)
print(phone2.brand)
```

Answer:

1. What will be printed?
2. Are `phone1` and `phone2` the same object or different objects?
3. Where do you think `brand` is stored — inside the class or inside each object?

After this, we will start **Lesson 10: Attributes (Properties)**, where you will learn how objects store information like a phone's brand, a student's name, or a car's color.


Excellent! You're thinking through the code instead of memorizing it, which is exactly what we want.

Let's review your answers.

---

# Question 1

Code:

```python
class Phone:
    pass

phone1 = Phone()
phone2 = Phone()

phone1.brand = "Samsung"
phone2.brand = "Apple"

print(phone1.brand)
print(phone2.brand)
```

Your answer:

> It will print Samsung & Apple

✅ Correct.

Output:

```text
Samsung
Apple
```

Each object has its own `brand`.

---

# Question 2

Are `phone1` and `phone2` the same object?

Your answer:

> Different objects

✅ Correct.

Memory looks like this:

```text
             Phone Class
                  |
         -------------------
         |                 |
         ↓                 ↓
      phone1           phone2
   brand="Samsung"   brand="Apple"
```

Notice that **both objects come from the same class**, but each stores its own data.

---

# Question 3

Where is `brand` stored?

Your answer:

> Brand is stored outside the class

🟡 Almost correct, but let's make it more precise.

The best answer is:

> **`brand` is stored inside each object, not inside the class.**

Think of the class as a cookie cutter.

```text
Cookie Cutter (Class)
        |
        | makes
        ↓

Cookie 1 → Chocolate chips
Cookie 2 → Raisins
Cookie 3 → Plain
```

The cookie cutter does **not** hold the chocolate chips or raisins.

Each **cookie** holds its own ingredients.

Similarly:

```text
Phone Class
      |
      | creates
      ↓

phone1
brand = Samsung

phone2
brand = Apple
```

The `Phone` class doesn't store `"Samsung"` or `"Apple"`.

Each object stores its own `brand`.

---

# Why This Matters

Imagine this code:

```python
phone1.brand = "Samsung"
phone2.brand = "Apple"
```

If `brand` were stored in the class, then changing one phone's brand would change **every** phone's brand—which is not what we want.

Instead:

* `phone1.brand` belongs only to `phone1`.
* `phone2.brand` belongs only to `phone2`.

---

# A Small Preview of Lesson 10

So far, we've added `brand` **after** creating the objects:

```python
phone1.brand = "Samsung"
```

This works, but it's not the best way.

In the next lesson, you'll learn how to design a class so that every `Phone` object is expected to have attributes like `brand` and `color` from the moment it's created.

For example:

```python
phone1 = Phone("Samsung", "Black")
phone2 = Phone("Apple", "White")
```

We'll learn how to make that work step by step.

---

## Mini Quiz (No Coding)

Answer these:

1. What is the difference between a **class** and an **object** in one sentence?

2. If you create three `Dog` objects from one `Dog` class, how many classes and how many objects are there?

3. If `dog1.name = "Buddy"` and `dog2.name = "Max"`, where are `"Buddy"` and `"Max"` stored?

Once you answer these correctly, we'll begin **Lesson 10: Attributes (Properties)**.

Outstanding! 🎉 Your understanding has grown a lot since the beginning.

Let's review each answer carefully.

---

# Question 1

Your answer:

> Class - Blueprint design to the problem, where it stores the attributes (properties) & actions (methods) which are used by the objects created using the class. Object is an instance of the class created by using the class.

✅ This is a very good explanation.

I would make just one small improvement:

> **A class is a blueprint that defines what data (attributes) and behavior (methods) an object should have. An object is a real instance created from that blueprint.**

### Why this wording?

A class **defines** attributes and methods. It doesn't always *store* the actual data.

For example:

```python
class Phone:
    brand = "Unknown"
```

The class defines that a `Phone` has a `brand`.

But when you do:

```python
phone1.brand = "Samsung"
phone2.brand = "Apple"
```

the actual values `"Samsung"` and `"Apple"` are stored inside the objects.

This difference will become even clearer when we learn **constructors** and **instance attributes**.

---

# Question 2

> One Dog class & 3 Dog objects.

✅ Perfect.

Memory:

```text
               Dog Class
                   |
        -----------------------
        |          |          |
        ↓          ↓          ↓
      dog1       dog2       dog3
```

---

# Question 3

> Buddy and Max are stored in the objects itself.

✅ Exactly right.

Memory:

```text
Dog Class
     |
     | creates
     |
--------------------------
|                        |
↓                        ↓

dog1                   dog2
name = Buddy           name = Max
```

Notice that the class doesn't hold "Buddy" or "Max".

Each object holds its own data.

---

# 🌟 Progress Check

Here's what you've mastered so far:

| Topic                             | Status      |
| --------------------------------- | ----------- |
| What is a Class?                  | ✅ Excellent |
| What is an Object?                | ✅ Excellent |
| Difference between Class & Object | ✅ Excellent |
| One class → Many objects          | ✅ Excellent |
| Objects store their own data      | ✅ Excellent |

I'd say you're around **95% comfortable** with this topic. The remaining 5% will naturally become clear as we build more classes.

---

# 🧠 Memory Trick

Whenever you're confused, ask yourself these two questions:

1. **Is this the design?** → It's probably a **Class**.
2. **Is this a real thing created from the design?** → It's probably an **Object**.

Example:

```text
Recipe ---------------> Class
Cake baked from it ---> Object

Building plan --------> Class
Actual building ------> Object

Student form ---------> Class
Rahul's record -------> Object
```

---

# 🎯 Ready for Lesson 10: Attributes (Properties)

This is where OOP starts becoming really practical.

By the end of the next lesson, you'll be able to create objects like:

```python
student1.name = "Rahul"
student1.age = 20

student2.name = "Priya"
student2.age = 22
```

and you'll understand:

* What an **attribute** really is.
* Why different objects can have different attribute values.
* How attributes are stored in memory.
* Common beginner mistakes when working with attributes.

From here onward, you'll start building classes that resemble real-world entities like students, bank accounts, and shopping carts.

You're asking good questions and reasoning through the answers, which is exactly how you build a strong OOP foundation.

