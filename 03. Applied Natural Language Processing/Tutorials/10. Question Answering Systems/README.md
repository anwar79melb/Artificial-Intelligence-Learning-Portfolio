# Tutorial 10: Question Answering Systems

## Overview

One of the most natural ways humans interact with information is by asking questions.

Consider the following examples:

```text
Where is the Louvre Museum located?

Who founded Microsoft?

What is the capital of Australia?
```

Traditionally, search engines return a list of documents that may contain the answer. Question Answering (QA) systems go a step further by attempting to provide the answer directly.

Question Answering is one of the most important areas of Natural Language Processing because it combines many NLP techniques, including:

- Information Retrieval
- Named Entity Recognition
- Information Extraction
- Language Understanding
- Machine Learning
- Deep Learning

Modern QA systems form the foundation of technologies such as:

- ChatGPT
- Microsoft Copilot
- Google Search AI
- Siri
- Alexa
- Virtual Assistants

In this tutorial, we explore how Question Answering systems work, the role of Information Retrieval, major QA datasets, answer extraction techniques, and the use of modern language models for question answering.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define Question Answering (QA)

✅ Distinguish different QA approaches

✅ Explain Information Retrieval

✅ Understand Factoid Question Answering

✅ Describe Retrieve-and-Read architectures

✅ Understand Reading Comprehension systems

✅ Explain common QA datasets

✅ Understand Answer Span Extraction

✅ Describe BERT-based QA models

✅ Explain how Language Models perform QA

✅ Understand modern Open-Domain QA systems

---

# 1. What is Question Answering?

Question Answering (QA) is the task of automatically answering questions expressed in natural language.

Unlike traditional search systems, QA systems attempt to provide answers directly rather than simply returning documents.

---

## Example

Question:

```text
Where is the Eiffel Tower located?
```

Search Engine:

```text
Returns webpages
```

Question Answering System:

```text
Paris, France
```

---

## Illustration

```text
Question
    ↓
Question Answering System
    ↓
Answer
```

---

# 2. Why Question Answering Matters

Humans naturally seek information through questions.

Examples include:

```text
Who invented the telephone?

When was Google founded?

Why is the sky blue?
```

Question Answering systems provide fast and direct access to information.

---

## Applications

- Search engines
- Virtual assistants
- Customer support systems
- Educational platforms
- Healthcare information systems
- Enterprise knowledge systems

---

# 3. Types of Question Answering

Different QA systems solve different problems.

---

## Factoid Question Answering

Answers are short factual responses.

Examples:

```text
Who founded Apple?

Steve Jobs
```

---

```text
What is the capital of Japan?

Tokyo
```

---

## Long-Form Question Answering

Requires detailed answers.

Example:

```text
Why do earthquakes occur?
```

---

## Community Question Answering

Uses previously answered questions.

Examples:

```text
Quora

Stack Overflow

Reddit
```

---

# 4. Two Major Approaches to QA

Modern QA systems generally follow one of two approaches.

---

# Information Retrieval-Based QA

This approach searches large document collections for relevant information.

---

## Workflow

```text
Question
      ↓
Retrieve Documents
      ↓
Read Documents
      ↓
Extract Answer
```

---

# Knowledge-Based QA

Uses structured databases and knowledge graphs.

---

## Workflow

```text
Question
      ↓
Convert to Query
      ↓
Knowledge Base
      ↓
Answer
```

---

# 5. Information Retrieval-Based Question Answering

Information Retrieval (IR)-based QA is currently one of the most common approaches.

---

## Example

Question:

```text
Who discovered penicillin?
```

---

The system:

1. Searches a large collection.
2. Finds relevant passages.
3. Extracts the answer.

Output:

```text
Alexander Fleming
```

---

## Illustration

```text
Question
     ↓
Search Collection
     ↓
Relevant Documents
     ↓
Answer
```

---

# 6. Knowledge-Based Question Answering

Knowledge-Based QA relies on structured facts.

---

## Example

Knowledge Graph:

```text
Alexander Fleming
         │
 discovered
         │
 Penicillin
```

---

Question:

```text
Who discovered penicillin?
```

Answer:

```text
Alexander Fleming
```

---

## Advantages

✅ Fast retrieval

✅ Structured information

✅ Highly accurate facts

---

## Limitations

❌ Requires large knowledge bases

❌ Expensive to maintain

---

# 7. Information Retrieval (IR)

