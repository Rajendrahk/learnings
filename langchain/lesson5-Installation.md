# Lesson 5: Installation

## Learning Objective

Learn how to set up a LangChain development environment using Python.

---

# Prerequisites

* Python **3.10+** (Recommended: **3.11 or 3.12**)
* VS Code (or any IDE)
* Git (optional)
* Internet connection
* API Key (OpenAI, Gemini, etc.) **or** Ollama for local models

---

# Create a Project

```bash
mkdir langchain-learning
cd langchain-learning
```

---

# Create a Virtual Environment

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

# Upgrade pip

```bash
python -m pip install --upgrade pip
```

---

# Install LangChain

```bash
pip install langchain
```

> Installs the core LangChain framework.

---

# Install a Model Provider

Choose based on your LLM.

### OpenAI

```bash
pip install langchain-openai openai
```

### Google Gemini

```bash
pip install langchain-google-genai
```

### Ollama (Local Models)

```bash
pip install langchain-ollama ollama
```

### Anthropic Claude

```bash
pip install langchain-anthropic
```

---

# Install Common Packages

```bash
pip install python-dotenv
pip install pydantic
pip install faiss-cpu
pip install chromadb
pip install tiktoken
```

These are commonly used for:

* Environment variables
* Data validation
* Vector databases
* Token counting

---

# Verify Installation

```bash
python
```

```python
import langchain
print(langchain.__version__)
```

If no errors occur, the installation is successful.

---

# Store API Keys Securely

Create a **`.env`** file.

```text
OPENAI_API_KEY=your_key_here
GOOGLE_API_KEY=your_key_here
```

Load it in Python:

```python
from dotenv import load_dotenv

load_dotenv()
```

> **Never hardcode API keys** in your source code.

---

# Recommended Project Structure

```text
langchain-learning/
│
├── .venv/
├── .env
├── requirements.txt
├── app.py
├── README.md
└── src/
```

As projects grow:

```text
src/
├── prompts/
├── chains/
├── tools/
├── retrievers/
├── utils/
└── main.py
```

---

# Freeze Dependencies

Save installed packages:

```bash
pip freeze > requirements.txt
```

Reinstall later:

```bash
pip install -r requirements.txt
```

---

# Check Installed Packages

```bash
pip list
```

---

# Common Installation Issues

| Issue                          | Solution                                                                 |
| ------------------------------ | ------------------------------------------------------------------------ |
| `ModuleNotFoundError`          | Install the missing package using `pip install`                          |
| Wrong Python version           | Use Python 3.10+                                                         |
| Virtual environment not active | Activate `.venv` before running code                                     |
| API key not found              | Check `.env` and call `load_dotenv()`                                    |
| Import errors                  | Ensure provider-specific package is installed (e.g., `langchain-openai`) |

---

# Best Practices

* ✅ Use a virtual environment for every project.
* ✅ Store secrets in a `.env` file.
* ✅ Install only the provider packages you need.
* ✅ Keep dependencies in `requirements.txt`.
* ✅ Use the latest stable versions unless a project requires specific versions.

---

# Key Takeaways

* Install the **LangChain core** package first.
* Install **provider-specific integrations** (OpenAI, Gemini, Ollama, etc.) separately.
* Use a virtual environment and `.env` for clean, secure development.
* Maintain reproducible projects with `requirements.txt`.

---

# Interview Questions

1. Why should you use a virtual environment?
2. Why is LangChain split into provider-specific packages?
3. What is the purpose of a `.env` file?
4. How do you recreate a project's dependencies?
5. Why shouldn't API keys be hardcoded?
6. What is `python-dotenv` used for?
7. How do you verify a package installation?
8. What is `requirements.txt`?
9. Why might `ModuleNotFoundError` occur?
10. Which package would you install to use Ollama with LangChain?

---

# Mini Quiz

1. Which command creates a virtual environment?
2. Which file should store API keys?
3. What command installs dependencies from a project?
4. Which package loads environment variables?
5. True or False: `langchain` alone is enough to use OpenAI or Ollama.

---

# Lesson Summary

```text
Create Project
      ↓
Create Virtual Environment
      ↓
Activate Environment
      ↓
Install LangChain
      ↓
Install LLM Provider Package
      ↓
Create .env
      ↓
Verify Installation
      ↓
Start Building
```

> **Important:** Modern LangChain is modular. The `langchain` package provides the framework, while integrations such as `langchain-openai`, `langchain-ollama`, and `langchain-google-genai` are installed separately based on the models you plan to use.
