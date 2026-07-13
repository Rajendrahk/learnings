# Lesson 4: LangChain Architecture

## Learning Objective

Understand:

* The high-level architecture of LangChain
* Core building blocks
* How data flows through a LangChain application
* Why the architecture is modular

---

# What is LangChain Architecture?

LangChain is built using **independent, reusable components** that work together to create AI applications.

```text
                User
                  │
                  ▼
          Prompt Template
                  │
                  ▼
               Messages
                  │
                  ▼
              Chat Model
                  │
      ┌───────────┼───────────┐
      ▼           ▼           ▼
   Tools      Retriever    Memory
      │           │           │
      └───────────┼───────────┘
                  ▼
           Output Parser
                  │
                  ▼
            Final Response
```

---

# Core Components

| Component                 | Purpose                                   |
| ------------------------- | ----------------------------------------- |
| **Models**                | Generate AI responses                     |
| **Prompt Templates**      | Create dynamic prompts                    |
| **Messages**              | Structure chat conversations              |
| **Output Parsers**        | Convert model output into structured data |
| **Runnables**             | Connect components into workflows         |
| **Tools**                 | Enable API calls and external actions     |
| **Retrievers**            | Fetch relevant information                |
| **Memory / Chat History** | Maintain conversation context             |
| **Callbacks**             | Monitor and debug execution               |

---

# Architecture Layers

## 1. Application Layer

* User Interface (Streamlit, FastAPI, Web App)
* Receives user input
* Displays responses

```text
User
 │
 ▼
Application
```

---

## 2. Prompt Layer

Creates prompts dynamically.

```text
User Question
      │
      ▼
Prompt Template
      │
      ▼
Formatted Prompt
```

Example:

```text
Explain {topic} in simple terms.
```

Input:

```text
topic = "LangChain"
```

Output:

```text
Explain LangChain in simple terms.
```

---

## 3. Model Layer

The prompt is sent to an LLM.

Supported models include:

* OpenAI GPT
* Google Gemini
* Anthropic Claude
* Ollama
* Llama
* Mistral

```text
Prompt
   │
   ▼
Chat Model
   │
   ▼
Response
```

---

## 4. Retrieval Layer (Optional)

Provides external knowledge to the LLM.

Typical RAG pipeline:

```text
PDF / Database
       │
       ▼
Embeddings
       │
       ▼
Vector Database
       │
       ▼
Retriever
       │
       ▼
Relevant Documents
```

---

## 5. Tool Layer (Optional)

Allows the LLM to interact with external systems.

Examples:

* Weather API
* Calculator
* SQL Database
* Search Engine
* Email Service

```text
Question
   │
   ▼
Tool
   │
   ▼
External System
   │
   ▼
Result
```

---

## 6. Memory Layer (Optional)

Stores conversation history.

```text
User
 │
 ▼
Conversation History
 │
 ▼
LLM
```

Example:

```text
User: My name is Raj.
User: What is my name?

Without Memory → I don't know.
With Memory → Your name is Raj.
```

---

## 7. Output Layer

Converts raw model output into the required format.

Possible outputs:

* Plain text
* JSON
* Python objects
* Lists
* Tables

```text
LLM Response
      │
      ▼
Output Parser
      │
      ▼
Structured Output
```

---

# End-to-End Data Flow

```text
User
 │
 ▼
Prompt Template
 │
 ▼
Messages
 │
 ▼
Retriever (Optional)
 │
 ▼
Tools (Optional)
 │
 ▼
Chat Model
 │
 ▼
Output Parser
 │
 ▼
Application
 │
 ▼
User
```

---

# Why is LangChain Modular?

Each component has a **single responsibility**.

Example:

* Change the LLM without changing prompts.
* Replace the vector database without changing retrieval logic.
* Add memory without rewriting the application.

Benefits:

* Reusable
* Maintainable
* Scalable
* Easy to test
* Easy to extend

---

# High-Level Project Architecture

```text
                  User
                    │
                    ▼
          Streamlit / FastAPI
                    │
                    ▼
            LangChain Pipeline
                    │
    ┌─────────┬──────────┬─────────┐
    ▼         ▼          ▼
 Prompt    Retriever    Tools
    │         │          │
    └─────────┼──────────┘
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

# Key Takeaways

* LangChain uses a **modular architecture**.
* Every component has a specific responsibility.
* Components can be added, removed, or replaced independently.
* The application sends prompts to an LLM and optionally uses retrieval, tools, and memory before returning a response.
* This design makes AI applications flexible and maintainable.

---

# Common Mistakes

* ❌ Assuming every application needs every component.
* ❌ Mixing prompt logic with business logic.
* ❌ Treating memory as permanent storage.
* ❌ Calling tools when the LLM alone can answer.
* ❌ Hardcoding prompts instead of using templates.

---

# Interview Questions

1. What is LangChain's architecture?
2. Why is LangChain modular?
3. What is the role of Prompt Templates?
4. What does a Retriever do?
5. When would you use Tools?
6. What is the purpose of Output Parsers?
7. What are Runnables?
8. Can LangChain work without Retrieval?
9. Why is Memory optional?
10. Explain the data flow in a LangChain application.

---

# Mini Quiz

1. Which component formats user input before sending it to the model?
2. Which component fetches relevant documents?
3. Which component allows API calls?
4. What is the purpose of an Output Parser?
5. True or False: Every LangChain application must use retrieval and memory.

---

# Lesson Summary

* LangChain follows a **modular, pipeline-based architecture**.
* Core flow:

```text
User
   ↓
Prompt Template
   ↓
Messages
   ↓
Chat Model
   ↓
Output Parser
   ↓
Response
```

* Optional components such as **Retrievers, Tools, and Memory** extend the capabilities of the application without changing the core pipeline.
* Understanding this architecture is essential before learning each component individually in the upcoming lessons.