Information Retrieval is a field focused on finding documents that satisfy a user's information need.

Examples include:

- Google Search
- Bing Search
- Library Catalogues
- Academic Search Engines

---

## Basic Concepts

### Document

A unit of text.

Examples:

```text
Web Page

Article

Research Paper
```

---

### Collection

A set of documents.

Example:

```text
Entire Wikipedia
```

---

### Query

User's information request.

Example:

```text
Best AI books
```

---

# 8. Information Retrieval Architecture

A typical retrieval engine operates as follows.

---

## Workflow

```text
Document Collection
         ↓
Indexing
         ↓
Search Query
         ↓
Ranking
         ↓
Results
```

---

# 9. Vector Space Retrieval

A common IR technique represents both documents and queries as vectors.

---

## Example

Query:

```text
machine learning
```

and documents are transformed into vector representations.

---

Similarity is then calculated using:

```text
Cosine Similarity
```

---

Documents with higher similarity scores are ranked higher.

---

# 10. Factoid Question Answering

Factoid QA focuses on concise factual answers.

---

## Examples

Question:

```text
Who wrote Hamlet?
```

Answer:

```text
William Shakespeare
```

---

Question:

```text
What is the tallest mountain?
```

Answer:

```text
Mount Everest
```

---

## Characteristics

✅ Short answer

✅ Factually grounded

✅ Common in search systems

---

# 11. The Retrieve-and-Read Model

Modern Open-Domain QA systems generally follow a:

```text
Retrieve-and-Read
```

architecture.

---

## Step 1: Retrieval

Find documents likely to contain the answer.

---

## Step 2: Reading

Analyze retrieved passages and locate the answer.

---

## Illustration

```text
Question
     ↓
Retriever
     ↓
Relevant Passages
     ↓
Reader
     ↓
Answer
```

---

# 12. Reading Comprehension

Reading Comprehension systems assume that a relevant passage is already available.

---

## Input

Question:

```text
Where is Mount Everest located?
```

Passage:

```text
Mount Everest lies on the border between Nepal and Tibet.
```

---

## Output

```text
Nepal and Tibet
```

---

# 13. Open-Domain Question Answering

Unlike Reading Comprehension systems, Open-Domain QA must find the information itself.

---

## Characteristics

The system receives:

```text
Question
```

and access to:

```text
Massive Document Collection
```

---

The system must:

1. Retrieve relevant documents.
2. Read them.
3. Extract the answer.

---

# 14. Popular QA Datasets

Training modern QA systems requires large datasets.

---

# Stanford Question Answering Dataset (SQuAD)

One of the most widely used QA benchmarks.

---

## Characteristics

- Based on Wikipedia
- Human-written questions
- Answer spans inside passages

---

## Example

Passage:

```text
The Amazon River is located in South America.
```

Question:

```text
Where is the Amazon River located?
```

Answer:

```text
South America
```

---

# 15. HotpotQA

HotpotQA contains more challenging questions.

---

## What Makes It Different?

Questions require:

```text
Multi-Hop Reasoning
```

across multiple documents.

---

## Example

Question:

```text
Which author wrote the novel adapted into a specific film?
```

The system may need information from multiple sources to answer.

---

# 16. TriviaQA

TriviaQA contains questions written independently from supporting documents.

---

## Benefits

Provides:

✅ More realistic questions

✅ Less dataset bias

✅ Larger information requirements

---

# 17. Natural Questions Dataset

Created using real Google search queries.

---

## Features

Contains:

- Real-world questions
- Wikipedia pages
- Long answers
- Short answers
- No-answer cases

---

## Example

Question:

```text
When are hops added during brewing?
```

Answer:

```text
During the boiling process
```

---

# 18. TyDi QA

Most QA datasets focus on English.

TyDi QA was created to address multilingual question answering.

---

## Includes Languages Such As

```text
Arabic

Bengali

Russian

Thai

Swahili
```

---

## Importance

Supports multilingual NLP research.

---

# 19. Answer Span Extraction

Most modern QA systems use:

```text
Extractive Question Answering
```

---

## Goal

Find the exact span of text containing the answer.

---

## Example

Passage:

```text
Mount Everest reaches 29,029 feet.
```

Question:

```text
How tall is Mount Everest?
```

Answer:

```text
29,029 feet
```

---

# 20. Reading Comprehension as Span Prediction

Modern QA models treat answer extraction as a prediction problem.

