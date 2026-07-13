# Phase 2 – Lesson 5: Chains

## Learning Objective

Understand:

* What Chains are
* Why Chains are needed
* How data flows through a Chain
* Types of Chains
* Benefits and best practices

---

# What is a Chain?

A **Chain** is a sequence of connected steps where the **output of one step becomes the input of the next**.

> **Think of a Chain as an assembly line in a factory.**

---

# Real-World Analogy

Making tea:

```text
Boil Water
     │
     ▼
Add Tea Leaves
     │
     ▼
Add Milk
     │
     ▼
Add Sugar
     │
     ▼
Serve Tea
```

Each step depends on the previous one.

Similarly, an AI application performs multiple connected steps.

---

# Why Do We Need Chains?

A real AI application rarely makes just one LLM call.

It may need to:

* Format a prompt
* Retrieve documents
* Call an LLM
* Parse the response
* Return structured output

Chains connect these steps into one workflow.

---

# Chain Workflow

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
Final Response
```

---

# Simple Chain

```text
Question
    │
    ▼
Prompt
    │
    ▼
LLM
    │
    ▼
Answer
```

Example:

```
Input:
Explain Python.

↓

Output:
Python is a high-level programming language...
```

---

# Multi-Step Chain

```text
User Question
       │
       ▼
Prompt Template
       │
       ▼
Retriever
       │
       ▼
Chat Model
       │
       ▼
Output Parser
       │
       ▼
Application
```

Each component performs one specific task.

---

# Chain Components

| Component       | Purpose                |
| --------------- | ---------------------- |
| Prompt Template | Build the prompt       |
| Retriever       | Fetch relevant data    |
| Chat Model      | Generate response      |
| Output Parser   | Structure the response |

---

# Data Flow

```text
Input
  │
  ▼
Step 1
  │
  ▼
Step 2
  │
  ▼
Step 3
  │
  ▼
Output
```

Every step receives input from the previous step.

---

# Types of Chains

## 1. Sequential Chain

Steps execute one after another.

```text
Prompt
   │
   ▼
LLM
   │
   ▼
Parser
```

---

## 2. Retrieval Chain (RAG)

Adds external knowledge before calling the model.

```text
Question
    │
    ▼
Retriever
    │
    ▼
Relevant Documents
    │
    ▼
LLM
    │
    ▼
Answer
```

---

## 3. Tool Chain

Uses external tools.

```text
Question
    │
    ▼
Tool
    │
    ▼
Result
    │
    ▼
LLM
```

Example tools:

* Weather API
* Calculator
* SQL Database
* Search Engine

---

# Why Chains Are Powerful

Without Chains:

```text
Prompt
↓

LLM
```

With Chains:

```text
Prompt
   │
   ▼
Retriever
   │
   ▼
Tool
   │
   ▼
LLM
   │
   ▼
Parser
```

You can build sophisticated AI workflows by composing simple components.

---

# Benefits

* Modular
* Reusable
* Easy to test
* Easy to maintain
* Scalable
* Readable

---

# Chains in Modern LangChain

> **Important:** In modern LangChain, **Chains are built using the Runnable interface and LCEL (LangChain Expression Language).**

Older classes like `LLMChain` are considered legacy.

Modern approach:

```text
Prompt
   │
   ▼
Model
   │
   ▼
Output Parser
```

Connected using **Runnables**.

---

# Best Practices

* ✅ Keep each step focused on one responsibility.
* ✅ Reuse prompts and models.
* ✅ Parse outputs before using them.
* ✅ Separate retrieval from generation.
* ✅ Prefer LCEL/Runnables for new applications.

---

# Common Mistakes

* ❌ Putting all logic into one prompt.
* ❌ Creating very long, hard-to-maintain chains.
* ❌ Mixing retrieval, prompting, and parsing logic.
* ❌ Ignoring output validation.
* ❌ Using deprecated chain classes in new projects.

---

# Key Takeaways

* A Chain is a sequence of connected processing steps.
* The output of one step becomes the input to the next.
* Chains make AI applications modular and maintainable.
* Modern LangChain builds Chains using **Runnables** and **LCEL**.

---

# Interview Questions

1. What is a Chain in LangChain?
2. Why are Chains useful?
3. What is the difference between a simple and a multi-step Chain?
4. What is a Retrieval Chain?
5. What is a Tool Chain?
6. Why are legacy chain classes discouraged?
7. How do Chains improve maintainability?
8. What role does an Output Parser play in a Chain?
9. What are the benefits of modular workflows?
10. How are Chains implemented in modern LangChain?

---

# Mini Quiz

1. What is a Chain?
2. What happens to the output of one step in a Chain?
3. Which Chain type is commonly used in RAG?
4. Which modern LangChain feature is used to build Chains?
5. True or False: `LLMChain` is the recommended approach for new LangChain applications.

---

# Lesson Summary

```text
User Input
     │
     ▼
Prompt Template
     │
     ▼
Retriever (Optional)
     │
     ▼
Tool (Optional)
     │
     ▼
Chat Model
     │
     ▼
Output Parser
     │
     ▼
Final Response
```

### Types of Chains

| Chain Type           | Purpose                      |
| -------------------- | ---------------------------- |
| **Sequential Chain** | Execute steps in order       |
| **Retrieval Chain**  | Add external knowledge (RAG) |
| **Tool Chain**       | Use external APIs or tools   |

> **Remember:** A **Chain** is not a single component—it is a **workflow**. In modern LangChain, workflows are built by composing **Runnables** using **LCEL**, making applications more modular, reusable, and easier to maintain.
