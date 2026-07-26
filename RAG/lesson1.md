Lesson 1 — What is Retrieval-Augmented Generation (RAG)?
Previous Lesson Recap

This is our first lesson, so there is no previous material to review.

Knowledge Gap Analysis

Current assumed background:

Area	Current Level
Python	Strong
Machine Learning Fundamentals	Basic understanding
Neural Networks	Familiar
LLMs	Beginner
RAG Systems	No practical experience
Vector Databases	No experience
Production AI Systems	Learning path begins
Revision Recommendations

Before continuing through the course, keep these foundations active:

Python engineering:
Type hints
Async programming
API development
Testing
Packaging
Machine learning:
Embeddings
Similarity functions
Evaluation metrics
Data pipelines
Systems:
Databases
Distributed systems
APIs
Cloud infrastructure
Lesson 1 — Introduction to Retrieval-Augmented Generation
Concept

Retrieval-Augmented Generation (RAG) is an architecture that combines:

Information retrieval
Large language model generation

to allow an AI system to answer questions using external knowledge sources.

A traditional LLM generates answers only from knowledge stored inside its neural network parameters.

A RAG system retrieves relevant information from external sources and provides that information to the LLM before generating an answer.

The core idea:

Give the model the right information at the right time instead of expecting it to memorize everything.

Intuition

Imagine hiring a brilliant employee.

They have:

Excellent reasoning ability
Strong communication skills
General knowledge

But they do not know your company's:

Internal documentation
Customer records
Product manuals
Engineering decisions
Private databases

You have two options:

Option 1 — Train their brain

You could teach them every document.

This is similar to:

Fine-tuning
Pre-training

Problems:

Expensive
Slow
Knowledge becomes outdated
Difficult to update
Option 2 — Give them a searchable library

Before answering a question:

Search the company documents
Find relevant pages
Give those pages to the employee
Ask them to answer using those references

This is RAG.

Why Does RAG Exist?
The Problem With LLMs

Large Language Models are powerful, but they have limitations.

1. Knowledge Cutoff

An LLM does not automatically know new information.

Example:

A model trained in 2024 may not know:

2025 company policies
New research papers
Recent product documentation
2. Hallucinations

A hallucination occurs when a model generates information that sounds correct but is false.

Example:

User:

What is our company's refund policy?

Without access to company documents:

LLM:

Our refund policy allows returns within 45 days.

Possible problem:

The company actually allows only 30 days.

The model produced a convincing but incorrect answer.

3. Private Data Problem

Most valuable enterprise information is private.

Examples:

Medical records
Legal documents
Internal APIs
Financial reports
Customer conversations

A general LLM has no access to this information.

4. Context Limitations

LLMs can only process a limited amount of text.

Example:

A company has:

50 million documents
500 GB of knowledge


You cannot place everything into a prompt.

You need:

Question
   |
   |
Retrieve relevant documents
   |
   |
Send only useful context
   |
   |
LLM generates answer

Traditional LLM vs RAG
System	Knowledge Source	Update Knowledge?	Hallucination Risk
Traditional LLM	Training data	Difficult	Higher
Fine-tuned LLM	Training + fine-tuning data	Medium	Medium
RAG System	External retrieval system	Easy	Lower
End-to-End RAG Architecture

A production RAG system usually looks like this:

flowchart TD

A[User Question]

A --> B[Application API]

B --> C[Query Processing]

C --> D[Retriever]

D --> E[Vector Database]

E --> F[Relevant Documents]

F --> G[Prompt Construction]

G --> H[Large Language Model]

H --> I[Generated Answer]

I --> J[Citations / Sources]

Data Flow Explanation
Step 1 — User asks a question

Example:

How do I reset my company laptop password?

Step 2 — Query Processing

The system may:

Clean the query
Rewrite it
Expand it
Detect intent

Example:

Original:

forgot password


Expanded:

company laptop password reset procedure
IT password recovery instructions

Step 3 — Retrieval

The system searches external knowledge.

Possible sources:

PDFs
Websites
Databases
Documentation
Code repositories

Output:

Document A:
"Employees can reset passwords through the internal portal..."

Document B:
"Password reset requires MFA verification..."

Step 4 — Context Assembly

The application creates a prompt:

You are an assistant.

Use the following documents:

Document 1:
Employees can reset passwords...

Document 2:
Password reset requires MFA...

Question:
How do I reset my password?

Step 5 — Generation