---

## Input

```text
Question

+

Passage
```

---

## Output

```text
Start Position

End Position
```

of the answer.

---

# 21. BERT for Question Answering

One of the most influential QA models is:

```text
BERT
```

---

## Workflow

```text
Question
    +
Passage
      ↓
BERT Encoder
      ↓
Answer Span Prediction
```

---

## Example

Input:

```text
Question:
Who discovered penicillin?

Passage:
Alexander Fleming discovered penicillin in 1928.
```

Output:

```text
Alexander Fleming
```

---

# 22. How BERT Processes QA

BERT receives:

```text
Question

[SEP]

Passage
```

as input.

---

After encoding:

Each token receives a contextual representation.

The model then predicts:

```text
Answer Start

Answer End
```

positions.

---

# 23. Language Models for QA

Recent research explores answering questions directly using large language models.

---

Examples include:

```text
GPT

T5

LLaMA

Gemini

Claude
```

---

Instead of:

```text
Retrieve Documents
```

the model attempts to answer using:

```text
Knowledge Stored In Parameters
```

---

# 24. T5 and Generative QA

T5 treats question answering as a text generation problem.

---

## Example

Input:

```text
Who invented the telephone?
```

Output:

```text
Alexander Graham Bell
```

---

The model generates the answer directly.

---

# 25. Advantages of Language Model QA

✅ Simple interface

✅ End-to-end generation

✅ Flexible responses

✅ Supports open-ended questions

---

# 26. Limitations of Language Model QA

Despite impressive performance, several challenges remain.

---

## Hallucination

Models may generate incorrect answers.

---

## Lack of Explainability

Users may not know where the answer came from.

---

## Knowledge Cut-Off

Models may miss recent information.

---

## Factual Reliability

Generated answers may not always be accurate.

---

# 27. Comparing QA Approaches

| Feature | Retrieval-Based QA | Language Model QA |
|----------|----------|----------|
| Uses Documents | Yes | Not Always |
| Source Traceability | High | Lower |
| Explainability | Better | Limited |
| Flexibility | Moderate | High |
| Hallucination Risk | Low | Higher |
| Open-Ended Answers | Limited | Strong |

---

# 28. Applications of Question Answering

Question Answering systems are widely used in:

---

## Search Engines

Provide direct answers.

---

## Virtual Assistants

Examples:

```text
Siri

Alexa

Google Assistant
```

---

## Enterprise Knowledge Systems

Answer internal company questions.

---

## Healthcare

Provide medical information.

---

## Education

Support intelligent tutoring systems.

---

# Complete Question Answering Pipeline

```text
Question
      ↓
Question Analysis
      ↓
Information Retrieval
      ↓
Relevant Documents
      ↓
Answer Extraction
      ↓
Answer Ranking
      ↓
Final Answer
```

---

# Real-World Example

Question:

```text
Who founded Microsoft?
```

---

Retriever finds:

```text
Microsoft was founded by Bill Gates and Paul Allen in 1975.
```

---

Reader extracts:

```text
Bill Gates

Paul Allen
```

---

Final Answer:

```text
Bill Gates and Paul Allen
```

---

# Summary

In this tutorial we explored:

- Question Answering (QA)
- Factoid Questions
- Information Retrieval
- Retrieval-Based QA
- Knowledge-Based QA
- Retrieve-and-Read Architecture
- Reading Comprehension
- Open-Domain QA
- SQuAD
- HotpotQA
- TriviaQA
- Natural Questions
- TyDi QA
- Answer Span Extraction
- BERT-Based QA
- T5 and Language Model QA

Question Answering represents one of the most advanced areas of Natural Language Processing. By combining information retrieval, language understanding, reasoning, and machine learning, QA systems allow users to obtain direct answers from vast collections of information. Modern QA technologies now power search engines, virtual assistants, enterprise knowledge systems, and large language models used around the world.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define Question Answering.

✅ Explain Factoid QA.

✅ Distinguish Retrieval-Based and Knowledge-Based QA.

✅ Explain Information Retrieval.

✅ Describe the Retrieve-and-Read model.

✅ Understand Reading Comprehension systems.

✅ Identify major QA datasets.

✅ Explain Answer Span Extraction.

✅ Describe BERT-based QA.

✅ Explain Language Model QA.

✅ Compare Retrieval-Based QA and Generative QA.

✅ Understand real-world applications of Question Answering systems.
