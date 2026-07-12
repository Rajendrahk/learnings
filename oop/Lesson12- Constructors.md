Excellent! Since you've already reached **Lesson 12**, we'll continue from there and keep the same teaching style. We won't move to Lesson 13 until you're comfortable with constructors.

# Lesson 12: Constructors (`__init__`) in Python

---

# Step 1: Explain the idea in very simple words

Imagine you buy a new mobile phone.

The moment you switch it on for the first time, some things are already set:

* Language = English
* Battery = 100%
* Volume = 50%
* WiFi = Off

Nobody manually sets these every single time. The phone automatically initializes itself.

A **constructor** does exactly that for objects.

Whenever we create a new object, the constructor automatically runs and prepares the object.

Think of it as the **"setup method"** for an object.

---

### In Python

The constructor is a special method named:

```python
__init__()
```

Python calls it **automatically** whenever we create an object.

You never call it yourself.

---

## Why do we need constructors?

Without constructors:

```python
student = Student()

student.name = "Raj"
student.age = 25
student.city = "Bangalore"
```

Every time you create a student, you have to fill in all the details manually.

Now imagine creating 10,000 students!

Very repetitive.

Instead:

```python
student = Student("Raj", 25, "Bangalore")
```

Everything is initialized automatically.

Much easier.

---

# Step 2: Two Real-life Examples

## Example 1: Restaurant

When you order a pizza,

the chef automatically

* prepares the dough
* adds cheese
* adds sauce
* bakes it

You don't tell him every step.

The constructor is like the chef's default preparation process.

---

## Example 2: School Admission

When a student joins school,

the office automatically creates:

* Student ID
* Roll Number
* Attendance Record
* Library Account

These happen automatically.

Constructor = Admission Process

---

# Step 3: Simple Diagram

```
Create Object
      |
      ▼

Student("Raj",25)

      |

Python automatically calls

      |

__init__()

      |

Stores values

      |

Name = Raj
Age = 25

Object Ready
```

---

# Step 4: Smallest Possible Code Example

```python
class Student:

    def __init__(self):
        print("Student object created")


student1 = Student()
```

---

# Step 5: Explain Every Line

---

### Line 1

```python
class Student:
```

We are creating a blueprint called Student.

Nothing is created yet.

---

### Line 3

```python
def __init__(self):
```

This is the constructor.

It has a special name.

Python recognizes this name.

Whenever an object is created,

Python automatically calls it.

---

### Line 5

```python
print("Student object created")
```

This line executes immediately after the object is created.

---

### Line 8

```python
student1 = Student()
```

This creates an object.

Behind the scenes Python does:

```
Create memory

↓

Create object

↓

Call __init__()

↓

Run print()

↓

Return object
```

Output

```
Student object created
```

Notice that **we never called `__init__()` ourselves**.

Python did it automatically.

---

# What Happens in Memory?

Imagine your computer's memory like this:

Before object creation:

```
Memory

(empty)
```

After

```python
student1 = Student()
```

Memory becomes:

```
Memory

student1
   │
   ▼
+----------------+
| Student Object |
+----------------+
```

Then Python immediately runs

```
__init__()
```

before giving you the object.

---

# Another Example

```python
class Dog:

    def __init__(self):
        print("Dog is born")


dog1 = Dog()
dog2 = Dog()
```

Output

```
Dog is born
Dog is born
```

Why twice?

Because two objects were created.

Each object runs its own constructor.

---

# Constructors with Data

Now let's make constructors useful.

```python
class Student:

    def __init__(self, name):
        self.name = name


student1 = Student("Raj")
```

---

### What happens?

Python secretly does:

```
Student("Raj")

↓

Create object

↓

Call

__init__(student1, "Raj")
```

Notice something interesting.

Python automatically passes

```
student1
```

as `self`.

You only provide

```
"Raj"
```

---

# Visual Flow

```
Student("Raj")

↓

self ----> newly created object

name ----> "Raj"

↓

self.name = name

↓

Object now stores

name = Raj
```

---

# Another Example

```python
class Car:

    def __init__(self, brand, color):

        self.brand = brand
        self.color = color


car1 = Car("Toyota", "White")
```

