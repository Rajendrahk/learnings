# Phase 2 – Lesson 1: Models

## Learning Objective

Understand:

* What a Model is in LangChain
* Types of models
* How LangChain interacts with models
* Model providers and integrations
* Basic model workflow

---

# What is a Model?

A **Model** is the AI engine that processes input and generates output.

> **Think of the model as the "brain" of your AI application.**

LangChain does **not** provide models—it connects your application to models from different providers.

---

# Model Workflow

```text
User Input
     │
     ▼
 LangChain
     │
     ▼
 Chat Model (LLM)
     │
     ▼
 AI Response
```

---

# Types of Models

## 1. Chat Models (Most Common)

Designed for conversational interactions using messages.

Examples:

* OpenAI GPT
* Google Gemini
* Anthropic Claude
* Ollama
* Llama
* Mistral

Example:

```text
Human: Explain Python.
AI: Python is a programming language...
```

---

## 2. Text Completion Models (Legacy)

Generate text from a plain prompt.

```text
Prompt:
Complete this sentence...

↓

Generated Text
```

> Modern LangChain applications primarily use **Chat Models**.

---

# Popular Model Providers

| Provider      | Package                  |
| ------------- | ------------------------ |
| OpenAI        | `langchain-openai`       |
| Google Gemini | `langchain-google-genai` |
| Ollama        | `langchain-ollama`       |
| Anthropic     | `langchain-anthropic`    |
| Mistral       | `langchain-mistralai`    |

---

# Model Initialization

Typical steps:

```text
Install Provider
      │
      ▼
Configure API Key
      │
      ▼
Create Model
      │
      ▼
Invoke Model
      │
      ▼
Receive Response
```

---

# Basic Data Flow

```text
User
 │
 ▼
Prompt
 │
 ▼
Chat Model
 │
 ▼
AI Response
```

---

# Common Model Parameters

| Parameter     | Purpose                                        |
| ------------- | ---------------------------------------------- |
| `model`       | Selects the model (e.g., GPT-4, Gemini, Llama) |
| `temperature` | Controls creativity                            |
| `max_tokens`  | Limits response length                         |
| `timeout`     | Maximum request duration                       |
| `max_retries` | Retry failed requests                          |

---

# Temperature

Controls randomness in responses.

| Temperature | Behavior               |
| ----------- | ---------------------- |
| **0.0**     | Deterministic, factual |
| **0.3**     | Low creativity         |
| **0.7**     | Balanced               |
| **1.0+**    | Highly creative        |

**Use Cases**

* 0.0 → Code generation, factual Q&A
* 0.7 → General chat
* 1.0 → Creative writing

---

# Model Invocation

Basic flow:

```text
Create Model
      │
      ▼
Invoke
      │
      ▼
Response Object
      │
      ▼
Extract Content
```

---

# Response Flow

```text
User Question
       │
       ▼
LangChain
       │
       ▼
Chat Model
       │
       ▼
AI Message
       │
       ▼
Display Response
```

---

# Local vs Cloud Models

## Cloud Models

Examples:

* OpenAI
* Gemini
* Claude

**Pros**

* High quality
* No local hardware required
* Frequently updated

**Cons**

* Internet required
* API costs
* Data leaves your environment

---

## Local Models

Examples:

* Ollama
* Llama
* Mistral

**Pros**

* Privacy
* Offline usage
* No API cost

**Cons**

* Requires local hardware
* Slower on low-end systems
* Manual model management

---

# Best Practices

* ✅ Choose Chat Models for new applications.
* ✅ Keep API keys in `.env`.
* ✅ Use low temperature for deterministic tasks.
* ✅ Reuse model instances instead of creating new ones repeatedly.
* ✅ Select the model based on your use case (speed, cost, quality).

---

# Common Mistakes

* ❌ Thinking LangChain includes its own models.
* ❌ Setting temperature too high for factual tasks.
* ❌ Hardcoding API keys.
* ❌ Recreating the model for every request.
* ❌ Confusing Chat Models with Text Completion models.

---

# Key Takeaways

* A **Model** is the AI engine that generates responses.
* LangChain acts as a wrapper around different model providers.
* Modern LangChain applications primarily use **Chat Models**.
* Model behavior can be customized using parameters like **temperature** and **max_tokens**.
* You can switch providers with minimal changes thanks to LangChain's unified interface.

---

# Interview Questions

1. What is a Model in LangChain?
2. Does LangChain provide its own LLM?
3. What is the difference between Chat Models and Text Completion Models?
4. What does the `temperature` parameter control?
5. When would you use a temperature of 0?
6. What are the advantages of local models?
7. What are the advantages of cloud models?
8. Why is LangChain's unified model interface useful?
9. Why should model instances be reused?
10. What factors influence model selection?

---

# Mini Quiz

1. What is the role of a Model in LangChain?
2. Name three model providers supported by LangChain.
3. Which parameter controls creativity?
4. Which type of model is recommended for modern LangChain applications?
5. True or False: LangChain includes its own LLM.

---

# Lesson Summary

```text
User
 │
 ▼
Prompt
 │
 ▼
LangChain
 │
 ▼
Chat Model
 │
 ▼
AI Response
```

* **Model = Brain**
* **LangChain = Connector/Framework**
* **Chat Models** are the standard choice for modern AI applications.
* Configure model behavior using parameters such as **temperature**, **max_tokens**, and **timeout**.
* LangChain provides a consistent interface across multiple LLM providers.
