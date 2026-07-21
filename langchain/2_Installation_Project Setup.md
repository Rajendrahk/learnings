# Chapter 2: Installation & Project Setup

> **Goal:** By the end of this chapter, you will have a modern LangChain development environment, understand Python virtual environments, install LangChain using multiple package managers, securely manage API keys, and run your first LangChain application.

---

# Why Proper Project Setup Matters

AI projects often depend on:

* Multiple Python packages
* Different LLM providers
* API keys
* Vector databases
* Embedding models
* Environment variables

A clean project setup helps you:

* Avoid dependency conflicts
* Reproduce projects easily
* Keep secrets secure
* Scale from prototypes to production

---

# Prerequisites

Before installing LangChain, ensure you have:

| Requirement | Recommended Version                  |
| ----------- | ------------------------------------ |
| Python      | **3.10+** (3.11 or 3.12 recommended) |
| pip         | Latest version                       |
| Git         | Latest version                       |
| Code Editor | VS Code, PyCharm, or similar         |
| Terminal    | PowerShell, Bash, Zsh, etc.          |

Check your Python version:

```bash
python --version
```

Expected output:

```text
Python 3.12.4
```

Check `pip`:

```bash
pip --version
```

---

# Understanding Virtual Environments

## What Is a Virtual Environment?

A **virtual environment** is an isolated Python environment with its own installed packages.

Without one, packages are installed globally, which can lead to version conflicts between projects.

### Analogy

Think of each project as its own kitchen:

* Each kitchen has its own ingredients.
* Recipes don't interfere with each other.
* Updating ingredients in one kitchen doesn't affect another.

---

## Why Use a Virtual Environment?

* Prevent dependency conflicts
* Keep projects isolated
* Easier collaboration
* Simpler deployment
* Cleaner upgrades

---

## Creating a Virtual Environment

### Windows

```bash
python -m venv .venv
```

Activate:

```bash
.venv\Scripts\activate
```

---

### macOS / Linux

```bash
python3 -m venv .venv
```

Activate:

```bash
source .venv/bin/activate
```

Expected prompt:

```text
(.venv) $
```

---

> 💡 **Tip:** Name your virtual environment `.venv`. Many editors (including VS Code) detect it automatically.

---

# Installing LangChain with pip

Upgrade `pip` first:

```bash
python -m pip install --upgrade pip
```

Install the core packages:

```bash
pip install langchain langchain-core langchain-community
```

For OpenAI support:

```bash
pip install langchain-openai
```

For Anthropic:

```bash
pip install langchain-anthropic
```

For Google Gemini:

```bash
pip install langchain-google-genai
```

For Ollama:

```bash
pip install langchain-ollama
```

For Hugging Face:

```bash
pip install langchain-huggingface
```

Install `python-dotenv` for environment variables:

```bash
pip install python-dotenv
```

---

# Installing with uv

`uv` is a fast Python package manager and installer written in Rust.

## Install uv

```bash
pip install uv
```

Create a project:

```bash
uv init my-langchain-app
```

Enter the project:

```bash
cd my-langchain-app
```

Create a virtual environment:

```bash
uv venv
```

Activate it:

**Windows**

```bash
.venv\Scripts\activate
```

**Linux/macOS**

```bash
source .venv/bin/activate
```

Install packages:

```bash
uv add langchain
uv add langchain-openai
uv add python-dotenv
```

---

# Installing with Poetry

Install Poetry:

```bash
pip install poetry
```

Create a project:

```bash
poetry new my-langchain-app
```

Move into the project:

```bash
cd my-langchain-app
```

Install dependencies:

```bash
poetry add langchain
poetry add langchain-openai
poetry add python-dotenv
```

Activate the environment:

```bash
poetry shell
```

---

# Comparing Package Managers

| Feature               | pip   | uv        | Poetry    |
| --------------------- | ----- | --------- | --------- |
| Built into Python     | ✅     | ❌         | ❌         |
| Very fast installs    | ❌     | ✅         | ⚠️ Good   |
| Dependency resolution | Basic | Excellent | Excellent |
| Lock file             | ❌     | ✅         | ✅         |
| Project management    | ❌     | Limited   | ✅         |
| Beginner friendly     | ✅     | ✅         | Moderate  |

---

# Recommended Project Structure

```text
my-langchain-app/
│
├── .venv/
├── .env
├── .gitignore
├── pyproject.toml
├── requirements.txt
├── README.md
│
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── prompts.py
│   ├── chains.py
│   ├── tools.py
│   ├── agents.py
│   └── config.py
│
├── data/
│   ├── pdfs/
│   ├── docs/
│   └── embeddings/
│
├── tests/
│
└── notebooks/
```

---

# Environment Variables

## Why Use Environment Variables?

Never hardcode secrets such as API keys in your source code.

**Bad:**

```python
api_key = "sk-123456789..."
```

**Good:**

Store them in a `.env` file.

Example:

```text
OPENAI_API_KEY=your_api_key_here
ANTHROPIC_API_KEY=your_api_key_here
GOOGLE_API_KEY=your_api_key_here
LANGSMITH_API_KEY=your_api_key_here
```

---

