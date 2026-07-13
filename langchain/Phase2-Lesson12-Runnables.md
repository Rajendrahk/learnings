# Phase 2 – Lesson 6: Runnables

## Learning Objective

Understand:

* What Runnables are
* Why LangChain introduced Runnables
* Types of Runnables
* Common Runnable methods
* How Runnables form the foundation of modern LangChain

---

# What is a Runnable?

A **Runnable** is the **fundamental building block** in modern LangChain.

It represents **any component that accepts an input, performs an operation, and produces an output**.

> **Think of a Runnable as a function with a standardized interface.**

---

# Why Runnables?

Before Runnables, LangChain had many specialized classes (`LLMChain`, `SequentialChain`, etc.).

Problems:

* Too many APIs
* Inconsistent interfaces
* Difficult composition

Runnables introduced a **single, consistent interface** for all components.

---

# Runnable Workflow

```text
Input
  │
  ▼
Runnable
  │
  ▼
Output
```

Every Runnable follows the same pattern.

---

# What Can Be a Runnable?

Almost every LangChain component:

* Prompt Template
* Chat Model
* Output Parser
* Retriever
* Tool
* Entire Chain

Everything can be connected because everything behaves like a Runnable.

---

# Runnable Pipeline

```text
User Input
     │
     ▼
Prompt Template
     │
     ▼
Chat Model
     │
     ▼
Output Parser
     │
     ▼
Final Output
```

Each component is a Runnable.

---

# Common Runnable Methods

| Method      | Purpose                     |
| ----------- | --------------------------- |
| `invoke()`  | Process one input           |
| `batch()`   | Process multiple inputs     |
| `stream()`  | Return output incrementally |
| `ainvoke()` | Async version of `invoke()` |
| `abatch()`  | Async batch processing      |
| `astream()` | Async streaming             |

---

# 1. invoke()

Processes a **single input**.

```text
Input
  │
  ▼
invoke()
  │
  ▼
Output
```

Use for:

* Single user requests
* Chatbots
* APIs

---

# 2. batch()

Processes **multiple inputs** together.

```text
Input 1 ─┐
Input 2 ─┼──► batch()
Input 3 ─┘
              │
              ▼
Multiple Outputs
```

Use for:

* Bulk processing
* Dataset generation
* Parallel requests

---

# 3. stream()

Returns output as it is generated.

```text
LLM
 │
 ▼
H
He
Hel
Hell
Hello
```

Use for:

* Chat interfaces
* Live typing effect
* Better user experience

---

# Runnable Composition

Multiple Runnables can be connected.

```text
Prompt
   │
   ▼
Model
   │
   ▼
Parser
```

The output of one Runnable becomes the input to the next.

---

# Why Runnables Are Powerful

Every component follows the same interface.

This allows easy composition.

```text
Runnable A
      │
      ▼
Runnable B
      │
      ▼
Runnable C
```

No custom glue code is needed.

---

# Data Flow

```text
User
 │
 ▼
Prompt Runnable
 │
 ▼
Model Runnable
 │
 ▼
Parser Runnable
 │
 ▼
Application
```

---

# Benefits

* Consistent API
* Easy composition
* Reusable components
* Async support
* Streaming support
* Better scalability

---

# Runnables vs Chains

| Chains                         | Runnables                 |
| ------------------------------ | ------------------------- |
| High-level workflow            | Individual building block |
| Legacy implementations exist   | Modern standard           |
| Built from multiple components | Represents each component |
| Often created using LCEL       | Foundation of LCEL        |

---

# Best Practices

* ✅ Prefer Runnables in new applications.
* ✅ Compose small Runnables instead of large monolithic workflows.
* ✅ Use `batch()` for multiple requests.
* ✅ Use `stream()` for interactive applications.
* ✅ Use async methods for high-concurrency systems.

---

# Common Mistakes

* ❌ Thinking Runnables replace models.
* ❌ Using legacy Chain classes in new projects.
* ❌ Ignoring streaming for chat applications.
* ❌ Repeating logic instead of composing Runnables.
* ❌ Confusing a Runnable with an entire application.

---

# Key Takeaways

* A Runnable is the core abstraction in modern LangChain.
* Every major component implements the Runnable interface.
* Runnables make composition simple through a consistent API.
* They support synchronous, asynchronous, batch, and streaming execution.

---

# Interview Questions

1. What is a Runnable?
2. Why were Runnables introduced?
3. What is the purpose of `invoke()`?
4. When would you use `batch()`?
5. What is the advantage of `stream()`?
6. Can a Prompt Template be a Runnable?
7. How do Runnables simplify application development?
8. Why are async methods useful?
9. How do Runnables relate to Chains?
10. Why are Runnables considered the foundation of modern LangChain?

---

# Mini Quiz

1. What is a Runnable?
2. Which method processes a single input?
3. Which method processes multiple inputs?
4. Which method supports streaming output?
5. True or False: Prompt Templates and Chat Models are both Runnables.

---

# Lesson Summary

```text
User
 │
 ▼
Prompt Runnable
 │
 ▼
Model Runnable
 │
 ▼
Parser Runnable
 │
 ▼
Response
```

### Common Runnable Methods

| Method      | Use Case               |
| ----------- | ---------------------- |
| `invoke()`  | Single request         |
| `batch()`   | Multiple requests      |
| `stream()`  | Live output            |
| `ainvoke()` | Async single request   |
| `abatch()`  | Async batch processing |
| `astream()` | Async streaming        |

> **Remember:** A **Runnable** is the **standard execution interface** in modern LangChain. Almost every component (Prompt, Model, Retriever, Tool, Parser) is a Runnable, making them easy to connect into powerful AI workflows.
