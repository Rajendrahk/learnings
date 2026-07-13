# Lesson 1: What is LangChain?

## Definition
* **LangChain** is a **Python framework** for building applications powered by **Large Language Models (LLMs)**.
* It is **not an AI model**.
* It provides reusable building blocks for creating AI applications.
---
# Real-World Analogy
### AI Assistant Analogy
LangChain acts like a **manager** that coordinates multiple tasks for an AI assistant.
```
User
 │
 ▼
Read PDF
 │
 ▼
Search Database
 │
 ▼
Generate Email
 │
 ▼
Return Result
```
### Restaurant Analogy

```
Customer
    │
    ▼
 Waiter (LangChain)
    │
    ▼
 Kitchen (LLM)
    │
    ▼
 Food (Response)
```
---
# Why LangChain?
Real AI applications need more than just an LLM.

LangChain helps connect:
* Prompt Templates
* LLMs
* Memory
* Document Loaders
* Retrievers
* Vector Databases
* Tools
* Output Parsers
---
# Without LangChain
```
User Input
     │
     ▼
Call LLM API
     │
     ▼
Manage History
     │
     ▼
Search Database
     │
     ▼
Format Prompt
     │
     ▼
Return Response
```
Requires lots of custom code.
---
# With LangChain
```
User
 │
 ▼
Prompt Template
 │
 ▼
LLM
 │
 ▼
Memory
 │
 ▼
Retriever
 │
 ▼
Output Parser
 │
 ▼
Answer
```
LangChain provides ready-made components.
---
# Problems LangChain Solves

| Problem                          | LangChain Solution |
| -------------------------------- | ------------------ |
| LLM forgets conversation         | Memory             |
| Cannot read PDFs                 | Document Loaders   |
| Cannot search company data       | Retrievers         |
| Cannot use APIs/tools            | Tools              |
| Multi-step workflows are complex | Chains             |
---
# Common Use Cases

* AI Chatbots
* PDF Question Answering
* RAG Applications
* Customer Support Bots
* AI Research Assistants
* SQL Database Chat
* AI Coding Assistants
* Multi-Agent Systems
---
# LangChain Architecture (High Level)
```
                    USER

                      │

                      ▼

               LangChain

      ┌─────────┬─────────┬──────────┐
      │         │         │          │
      ▼         ▼         ▼          ▼

 Prompt    Memory    Retriever    Tools

      │         │         │          │
      └─────────┴─────────┴──────────┘

                      │

                      ▼

                     LLM

                      │

                      ▼

                  Final Answer
---
# Key Points
* LangChain is a **framework**, not an LLM.
* It orchestrates multiple AI components.
* It works with many LLM providers:
  * OpenAI
  * Ollama
  * Gemini
  * Anthropic
  * Mistral
  * Llama
---
# Beginner Mental Model
```
LLM = Brain 🧠
LangChain = Manager/Coordinator
```
The LLM generates intelligence, while LangChain manages the workflow.
---
# Common Mistakes
* ❌ LangChain is an AI model.
  * ✅ It is a framework.
* ❌ LangChain only builds chatbots.
  * ✅ It supports many AI applications.
* ❌ LangChain makes the LLM smarter.
  * ✅ It organizes and connects components.
* ❌ LangChain is mandatory.
  * ✅ You can build AI applications without it, but LangChain simplifies development.
---
# Interview Questions
1. What is LangChain?
2. Why was LangChain created?
3. Is LangChain an LLM?
4. What problems does it solve?
5. Name some common LangChain use cases.
6. Can LangChain work with multiple LLM providers?
7. What is the role of Memory?
8. What is the purpose of Retrievers?
9. Why are workflows important in AI applications?
10. When would you choose to build without LangChain?
---

# Mini Quiz
1. Is LangChain an LLM?
2. What is the main purpose of LangChain?
3. Name three LangChain components.
4. In the restaurant analogy, who is LangChain?
5. True or False: LangChain only works with OpenAI.
---

# Lesson Summary
* LangChain is a framework for building LLM-powered applications.
* It connects prompts, models, memory, retrieval, tools, and output handling.
* It reduces boilerplate code and simplifies AI workflows.
* It supports multiple LLM providers.
* Think of **LLM as the brain** and **LangChain as the manager**.