# Loading Environment Variables

Install:

```bash
pip install python-dotenv
```

Example:

```python
# Import the load_dotenv function
from dotenv import load_dotenv

# Import os to access environment variables
import os

# Load variables from the .env file
load_dotenv()

# Read the API key
api_key = os.getenv("OPENAI_API_KEY")

print(api_key is not None)
```

Expected output:

```text
True
```

---

# Protecting Secrets with `.gitignore`

Create a `.gitignore` file:

```gitignore
# Virtual environment
.venv/

# Environment variables
.env

# Python cache
__pycache__/

*.pyc

# IDE settings
.vscode/
.idea/
```

---

> ⚠️ **Common Mistake:** Accidentally committing your `.env` file to Git can expose API keys. Always include `.env` in `.gitignore`.

---

# Installing Optional Packages

Depending on your use case, you may need additional integrations.

| Purpose  | Package           |
| -------- | ----------------- |
| PDFs     | `pypdf`           |
| DOCX     | `python-docx`     |
| HTML     | `beautifulsoup4`  |
| Markdown | `markdown`        |
| ChromaDB | `chromadb`        |
| FAISS    | `faiss-cpu`       |
| Qdrant   | `qdrant-client`   |
| Pinecone | `pinecone`        |
| Weaviate | `weaviate-client` |

Example:

```bash
pip install pypdf chromadb faiss-cpu
```

---

# Your First LangChain Program

Install prerequisites:

```bash
pip install langchain langchain-openai python-dotenv
```

Create `main.py`:

```python
# Load environment variables from the .env file
from dotenv import load_dotenv

# Import the OpenAI chat model wrapper
from langchain_openai import ChatOpenAI

# Load variables into the environment
load_dotenv()

# Create a chat model instance
model = ChatOpenAI(
    model="gpt-4.1-mini",
    temperature=0
)

# Send a prompt to the model
response = model.invoke("Explain LangChain in one sentence.")

# Print the response content
print(response.content)
```

### Expected Output

```text
LangChain is a framework for building applications that combine language models with tools, data sources, and workflows.
```

### Code Walkthrough

* `load_dotenv()` loads environment variables from `.env`.
* `ChatOpenAI` creates a model client.
* `temperature=0` makes responses more deterministic.
* `invoke()` sends the prompt and returns an AI message.
* `response.content` contains the generated text.

---

# Common Installation Errors

## Error: `ModuleNotFoundError`

```text
ModuleNotFoundError: No module named 'langchain'
```

**Cause:** Package not installed in the active environment.

**Fix:**

```bash
pip install langchain
```

Ensure your virtual environment is activated.

---

## Error: Missing API Key

```text
AuthenticationError
```

**Cause:** API key is missing or invalid.

**Fix:**

* Verify your `.env` file.
* Confirm the variable name (for example, `OPENAI_API_KEY`).
* Reload the environment.

---

## Error: Wrong Python Interpreter

Your editor may be using a different Python installation than your terminal.

**Fix:**

* Select the correct interpreter in your IDE.
* Ensure it points to the `.venv` environment.

---

## Error: Dependency Conflicts

**Fix:**

```bash
pip freeze > requirements.txt
```

or, if using Poetry or `uv`, rely on the generated lock file to ensure consistent dependency versions.

---

# Verifying Your Installation

Run:

```bash
python main.py
```

If you receive a model response without errors, your setup is complete.

---

> 💡 **Tip:** Keep separate `.env` files (or equivalent secret management) for development, testing, and production environments.

> ⚠️ **Common Mistakes**
>
> * Installing packages outside the virtual environment.
> * Hardcoding API keys.
> * Forgetting to activate the virtual environment.
> * Mixing package managers within the same project without understanding the implications.
> * Ignoring dependency versions in collaborative projects.

> ✅ **Best Practices**
>
> * Use Python 3.11 or newer when possible.
> * Create a new virtual environment for each project.
> * Store secrets in environment variables.
> * Commit dependency manifests (`requirements.txt`, `pyproject.toml`, or lock files) to version control.
> * Organize your project into modules as it grows.

> 🚀 **Pro Tips**
>
> * Consider `uv` for faster dependency installation in new projects.
> * Use `temperature=0` during development for more predictable outputs.
> * Pin dependency versions for production deployments.
> * Add automated tests early, even for simple prompt pipelines.

---

# Chapter Summary

In this chapter, you learned:

* Why virtual environments are essential.
* How to install LangChain using `pip`, `uv`, and Poetry.
* How to structure a LangChain project.
* How to manage API keys securely with `.env`.
* How to install common integration packages.
* How to write and run your first LangChain application.
* How to troubleshoot common installation issues.

---

## What's Next?

In **Chapter 3: Core Concepts**, you'll explore the foundational building blocks of LangChain, including:

* LLMs and Chat Models
* Messages
* Prompts and Prompt Templates
* Output Parsers
* Runnables and LCEL
* Chains
* Memory
* Tools
* Agents
* Retrievers
* Documents
* Embeddings
* Vector Stores
* Callbacks
* Streaming
* Async
* Middleware

These concepts form the foundation for everything you'll build with LangChain.
