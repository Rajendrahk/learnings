# Phase 2 – Lesson 2: Prompt Templates

## Learning Objective

Understand:

* What Prompt Templates are
* Why they are used
* Static vs Dynamic prompts
* Variables in prompts
* Benefits and best practices

---

# What is a Prompt Template?

A **Prompt Template** is a reusable prompt with **placeholders (variables)**.

Instead of hardcoding prompts, you create a template and fill in values dynamically.

---

# Without Prompt Templates

Hardcoded prompt:

```text
Explain Python in simple language.
```

Problem:

* Not reusable
* Difficult to maintain
* Requires code changes for every new topic

---

# With Prompt Templates

Reusable template:

```text
Explain {topic} in simple language.
```

Example:

```text
topic = "LangChain"

↓

Explain LangChain in simple language.
```

---

# Why Use Prompt Templates?

* Reusable prompts
* Dynamic input
* Easier maintenance
* Cleaner code
* Consistent prompt formatting

---

# Prompt Flow

```text
Template
   │
   ▼
Variables
   │
   ▼
Formatted Prompt
   │
   ▼
Chat Model
```

---

# Template Components

| Component        | Purpose                        |
| ---------------- | ------------------------------ |
| Template         | Prompt with placeholders       |
| Variables        | Dynamic values                 |
| Formatted Prompt | Final prompt sent to the model |

---

# Static vs Dynamic Prompts

## Static Prompt

```text
Explain Python.
```

* Fixed content
* No variables

---

## Dynamic Prompt

```text
Explain {topic}.
```

Example:

```text
topic = "AI"

↓

Explain AI.
```

---

# Multiple Variables

Template:

```text
Explain {topic} for a {audience}.
```

Example:

```text
topic = "Python"
audience = "Beginner"

↓

Explain Python for a Beginner.
```

---

# Prompt Lifecycle

```text
Create Template
       │
       ▼
Provide Variables
       │
       ▼
Format Prompt
       │
       ▼
Send to Model
       │
       ▼
Receive Response
```

---

# Real-World Example

### AI Tutor

Template:

```text
You are an AI tutor.

Explain {topic} for a student studying in {grade}.
```

Input:

```text
topic = "Photosynthesis"
grade = "8th Grade"
```

Final Prompt:

```text
You are an AI tutor.

Explain Photosynthesis for a student studying in 8th Grade.
```

---

# Benefits

* Reusable
* Flexible
* Easy to update
* Reduces duplicate prompts
* Supports personalization

---

# Best Practices

* ✅ Keep prompts simple and specific.
* ✅ Use meaningful variable names.
* ✅ Reuse templates across the application.
* ✅ Store templates in a dedicated `prompts/` folder.
* ✅ Separate prompts from business logic.

---

# Common Mistakes

* ❌ Hardcoding prompts everywhere.
* ❌ Using unclear variable names.
* ❌ Creating duplicate templates.
* ❌ Mixing prompt text with application logic.
* ❌ Forgetting to provide required variables.

---

# Data Flow

```text
User Input
     │
     ▼
Prompt Template
     │
     ▼
Fill Variables
     │
     ▼
Formatted Prompt
     │
     ▼
Chat Model
     │
     ▼
AI Response
```

---

# Key Takeaways

* Prompt Templates create **dynamic, reusable prompts**.
* Variables make prompts flexible and personalized.
* Templates improve readability and maintainability.
* Separate prompt definitions from application code.

---

# Interview Questions

1. What is a Prompt Template?
2. Why use Prompt Templates instead of hardcoded prompts?
3. What are placeholders (variables)?
4. What is the difference between static and dynamic prompts?
5. What happens after a template is formatted?
6. Why should prompts be stored separately?
7. Can a template contain multiple variables?
8. How do Prompt Templates improve maintainability?
9. What happens if a required variable is missing?
10. Why are Prompt Templates important in production applications?

---

# Mini Quiz

1. What is the main purpose of a Prompt Template?
2. What are placeholders used for?
3. Which type of prompt is reusable: static or dynamic?
4. Can one template contain multiple variables?
5. True or False: Prompt Templates reduce code duplication.

---

# Lesson Summary

```text
Prompt Template
      │
      ▼
Insert Variables
      │
      ▼
Formatted Prompt
      │
      ▼
Chat Model
      │
      ▼
Response
```

* **Prompt Template = Reusable prompt**
* **Variables = Dynamic values**
* **Formatted Prompt = Final prompt sent to the model**
* Prompt Templates improve **reusability, maintainability, and scalability** in LangChain applications.
