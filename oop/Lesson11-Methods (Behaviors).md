Excellent! You're doing well. So far you've learned:

* ✅ Class = Blueprint
* ✅ Object = Real instance
* ✅ Attributes = Information about an object

Now we'll learn the other half of an object.

# Lesson 11: Methods (Behaviors)

---

# Step 1: Explain the idea in very simple words

Imagine your pet dog.

Your dog has:

**Information (Attributes):**

* Name = Buddy
* Age = 3
* Color = Brown

But is a dog just information?

No.

A dog can also:

* Bark
* Eat
* Run
* Sleep

These are **actions**.

In OOP, these actions are called **methods**.

## Simple Definition

> **A method is a function that belongs to a class and describes what an object can do.**

Notice something important:

Earlier, we learned **functions**.

A method is **just a function inside a class**.

Think of it like this:

```text
Function
    ↓
General action

Method
    ↓
Action that belongs to an object
```

---

# Step 2: Two Real-Life Examples

## Example 1: Car 🚗

A car has:

### Attributes

* Color
* Brand
* Fuel

### Methods

* Start()
* Stop()
* Accelerate()
* Brake()

```text
Car

Has:
-------
Brand
Color
Fuel

Can:
-------
Start()
Stop()
Brake()
```

---

## Example 2: Bank Account 🏦

A bank account has:

### Attributes

* Account Number
* Owner Name
* Balance

### Methods

* Deposit()
* Withdraw()
* CheckBalance()

Notice something:

The **balance** is information.

The **deposit** is an action.

---

# Step 3: Simple Diagram

```text
             Student

        Attributes
        ----------
        name
        age

        Methods
        --------
        study()
        play()
        sleep()
```

Think of every object like a person.

Every person has:

* Information
* Abilities

Objects are exactly the same.

---

# Step 4: Smallest Possible Code Example

```python
class Dog:

    def bark(self):
        print("Woof! Woof!")


dog1 = Dog()

dog1.bark()
```

Don't worry if `self` looks strange.

We'll spend an entire lesson on it (Lesson 13).

For now, think of `self` as:

> "The object that is doing the action."

---

# Step 5: Explain Every Line

## Line 1

```python
class Dog:
```

Create a blueprint called `Dog`.

---

## Line 3

```python
def bark(self):
```

Let's break this down.

```python
def
```

Means:

"I'm creating a function."

---

```python
bark
```

This is the method's name.

---

```python
(self)
```

We'll study this deeply later.

For now, remember:

> Every method in a class needs `self` as its first parameter.

---

## Line 4

```python
print("Woof! Woof!")
```

Whenever this method runs,

Python prints:

```text
Woof! Woof!
```

---

## Line 7

```python
dog1 = Dog()
```

Create one dog object.

Memory:

```text
Dog Class
      |
      |
      ↓

dog1
```

---

## Line 9

```python
dog1.bark()
```

Read this in English:

> "Tell `dog1` to bark."

Output:

```text
Woof! Woof!
```

---

# What Does the Dot (`.`) Mean?

This is very important.

Look at:

```python
dog1.bark()
```

Break it apart:

```text
dog1
```

Which object?

↓

```text
.
```

Access something inside the object.

↓

```text
bark()
```

Call the method.

Think of the dot (`.`) as saying:

> "Go inside this object."

The same applies to attributes:

```python
dog1.name
```

means:

> "Go inside `dog1` and get the `name`."

---

# Step 6: Another Example

Let's make a robot.

```python
class Robot:

    def greet(self):
        print("Hello! I am your robot.")


robot1 = Robot()
robot2 = Robot()

robot1.greet()
robot2.greet()
```

Output:

```text
Hello! I am your robot.
Hello! I am your robot.
```

Both objects use the same method because they were created from the same class.

Memory:

```text
             Robot Class
                  |
        -------------------
        |                 |
        ↓                 ↓

     robot1           robot2

       greet()         greet()
```

---

# Methods vs Attributes

This is one of the most common interview questions.

| Attribute   | Method          |
| ----------- | --------------- |
| Stores data | Performs action |
| Noun        | Verb            |
| `name`      | `study()`       |
| `color`     | `start()`       |
| `balance`   | `deposit()`     |

### Memory Trick

Ask yourself:

> **Is it information?**

→ Attribute

> **Is it an action?**

→ Method

Example:

```text
Phone

Brand
Storage
Battery
```

These are attributes.

```text
Call()
Restart()
TakePhoto()
```

These are methods.

---

# Common Beginner Mistakes

## Mistake 1: Forgetting the parentheses

```python
dog1.bark
```

This doesn't call the method.

You're just referring to it.

To execute it:

```python
dog1.bark()
```

The `()` tells Python:

> "Run this method."

---

## Mistake 2: Forgetting `self`

Inside a class, beginners often write:

```python
class Dog:

    def bark():
        print("Woof")
```

This will cause problems when you call the method.

For now, always remember:

```python
def bark(self):
```

We'll learn exactly *why* in Lesson 13.

---

## Mistake 3: Mixing attributes and methods

Wrong:

```python
dog1.name()
```

Why?

Because `name` is data, not an action.

Correct:

```python
print(dog1.name)
```

---

Wrong:

```python
dog1.bark
```

