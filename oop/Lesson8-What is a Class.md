# Lesson 8: What is a Class?

Great progress! You now understand that:

```text
Class → Blueprint
Object → Actual thing created from blueprint
```

Today we will go deeper into **classes**, because classes are the foundation of OOP.

---

# Step 1: Explain the idea in very simple words

A **class** is a blueprint or a plan used to create objects.

A class describes:

1. What information an object will have.
2. What actions an object can perform.

Think about a cookie factory.

Before making cookies, you need a recipe.

The recipe says:

```text
Cookie Recipe

Shape: Round
Size: Medium
Ingredients: Flour, Sugar

Steps:
- Mix
- Bake
- Decorate
```

The recipe is the **class**.

The actual cookies are the **objects**.

```text
          Cookie Class
          (Recipe)

              |
       ----------------
       |              |
       ▼              ▼

    Cookie 1       Cookie 2
    Object         Object
```

---

# Step 2: Two Real-Life Examples

## Example 1: Student Class

Imagine a school system.

Every student has:

Information:

```text
Name
Age
Roll Number
Marks
```

Actions:

```text
Study
Attend Class
Take Exam
```

Instead of writing separate code for every student:

```text
Rahul's name
Rahul's age
Rahul's marks

Priya's name
Priya's age
Priya's marks
```

We create a blueprint:

```text
             Student Class

       +----------------+
       | Information    |
       |----------------|
       | name           |
       | age            |
       | marks          |
       +----------------+

       +----------------+
       | Actions        |
       |----------------|
       | study()        |
       | exam()         |
       +----------------+
```

Then create many student objects.

---

## Example 2: Bank Account Class

A bank does not create every account manually.

It has a standard design.

Bank Account Class:

Information:

```text
Account Number
Holder Name
Balance
```

Actions:

```text
Deposit Money
Withdraw Money
Check Balance
```

Objects:

```text
Account 1 → Ravi's Account

Account 2 → Priya's Account

Account 3 → Amit's Account
```

Same blueprint, different objects.

---

# Step 3: Simple Diagram

A class works like a factory.

```text
                 CLASS

              +----------+
              |  Car     |
              | Blueprint|
              +----------+

                    |
        ------------------------
        |                      |
        ▼                      ▼

     Object                 Object

     car1                   car2

   Red Car               Blue Car
```

The class does not represent one specific car.

It describes how cars should be created.

---

# Step 4: Smallest Possible Python Code Example

Let's create a simple class:

```python
class Car:
    pass
```

Now create objects:

```python
car1 = Car()
car2 = Car()
```

Complete code:

```python
class Car:
    pass

car1 = Car()
car2 = Car()
```

---

# Step 5: Explain Every Line of Code

## Line 1

```python
class Car:
```

Let's break this down.

### `class`

This keyword tells Python:

> "I want to create a blueprint."

---

### `Car`

This is the name of the blueprint.

It represents the general idea of a car.

It is not a real car yet.

---

### `:`

The colon means:

> "The instructions inside the class start here."

---

## Line 2

```python
    pass
```

`pass` means:

> "There is nothing inside this class yet."

We use it temporarily.

Later we will add:

* Attributes
* Methods

---

## Line 4

```python
car1 = Car()
```

This creates the first object.

Think:

```text
Car Blueprint

       |
       ▼

Actual Car Object

car1
```

---

## Line 5

```python
car2 = Car()
```

This creates another object.

Memory:

```text
Car Class

       |
       |
  -------------
  |           |
  ▼           ▼

car1        car2

Object      Object
```

They are separate.

---

# What Happens in Memory?

When Python reads:

```python
class Car:
    pass
```

It creates a class blueprint.

Memory:

```text
Memory:

Car
 |
 ▼
Blueprint
```

---

When Python reads:

```python
car1 = Car()
```

It creates an object.

Memory:

```text
Memory:

Car
 |
 ▼
Blueprint


car1
 |
 ▼
Car Object
```

---

When:

```python
car2 = Car()
```

Memory:

```text
Memory:

Car
 |
 ▼
Blueprint


car1
 |
 ▼
Car Object


car2
 |
 ▼
Car Object
```

---

# Step 6: Another Example

Let's create a real class idea.

```python
class Student:
    pass

student1 = Student()
student2 = Student()
```

We have:

```text
          Student Class

          Blueprint

              |
       ----------------

       ▼              ▼

   student1        student2

   Object          Object
```

Both students are created from the same class.

Later, we can give them different:

* Names
* Ages
* Marks

---

# Important Difference: Class vs Object

| Class                                 | Object                        |
| ------------------------------------- | ----------------------------- |
| Blueprint                             | Actual thing                  |
| Design                                | Created item                  |
| Template                              | Instance                      |
| Does not represent one specific thing | Represents one specific thing |

Example:

| Class       | Objects                        |
| ----------- | ------------------------------ |
| Car         | my_car, your_car               |
| Student     | Rahul, Priya                   |
| BankAccount | Ravi's account, Amit's account |

---

# Common Beginner Mistakes

## Mistake 1: Thinking class is a real object

Wrong:

> "Car class is my red car."

Correct:

```text
Car class = idea of a car

my_car = actual car
```

---

## Mistake 2: Forgetting parentheses when creating objects

Wrong:

```python
car1 = Car
```

This stores the class itself.

Correct:

```python
car1 = Car()
```

This creates an object.

---

## Mistake 3: Creating one class for every object

Wrong idea:

```text
RahulClass
PriyaClass
AmitClass
```

Better:

```text
Student Class

creates:

Rahul object
Priya object
Amit object
```

---

# Step 7: Questions

Answer these:

### Question 1

What is a class?

---

### Question 2

Why do we use classes?

---

### Question 3

Which one creates an object?

A)

```python
class Student:
    pass
```

B)

```python
student1 = Student()
```

---

### Question 4

What is the difference between:

```text
Student class
```

and

```text
Rahul student object
```

---

### Question 5

True or False:

> One class can create many objects.

---

# Step 8: Practice Exercise

Design a **Mobile Phone Class**.

Do not write code yet.

## Class Name:

---

## Attributes (Information):

1. ---
2. ---
3. ---

## Methods (Actions):

1. __________()
2. __________()
3. __________()

---

# Coding Exercise

Create an empty class:

```python
class MobilePhone:
    pass
```

Then create two objects:

```python
phone1 = MobilePhone()
phone2 = MobilePhone()
```

---

Reply with:

1. Answers to the 5 questions.
2. Your Mobile Phone class design.
3. Your Python code.

After reviewing, we will move to **Lesson 9: Difference Between Class and Object** where we will compare them deeply with more examples and memory diagrams.
