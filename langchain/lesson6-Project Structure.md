# Lesson 6: Project Structure

## Learning Objective

Learn how to organize a LangChain project for scalability, readability, and maintainability.

---

# Why Project Structure Matters

A good project structure:

* Improves code readability
* Separates responsibilities
* Makes debugging easier
* Simplifies testing
* Scales as the project grows

---

# Small Project Structure

Suitable for learning and simple applications.

```text
langchain-project/
│
├── .env                  # API keys and secrets
├── requirements.txt      # Project dependencies
├── README.md             # Project documentation
├── app.py                # Main application entry point
└── utils.py              # Helper functions
```

---

# Recommended Project Structure

Suitable for production-ready applications.

```text
langchain-project/
│
├── .env
├── requirements.txt
├── README.md
├── main.py
│
├── config/
│   ├── settings.py
│   └── logging.py
│
├── models/
│   └── llm.py
│
├── prompts/
│   ├── chat_prompt.py
│   └── system_prompt.py
│
├── chains/
│   └── qa_chain.py
│
├── tools/
│   ├── calculator.py
│   └── weather.py
│
├── retrievers/
│   └── vector_store.py
│
├── loaders/
│   └── pdf_loader.py
│
├── memory/
│   └── chat_history.py
│
├── parsers/
│   └── output_parser.py
│
├── utils/
│   └── helpers.py
│
├── data/
│   ├── documents/
│   └── embeddings/
│
└── tests/
    └── test_app.py
```

---

# Folder Responsibilities

| Folder        | Purpose                         |
| ------------- | ------------------------------- |
| `config/`     | Configuration and logging       |
| `models/`     | LLM initialization              |
| `prompts/`    | Prompt templates                |
| `chains/`     | LangChain pipelines/workflows   |
| `tools/`      | External APIs and utilities     |
| `retrievers/` | RAG retrieval logic             |
| `loaders/`    | Load PDFs, web pages, files     |
| `memory/`     | Chat history/session management |
| `parsers/`    | Structured output parsing       |
| `utils/`      | Shared helper functions         |
| `data/`       | Documents, embeddings, datasets |
| `tests/`      | Unit and integration tests      |

---

# Data Flow

```text
User
 │
 ▼
main.py
 │
 ▼
Prompt Template
 │
 ▼
Retriever (Optional)
 │
 ▼
Tools (Optional)
 │
 ▼
LLM
 │
 ▼
Output Parser
 │
 ▼
Response
```

---

# Example File Responsibilities

### `main.py`

* Application entry point
* Receives user input
* Invokes the LangChain pipeline

---

### `models/llm.py`

* Configure the LLM
* Store model settings
* Reuse across the project

---

### `prompts/`

Store reusable prompt templates.

Example:

```text
You are an AI tutor.
Explain {topic} in simple language.
```

---

### `chains/`

Contains application workflows.

Example:

```text
User Question
      │
      ▼
Prompt
      │
      ▼
LLM
      │
      ▼
Response
```

---

### `tools/`

Contains external integrations.

Examples:

* Calculator
* Weather API
* Search API
* SQL Database
* Email Service

---

### `retrievers/`

Handles Retrieval-Augmented Generation (RAG).

```text
PDF
 │
 ▼
Embeddings
 │
 ▼
Vector Database
 │
 ▼
Retriever
```

---

### `memory/`

Stores conversation history.

Example:

```text
User: My name is Raj.
Assistant: Nice to meet you.

↓

Later...

User: What is my name?

↓

Assistant: Raj
```

---

### `parsers/`

Converts model output into structured formats.

Examples:

* JSON
* Lists
* Tables
* Python objects

---

# Configuration Files

## `.env`

Store secrets securely.

```text
OPENAI_API_KEY=...
GOOGLE_API_KEY=...
```

---

## `requirements.txt`

Project dependencies.

```text
langchain
langchain-openai
python-dotenv
```

---

## `README.md`

Include:

* Project overview
* Installation steps
* Usage instructions
* Folder structure
* Example commands

---

# Best Practices

* ✅ Keep prompts separate from business logic.
* ✅ Store secrets in `.env`.
* ✅ Use reusable modules.
* ✅ Keep functions small and focused.
* ✅ Add tests as the project grows.
* ✅ Separate configuration from application code.

---

# Common Mistakes

* ❌ Putting all code in one file.
* ❌ Hardcoding API keys.
* ❌ Mixing prompt, retrieval, and business logic.
* ❌ Duplicating LLM initialization.
* ❌ Ignoring project documentation.

---

# Key Takeaways

* Organize projects by **responsibility**, not by file size.
* Keep prompts, models, tools, and retrieval logic separate.
* A modular structure makes projects easier to maintain and extend.
* Start simple, then evolve the structure as your application grows.

---

# Interview Questions

1. Why is project structure important?
2. What belongs in the `prompts/` folder?
3. Why should LLM initialization be centralized?
4. What is the purpose of the `retrievers/` folder?
5. Why keep API keys in `.env`?
6. What should `chains/` contain?
7. Where should helper functions be stored?
8. Why maintain a `tests/` folder?
9. What belongs in `config/`?
10. How does modularity improve maintainability?

---

# Mini Quiz

1. Which folder stores prompt templates?
2. Where should LLM initialization be placed?
3. Which folder contains RAG logic?
4. Where should API keys be stored?
5. True or False: All LangChain code should be written in `main.py`.

---

# Lesson Summary

```text
Project
 │
 ├── Configuration
 ├── Models
 ├── Prompts
 ├── Chains
 ├── Tools
 ├── Retrievers
 ├── Memory
 ├── Parsers
 ├── Data
 └── Tests
```

A well-structured project is easier to **develop, debug, test, and scale**, especially as AI applications become more complex.

---

## 🎉 Phase 1 Complete

You have completed the **Foundations** phase and now understand:

* ✅ What LangChain is
* ✅ Why LangChain exists
* ✅ LLMs vs. LangChain
* ✅ LangChain architecture
* ✅ Installation
* ✅ Project structure

**Next Phase:** **Core Components**, where you'll start building real LangChain applications by learning about **Models**, **Prompt Templates**, **Messages**, **Output Parsers**, **Chains**, **Runnables**, and **LCEL**. This is where you'll begin writing and understanding practical code.
