# Phase 2 – Lesson 3: Messages

## Learning Objective

Understand:

* What Messages are
* Why chat models use messages instead of plain text
* Types of messages
* Conversation flow
* Message roles in LangChain

---

# What are Messages?

**Messages** are structured objects used to communicate with **Chat Models**.

Instead of sending one long text prompt, you send a sequence of messages with different roles.

---

# Why Messages?

Chat models understand conversations better when each message has a defined role.

Instead of:

```text
Explain Python.
Also remember that I'm a beginner.
```

Use structured messages:

```text id="3xvf5t"
System
   ↓
Human
   ↓
AI
```

This preserves conversation context and intent.

---

# Message Flow

```text id="4smgzq"
System Message
       │
       ▼
Human Message
       │
       ▼
AI Message
       │
       ▼
Next Human Message
       │
       ▼
AI Response
```

---

# Types of Messages

| Message Type                    | Purpose                                   |
| ------------------------------- | ----------------------------------------- |
| **System Message**              | Defines the AI's behavior or instructions |
| **Human Message**               | User's input/question                     |
| **AI Message**                  | Model's previous response                 |
| **Tool Message**                | Result returned from a tool/API           |
| **Function Message** *(Legacy)* | Older function-calling responses          |

> In modern LangChain, **System, Human, AI, and Tool Messages** are the most common.

---

# 1. System Message

Defines the assistant's role and behavior.

Example:

```text id="2i7pnn"
You are an AI tutor.
Explain concepts in simple language.
```

Purpose:

* Set personality
* Define response style
* Establish rules

---

# 2. Human Message

Represents the user's request.

Example:

```text id="pw83kz"
Explain LangChain.
```

Purpose:

* Ask questions
* Give instructions
* Provide information

---

# 3. AI Message

Represents the model's previous response.

Example:

```text id="m9t3wz"
LangChain is a framework for building LLM applications.
```

Purpose:

* Maintain conversation history
* Provide context for future responses

---

# 4. Tool Message

Contains the output of an external tool.

Example:

```text id="06jz7g"
Weather API Result:
28°C, Sunny
```

Purpose:

* Pass external data back to the model
* Enable tool calling and agents

---

# Conversation Example

```text id="4e5c9s"
System:
You are a helpful tutor.

↓

Human:
What is Python?

↓

AI:
Python is a programming language.

↓

Human:
Who created it?

↓

AI:
Guido van Rossum created Python.
```

---

# Data Flow

```text id="eb5imc"
System Message
        │
        ▼
Human Message
        │
        ▼
Chat Model
        │
        ▼
AI Message
        │
        ▼
Conversation Continues
```

---

# Why Not Use Plain Text?

Plain text:

```text
You are a tutor.
Explain Python.
```

Structured messages:

```text id="x27lzb"
System → You are a tutor.

Human → Explain Python.
```

Benefits:

* Clear separation of roles
* Better context management
* Improved conversation quality
* Easier integration with tools

---

# Messages vs Prompt Templates

| Prompt Templates        | Messages                |
| ----------------------- | ----------------------- |
| Build dynamic prompts   | Structure conversations |
| Use variables           | Use roles               |
| Generate formatted text | Create chat history     |
| Usually one prompt      | Multiple messages       |

They are often used **together**.

---

# Best Practices

* ✅ Use **System Messages** to define assistant behavior.
* ✅ Keep **Human Messages** focused on user input.
* ✅ Preserve **AI Messages** for conversation context.
* ✅ Use **Tool Messages** for external tool results.
* ✅ Avoid putting everything into one long message.

---

# Common Mistakes

* ❌ Mixing system instructions with user input.
* ❌ Omitting the System Message when consistent behavior is needed.
* ❌ Losing conversation history.
* ❌ Treating AI Messages as user input.
* ❌ Using plain text for complex conversations.

---

# Key Takeaways

* Messages are the standard communication format for chat models.
* Each message has a specific **role**.
* System Messages define behavior.
* Human Messages contain user input.
* AI Messages preserve conversation history.
* Tool Messages enable integration with external systems.

---

# Interview Questions

1. What are Messages in LangChain?
2. Why do chat models use Messages instead of plain text?
3. What is the purpose of a System Message?
4. What is the difference between Human and AI Messages?
5. When is a Tool Message used?
6. How do Messages improve conversation quality?
7. Can Prompt Templates and Messages be used together?
8. Why is conversation history important?
9. What happens if the System Message is omitted?
10. What is the advantage of structured messages?

---

# Mini Quiz

1. Which message type defines the assistant's behavior?
2. Which message type represents the user's question?
3. Which message type stores previous model responses?
4. Which message type contains API/tool results?
5. True or False: Messages replace Prompt Templates.

---

# Lesson Summary

```text id="d1ef1o"
System Message
       │
       ▼
Human Message
       │
       ▼
Chat Model
       │
       ▼
AI Message
       │
       ▼
Tool Message (Optional)
       │
       ▼
Next Conversation
```

### Message Roles

* **System Message** → Defines the AI's behavior
* **Human Message** → User's input
* **AI Message** → Model's response
* **Tool Message** → External tool/API output

> **Remember:**
>
> * **Prompt Templates** create the content of prompts.
> * **Messages** organize that content into a structured conversation that chat models understand.