Object looks like

```
car1

brand = Toyota

color = White
```

---

# More Real-Life Example

Imagine filling a bank account form.

```
Name : Raj

Age : 25

Balance : 10000
```

Instead of writing these later,

the bank records them while creating the account.

Exactly what constructors do.

---

# Constructor with Three Values

```python
class Employee:

    def __init__(self, name, age, salary):

        self.name = name
        self.age = age
        self.salary = salary
```

Now

```python
emp1 = Employee("Rahul", 30, 70000)
```

Object contains

```
Name

Rahul

Age

30

Salary

70000
```

---

# Common Beginner Mistakes

### Mistake 1

Forgetting `self`

Wrong

```python
def __init__(name):
```

Correct

```python
def __init__(self, name):
```

---

### Mistake 2

Forgetting `self.`

Wrong

```python
name = name
```

Nothing is stored in the object.

Correct

```python
self.name = name
```

---

### Mistake 3

Calling constructor directly

Wrong

```python
Student.__init__()
```

Don't do this.

Instead create an object.

```python
Student()
```

---

# Why Is `__init__` Called Automatically?

Because Python knows

```
Student()
```

means

```
Create object

↓

Initialize object

↓

Return object
```

Initialization means running `__init__`.

---

# Step 6: Another Example

```python
class Mobile:

    def __init__(self, company, price):

        self.company = company
        self.price = price


phone = Mobile("Samsung", 50000)

print(phone.company)

print(phone.price)
```

Output

```
Samsung

50000
```

---

# Memory Diagram

```
phone

│

▼

+------------------------+

company = Samsung

price = 50000

+------------------------+
```

The constructor stored these values inside the object when it was created.

---

# Step 7: Check Your Understanding

Answer these without looking back:

1. What is a constructor in Python?
2. What is the special name of a constructor?
3. Do we call `__init__()` manually or does Python call it automatically?
4. What is the purpose of `self.name = name`?
5. If you create three objects, how many times does the constructor run?

Reply with your answers (e.g., `1. ...`, `2. ...`). If anything is unclear, I'll explain it before we move on.

---

# Step 8: Practice Exercise (Don't Run Yet—Think First)

Create a class named `Book`.

Requirements:

* Constructor should accept:

  * `title`
  * `author`
  * `price`
* Store all three values in the object using `self`.
* Create one object for:

  * Title = `"Python Basics"`
  * Author = `"Raj"`
  * Price = `499`

**Hint 1:** Start with `class Book:`.

**Hint 2:** Your constructor will look like:

```python
def __init__(self, title, author, price):
```

**Hint 3:** Inside the constructor, assign each parameter to an attribute using `self`.

Don't worry about printing anything yet. Try writing the class and creating the object yourself, then share your code. I'll review it line by line, point out any mistakes, and explain why they happen before we continue to **Lesson 13: The `self` Keyword**.


Excellent effort! 👏 You're thinking about **what** a constructor does instead of just memorizing syntax, which is exactly how you should learn. Let's review your answers one by one.

---

# Review of Your Answers

## Q1. What is a constructor?

Your answer:

> Constructor is a special way which provides a tool to create the object, it helps to pass the attribute provided in object parameters to create the real object.

### What's Correct ✅

* You understood that a constructor is involved when an object is created.
* You understood that it helps initialize the object with values.

### Small Correction

A constructor **does not create the object**. Python creates the object first.

The constructor's job is to **initialize** (set up) the object after it has been created.

Think of it like this:

```
Python creates the object
        │
        ▼
Constructor (__init__) runs
        │
        ▼
Sets initial values
        │
        ▼
Object is ready to use
```

### A simple definition to remember

> **A constructor is a special method that Python automatically calls when a new object is created. Its job is to initialize the object's data.**

---

## Q2. What is the special name of a constructor?

Your answer:

> `__init__`

✅ **100% Correct!**

---

## Q3. Who calls `__init__()`?

Your answer:

> Python call it automatically.

✅ **Perfect!**

You never write:

```python
book.__init__()
```

Instead:

```python
book = Book(...)
```

Python internally calls:

```python
__init__()
```

---

## Q4. What is the purpose of `self.name = name`?

Your answer:

> self.name = name provides a route way to pass the object name to the **init** constructor.

You're close, but this is the one concept I'd like to improve before moving on.

### The important idea

Let's separate the two `name`s:

```python
def __init__(self, name):
```

Here:

* `name` (right side) is the **value passed into the constructor**.

Now:

```python
self.name = name
```

means:

```
Object's name
      │
      ▼
self.name

=

Value received
      │
      ▼
name
```

If you create:

```python
book = Book("Python Basics")
```

then Python does something like:

```
name = "Python Basics"

↓

self.name = "Python Basics"
```

Now the object remembers that value.

A better definition is:

> **`self.name = name` stores the value passed into the constructor inside the object so it can be used later.**

This is a very important concept because almost every Python class uses it.

---

## Q5. If three objects are created, how many times does the constructor run?

Your answer:

> 3 times

✅ **Absolutely Correct!**

Each object has its own constructor call.

```
Book(...)
↓

Constructor runs

Book(...)
↓

Constructor runs

Book(...)
↓

Constructor runs
```

---

# Review of Your Coding Exercise

You wrote:

```python
class Book():
    def __init__(self, title, author, price):

    self.title = title
    self.author = author
    self.price = price

book1 = Book("Python Basics","Raj",499)
```

## Great Job! 🎉

You got:

* Class name ✔️
* Constructor name ✔️
* Parameters ✔️
* `self.title = title` ✔️
* Object creation ✔️

The only issue is **indentation**.

In Python, indentation tells Python which code belongs to the constructor.

It should look like this:

```python
class Book:
    def __init__(self, title, author, price):
        self.title = title
        self.author = author
        self.price = price

book1 = Book("Python Basics", "Raj", 499)
```

Notice that the three `self...` lines are indented one level inside `__init__`.

---

# Let's See What Happens in Memory

After running:

```python
book1 = Book("Python Basics", "Raj", 499)
```

Memory looks like this:

```
book1
  │
  ▼
+---------------------------+
| title  = Python Basics    |
| author = Raj              |
| price  = 499              |
+---------------------------+
```

The constructor stored these three values inside the object.

---

# Memory Trick 🧠

Think of `__init__` as:

> **Initialize = Set everything up before using it.**

Just like when you buy a new phone:

* Insert SIM
* Set language
* Set Wi-Fi
* Set date & time

You don't use the phone before this setup is complete.

Similarly, Python initializes an object before you start using it.

---

# Mini Challenge (No Hints This Time)

Create a class called `Laptop`.

Requirements:

* Constructor should accept:

  * `brand`
  * `ram`
  * `price`
* Store them using `self`.
* Create two objects:

```text
Laptop 1:
Brand = Dell
RAM = 16
Price = 75000

Laptop 2:
Brand = HP
RAM = 8
Price = 55000
```

Then print:

```python
print(laptop1.brand)
print(laptop2.price)
```

Take your time and write the code yourself. I'll review it line by line. If you get this right, you'll have a solid understanding of constructors, and we'll confidently move on to **Lesson 13: `self`**, where you'll learn one of the most important concepts in Python OOP.

Excellent work! 🎉 You're understanding constructors well. I can see you're thinking in terms of **classes**, **objects**, and **attributes**, which is exactly the right direction.

Let's review your code like a Python mentor.

---

# Your Code

```python
class Laptop:
    	def __init__(self, brand, ram, price):
            self.brand = brand
            self.ram = ram
            self.price = price
            	
laptop1 = Laptop("Dell", 16, 7500)
laptop2 = Laptop("HP", 16, 7500)

print(laptop1.brand)
print(laptop2.price)
```

---

# Line-by-Line Review

## Line 1

```python
class Laptop:
```

✅ Correct.

You created a blueprint named **Laptop**.

At this point, no laptop object exists yet.

---

## Line 2

```python
def __init__(self, brand, ram, price):
```

✅ Correct.

Your constructor accepts three values:

* brand
* ram
* price