Correct:

```python
dog1.bark()
```

Methods need `()` to run.

---

# Memory Diagram

```text
                Dog Object

         +--------------------+
         | name = Buddy       | ← Attribute
         | age = 3            | ← Attribute
         |                    |
         | bark()             | ← Method
         | eat()              | ← Method
         +--------------------+
```

Think of an object as a box containing:

* Data (attributes)
* Actions (methods)

---

# Step 7: Questions

### Question 1

What is a method in your own words?

---

### Question 2

Which of these are methods?

A. Name

B. Eat()

C. Sleep()

D. Age

---

### Question 3

Predict the output:

```python
class Cat:

    def sound(self):
        print("Meow")


cat1 = Cat()

cat1.sound()
```

---

### Question 4

Which one calls the method correctly?

A.

```python
dog.bark
```

B.

```python
dog.bark()
```

Explain why.

---

### Question 5

A `TV` has:

* Brand
* Size
* TurnOn()
* TurnOff()

Which are attributes, and which are methods?

---

# Step 8: Practice Exercise

Create a class called `Fan`.

Create one method called:

```python
turn_on()
```

When it is called, it should print:

```text
Fan is now ON.
```

Then:

1. Create one object named `fan1`.
2. Call the `turn_on()` method.

**Hint:** The method should be inside the class, and don't forget `self`.

---

## 🌟 Thinking Like a Software Developer

Before writing code, ask yourself:

> What **data** does this object have?

> What **actions** can this object perform?

For a `Fan`:

**Attributes (later):**

* brand
* speed
* color

**Methods:**

* turn_on()
* turn_off()
* increase_speed()

This habit will help you design good classes as your projects grow.

---

Reply with:

1. Your answers to the 5 questions.
2. Your `Fan` class code.

I'll review it line by line, explain any mistakes, and then we'll continue building your OOP skills.

Excellent! 👏 Your understanding is getting stronger with each lesson.

You answered **all 5 questions correctly**. Before reviewing your answers, I noticed you didn't include the **`Fan` coding exercise**. We'll come back to that after the review.

---

# Review of Your Answers

## Q1. What is a method?

Your answer:

> Method is the action which performs actions.

✅ You're on the right track.

A slightly clearer definition would be:

> **A method is a function inside a class that defines what an object can do.**

Notice two important ideas:

* It's a **function**.
* It belongs to a **class**.

For example:

```python
class Dog:
    def bark(self):
        print("Woof!")
```

Here:

* `Dog` → Class
* `bark()` → Method

---

## Q2. Which are methods?

Your answer:

> B. Eat() & C. Sleep()

✅ Correct!

Think of methods as **verbs** (actions).

Examples:

* eat()
* sleep()
* run()
* deposit()
* withdraw()

---

## Q3. Predict the output

Your answer:

> Meow

✅ Correct.

Python creates the `Cat` object and then calls its `sound()` method.

Output:

```text
Meow
```

---

## Q4. Which correctly calls the method?

Your answer:

> B

✅ Correct.

```python
dog.bark()
```

This tells Python:

> "Execute the `bark` method."

Whereas:

```python
dog.bark
```

doesn't execute it—it just refers to the method itself.

Here's a simple analogy:

Suppose your TV remote has a power button.

* Looking at the button = `dog.bark`
* Pressing the button = `dog.bark()`

The parentheses `()` are like pressing the button.

---

## Q5. TV example

Your answer:

> Brand & size are attributes & turnOn & turnOff are methods

✅ Perfect!

Here's the breakdown:

```text
TV

Attributes
----------
Brand
Size

Methods
-------
turn_on()
turn_off()
```

Excellent.

---

# 🎉 Score: 5/5

You're doing a great job distinguishing between **data** and **behavior**, which is one of the core ideas of OOP.

---

# One Small Improvement

Earlier, you learned:

* **Attributes** = Information (nouns)
* **Methods** = Actions (verbs)

Whenever you're unsure, ask yourself:

> Is this describing the object?

➡️ Attribute

> Is this something the object does?

➡️ Method

Example:

```text
Bank Account

Has:
------
balance
owner_name

Can:
------
deposit()
withdraw()
check_balance()
```

---

# Now Let's Do the Coding Exercise

Create this class:

```python
class Fan:
    ...
```

Requirements:

1. Create a method called `turn_on()`.
2. It should print:

```text
Fan is now ON.
```

3. Create an object called `fan1`.
4. Call the method.

Try writing it yourself.

---

# ⭐ Bonus Challenge (Optional)

After you finish the first exercise, add another method:

```python
turn_off()
```

It should print:

```text
Fan is now OFF.
```

Then call **both** methods.

Expected output:

```text
Fan is now ON.
Fan is now OFF.
```

---

## 📖 What Comes Next?

After you're comfortable with methods, we'll move to **Lesson 12: Constructors (`__init__`)**.

This is where OOP starts feeling much more natural.

Instead of writing:

```python
laptop1 = Laptop()
laptop1.brand = "Dell"
laptop1.ram = 16
```

you'll learn to write:

```python
laptop1 = Laptop("Dell", 16)
```

You'll also finally understand **how Python automatically fills an object's attributes when it's created**.

This is a major milestone in learning OOP.