The LLM produces:

You can reset your password through the internal portal.
You will need MFA verification.

Sources:
- IT Documentation Page 12
- Security Policy Page 4

RAG System Architecture

A complete production architecture:

flowchart LR

subgraph Data_Collection

A[PDF Files]
B[Web Pages]
C[DOCX Files]
D[Databases]

end


subgraph Processing

E[Document Loader]
F[Text Cleaning]
G[Chunking]
H[Embedding Model]

end


subgraph Storage

I[Vector Database]
J[Metadata Store]

end


subgraph Query_Time

K[User Query]
L[Query Understanding]
M[Retriever]
N[Reranker]
O[Prompt Builder]
P[LLM]

end


A --> E
B --> E
C --> E
D --> E

E --> F
F --> G
G --> H

H --> I
G --> J

K --> L
L --> M

I --> M
J --> M

M --> N
N --> O
O --> P

Technical Explanation
The Two Main Components

A RAG system has two major phases:

Phase 1 — Indexing

Offline process.

Goal:

Convert documents into searchable representations.

Pipeline:

Documents
    |
    v
Chunking
    |
    v
Embedding Generation
    |
    v
Vector Storage

Phase 2 — Retrieval + Generation

Online process.

Pipeline:

User Question

      |
      v

Convert Query to Vector

      |
      v

Search Similar Documents

      |
      v

Send Context to LLM

      |
      v

Generate Answer

Parametric Knowledge vs External Knowledge

A critical RAG concept.

Parametric Knowledge

Knowledge stored inside model weights.

Example:

The model knows:

What Python is
What gravity is
Basic programming concepts

This knowledge comes from training.

External Knowledge

Knowledge stored outside the model.

Examples:

Company wiki
Product database
Research papers
Customer documents

RAG connects the model to this information.

Knowledge Grounding

Grounding means:

The answer is based on retrieved evidence rather than only model memory.

Example:

Bad:

The refund policy is probably 30 days.


Grounded:

According to the refund policy document:

"Customers may request refunds within 30 days."

Therefore, the refund period is 30 days.

Technical Deep Dive
Why Not Just Put All Documents Into the Prompt?

Because of:

1. Cost

More tokens:

Higher API cost
Slower responses
2. Attention Dilution

LLMs do not treat every token equally.

If important information is buried among thousands of irrelevant tokens:

The model may ignore it.

3. Context Window Limits

Even modern models have limits.

Example:

Model context window:
128k tokens

Company documents:
10 billion tokens


Retrieval solves this mismatch.

RAG vs Fine-Tuning
Feature	RAG	Fine-tuning
Add new knowledge	Excellent	Poor
Update frequently	Easy	Difficult
Requires training	No	Yes
Reduces hallucination	Yes	Sometimes
Changes behavior/style	Limited	Excellent
Uses private documents	Excellent	Possible
When Should You Use RAG?

Use RAG when:

Information changes frequently
Data is private
Documents are large
You need citations
Accuracy matters

Examples:

Industry	RAG Application
Healthcare	Medical document assistant
Legal	Case research assistant
Finance	Regulatory compliance search
Software	Code documentation assistant
Customer Support	Helpdesk chatbot
Education	Personalized tutor
Common Beginner Mistakes
Mistake 1: Thinking RAG = Chatbot

A chatbot is an interface.

RAG is a knowledge architecture.

A chatbot may use RAG.

Mistake 2: Believing Better LLM = Better RAG

A weak retrieval system with a powerful model often performs poorly.

Important:

Retrieval quality is frequently the bottleneck.

Mistake 3: Ignoring Data Quality

Garbage documents create garbage answers.

Problems:

Duplicate documents
Poor chunking
Missing metadata
Bad OCR
Mistake 4: Sending Too Much Context

More context is not always better.

A good RAG system retrieves:

Relevant
Small
High-quality

context.

Production Considerations

A production RAG system requires:

Data Layer
Document ingestion
Cleaning
Metadata extraction
Version tracking
Retrieval Layer
Vector search
Keyword search
Filtering
Ranking
Generation Layer
Prompt templates
LLM calls
Streaming
Citations
Operations Layer
Monitoring
Evaluation
Security
Cost tracking
First Production Project Overview

Throughout this course, we will build:

Intelligent Enterprise Knowledge Assistant

Capabilities:

Upload documents
Crawl websites
Index knowledge
Search semantically
Answer questions
Provide citations
Support multiple users
Stream responses
Deploy to cloud