Python will automatically call this constructor whenever a new `Laptop` object is created.

---

## Lines 3–5

```python
self.brand = brand
self.ram = ram
self.price = price
```

✅ Perfect!

These lines store the values inside each laptop object.

For example, when you write:

```python
Laptop("Dell", 16, 7500)
```

Python internally does something like:

```text
brand = "Dell"
ram = 16
price = 7500

↓

Store them inside the object

self.brand = "Dell"
self.ram = 16
self.price = 7500
```

---

## Line 7

```python
laptop1 = Laptop("Dell", 16, 7500)
```

✅ Correct.

Python performs:

```text
Create Laptop object
        │
        ▼
Call __init__()
        │
        ▼
Store:

brand = Dell
ram = 16
price = 7500
```

Memory now looks like:

```text
laptop1
   │
   ▼
+----------------+
| brand = Dell   |
| ram = 16       |
| price = 7500   |
+----------------+
```

---

## Line 8

```python
laptop2 = Laptop("HP", 16, 7500)
```

✅ This is syntactically correct.

However...

### According to the exercise

Laptop 2 should have been:

```text
Brand = HP
RAM = 8
Price = 55000
```

You wrote:

```python
Laptop("HP", 16, 7500)
```

So it's not wrong Python code, but it doesn't match the exercise requirements.

It should be:

```python
laptop2 = Laptop("HP", 8, 55000)
```

---

## Last Two Lines

```python
print(laptop1.brand)
print(laptop2.price)
```

✅ Perfect.

Output (with your values):

```text
Dell
7500
```

Output (with the exercise values):

```text
Dell
55000
```

---

# One Small Formatting Issue

Your code uses a mix of **tabs** and **spaces** for indentation.

Python is very strict about indentation.

It's best practice to use **4 spaces** consistently.

Like this:

```python
class Laptop:
    def __init__(self, brand, ram, price):
        self.brand = brand
        self.ram = ram
        self.price = price

laptop1 = Laptop("Dell", 16, 7500)
laptop2 = Laptop("HP", 8, 55000)

print(laptop1.brand)
print(laptop2.price)
```

---

# What Happens in Memory?

After creating both objects:

```text
                    Memory

laptop1                     laptop2
   │                           │
   ▼                           ▼

+----------------+      +----------------+
| brand = Dell   |      | brand = HP     |
| ram = 16       |      | ram = 8        |
| price = 7500   |      | price = 55000  |
+----------------+      +----------------+
```

Notice something important:

Each object has **its own copy** of the data.

Changing `laptop1.brand` will **not** change `laptop2.brand`.

---

# Quick Revision Quiz (No Coding)

Answer these without looking at your notes.

### Q1

What is the difference between these two?

```python
brand
```

and

```python
self.brand
```

---

### Q2

How many times will `__init__()` execute here?

```python
l1 = Laptop("Dell", 16, 7500)
l2 = Laptop("HP", 8, 55000)
l3 = Laptop("Lenovo", 32, 90000)
```

---

### Q3

Complete this sentence:

> A constructor is used to ____________ an object.

---

### Q4

True or False?

> We normally call `__init__()` directly ourselves.

---

### Q5 (Most Important)

When you write:

```python
self.price = price
```

Which one is the **object's attribute**, and which one is the **constructor parameter**?

* A. Left side = Attribute, Right side = Parameter
* B. Left side = Parameter, Right side = Attribute

---

## 🎉 Progress Update

You've now completed **Lesson 12: Constructors**. Once you answer these five questions correctly, we'll move to **Lesson 13: The `self` Keyword**.

Although you've already used `self` in several examples, in the next lesson you'll learn **what `self` actually is**, **why Python needs it**, and **what happens behind the scenes** when methods are called. This is one of the most important concepts in Python OOP, and understanding it deeply will make the rest of OOP much easier.

Excellent! 🌟 You're making solid progress. More importantly, I can see that you're **reasoning** about the concepts instead of memorizing definitions. That's exactly how good software developers learn.

Let's review your answers.

---

# Review

## Q1. Difference between `brand` and `self.brand`

Your answer:

> brand is just the name, self.brand is the object name.

🟡 **Partially Correct (8.5/10)**

You're very close. Let me make it a little clearer.

Consider this constructor:

```python
class Laptop:
    def __init__(self, brand):
        self.brand = brand
```

There are **two different `brand`s** here.

### The right-side `brand`

```python
brand
```

This is a **parameter** (a temporary variable).

It only exists while the constructor is running.

When you create:

```python
Laptop("Dell")
```

Python does something like:

```text
brand = "Dell"
```

This variable is temporary.

---

### The left-side `self.brand`

```python
self.brand
```

This is an **attribute** (also called a property) stored **inside the object**.

It stays with the object as long as the object exists.

Think of it like this:

```text
Temporary box

brand
 │
 ▼
"Dell"

↓

Copied into

Laptop Object

+---------------+
| brand = Dell  |
+---------------+
```

### A memory trick

* `brand` → temporary value received by the constructor
* `self.brand` → permanent value stored inside the object

> We'll spend an entire lesson on `self` next, so this will become crystal clear.

---

## Q2. How many times does `__init__()` run?

Your answer:

> 3 times

✅ **100% Correct**

Each object gets its own constructor call.

---

## Q3. Constructor is used to ______ an object.

Your answer:

> initialize

✅ **Perfect!**

This is the key purpose of a constructor.

---

## Q4. Do we call `__init__()` directly?

Your answer:

> False

✅ **Correct**

Python calls it automatically.

---

## Q5.

```python
self.price = price
```

Your answer:

> A

✅ **Correct**

Left side → Object's attribute

Right side → Constructor parameter

Excellent.

---

# Overall Score

| Question | Result            |
| -------- | ----------------- |
| Q1       | 🟡 Almost Correct |
| Q2       | ✅                 |
| Q3       | ✅                 |
| Q4       | ✅                 |
| Q5       | ✅                 |

## **Score: 4.5 / 5 ⭐⭐⭐⭐⭐**

That's a very good result.

---

# One Last Visualization Before We Move On

Let's trace this code step by step:

```python
class Laptop:

    def __init__(self, brand):
        self.brand = brand

laptop1 = Laptop("Dell")
```

### Step 1

Python creates an empty object.

```text
Laptop Object

+----------+
|          |
+----------+
```

---

### Step 2

Python calls:

```python
__init__(self, "Dell")
```

At this moment:

```text
self  ─────► Laptop Object

brand ─────► "Dell"
```

---

### Step 3

This line runs:

```python
self.brand = brand
```

Python copies the value:

```text
Laptop Object

+----------------+
| brand = Dell   |
+----------------+
```

Now the object remembers `"Dell"` forever (until the object is destroyed).

---

# 🧠 Constructor Memory Trick

Think of a **hotel**.

When a guest checks in:

Guest:

```text
Name = Raj
Room = 305
Days = 2
```

Reception stores these details in the hotel's records.

Similarly, a constructor stores the values passed during object creation inside the object.

```text
Guest arrives
      │
      ▼
Constructor
      │
      ▼
Stores information
      │
      ▼
Object is ready
```

---

# 🎉 Congratulations!

You have successfully completed **Lesson 12: Constructors (`__init__`)**.

So far, you've learned:

* ✅ What programming is
* ✅ Problems and how code solves them
* ✅ Variables
* ✅ Data types
* ✅ Functions
* ✅ Why OOP exists
* ✅ Objects
* ✅ Classes
* ✅ Class vs Object
* ✅ Attributes
* ✅ Methods
* ✅ **Constructors**

---

## Next Lesson: **Lesson 13 – The `self` Keyword**

This is one of the most important topics in Python OOP.

By the end of the lesson, you'll understand:

* Why every method has `self`
* What `self` actually points to
* Why Python needs `self`
* What happens in memory when methods are called
* Why `self` is **not** a keyword (you can technically name it something else, though you shouldn't)
* The difference between `self.name` and `name`
* Common beginner mistakes involving `self`

Once you deeply understand `self`, topics like **encapsulation**, **inheritance**, and **polymorphism** will become much easier.