Final architecture:

flowchart TD

User[User]

User --> UI[Web Application]

UI --> API[FastAPI Backend]

API --> Auth[Authentication]

API --> RAG[RAG Pipeline]

RAG --> Retriever[Hybrid Retriever]

Retriever --> VectorDB[Vector Database]

Retriever --> BM25[Keyword Search]

VectorDB --> Reranker[Reranking Model]

BM25 --> Reranker

Reranker --> LLM[Large Language Model]

LLM --> Response[Streaming Answer]

Response --> UI

Summary

Today you learned:

What RAG is
Why RAG exists
LLM limitations
Hallucinations
Context windows
Parametric vs external knowledge
Knowledge grounding
Basic RAG architecture
Indexing vs retrieval phases
Cheat Sheet
Term	Meaning
RAG	Retrieval-Augmented Generation
Retrieval	Finding relevant information
Generation	Creating final answer
Embedding	Numeric representation of meaning
Vector Database	Storage optimized for similarity search
Context	Information provided to LLM
Grounding	Using evidence for answers
Hallucination	Incorrect generated information
Glossary
LLM

Large Language Model trained on massive text datasets.

Retrieval

The process of finding relevant information from a collection.

Embedding

A vector representation capturing semantic meaning.

Context Window

Maximum amount of text a model can process at once.

Vector Database

A database optimized for storing and searching embeddings.

Interview Questions
Beginner
What problem does RAG solve?
Why do LLMs hallucinate?
What is the difference between RAG and fine-tuning?
What happens during retrieval?
Intermediate
Why can adding more context reduce answer quality?
Explain indexing vs query-time retrieval.
How does RAG enable private knowledge?
Debugging Scenarios
Scenario 1

Your chatbot gives incorrect answers.

Possible causes:

Retriever found wrong documents
Documents are outdated
Prompt does not enforce grounding
Too much irrelevant context
Scenario 2

Your RAG system is slow.

Possible causes:

Large embeddings
Slow vector database
Too many retrieved documents
Large LLM prompt
Performance Tips

Early principles:

Optimize retrieval before changing the LLM
Measure everything
Store metadata
Keep chunks focused
Evaluate with real user questions
Further Reading
Books
Designing Data-Intensive Applications — Martin Kleppmann
Hands-On Large Language Models — Jay Alammar & Maarten Grootendorst
Research Papers

Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks

Lewis et al., 2020

Dense Passage Retrieval for Open-Domain Question Answering

Karpukhin et al., 2020

REALM: Retrieval-Augmented Language Model Pre-Training

Guu et al., 2020

Open Source Datasets

Beginner datasets:

Natural Questions
MS MARCO
BEIR Benchmark
HotpotQA
Practice Exercises
Concept Exercise

Explain RAG in your own words using the analogy of a university student and a library.

Stretch Challenge

Design a RAG system for:

A university assistant that answers questions from 100,000 research papers.

Identify:

Data sources
Retrieval approach
Storage system
Generation strategy
Progress Tracking

Current Progress:

Module 1 — Foundations

Lesson 1:
✅ What is RAG?
⬜ Why RAG exists
⬜ LLM limitations
⬜ Context windows
⬜ Knowledge grounding
⬜ Complete architecture

Concept Questions

Answer these before we continue:

1.

Why is RAG usually preferred over fine-tuning when company documents change frequently?

2.

Explain the difference between:

Parametric knowledge
External knowledge
3.

Why can giving an LLM every company document reduce answer quality?

4.

Describe the two major phases of a RAG system.

5.

What does "grounded generation" mean?

Practical Engineering Question

You are building an internal HR assistant for a company with 2 million documents.

Would you:

A. Fine-tune an LLM on all documents
B. Put all documents into the prompt
C. Build a RAG system

Explain your choice.

Coding Exercise

Create a simple Python design sketch for a RAG pipeline.

Requirements:

Use Python classes
Include:
DocumentLoader
Chunker
Retriever
Generator

Do not implement actual embeddings yet.

Example structure:

class DocumentLoader:
    def load(self, path: str) -> list[str]:
        pass


class Retriever:
    def search(self, query: str) -> list[str]:
        pass


Reply with your answers and we will review your understanding before moving to Lesson 2: LLM Fundamentals for RAG Engineers — Tokens, Context Windows, Attention, and Why Retrieval Works.