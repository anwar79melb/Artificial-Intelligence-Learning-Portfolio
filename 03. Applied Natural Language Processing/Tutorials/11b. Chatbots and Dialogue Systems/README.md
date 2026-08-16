# Tutorial 11B: Chatbots and Dialogue Systems

## Overview

One of the most visible applications of Natural Language Processing is the development of systems that can communicate with humans using natural language.

Whether asking Siri for the weather, requesting Alexa to play music, chatting with ChatGPT, or interacting with a customer support bot, we are engaging with a **Dialogue System**.

Chatbots and Dialogue Systems aim to create natural, useful, and engaging interactions between humans and machines. Over the years, these systems have evolved from simple rule-based programs into sophisticated AI-powered conversational agents capable of understanding context, generating responses, and assisting users with complex tasks.

In this tutorial, we explore the foundations of conversational AI, chatbot architectures, dialogue management, evaluation methods, and the ethical challenges involved in deploying conversational systems.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain what chatbots and dialogue systems are

✅ Distinguish between chatbot and task-oriented systems

✅ Understand the evolution of chatbot architectures

✅ Explain dialogue turns and turn-taking

✅ Understand dialogue acts

✅ Explain grounding in conversations

✅ Describe retrieval-based chatbots

✅ Explain generative chatbot models

✅ Understand dialogue evaluation techniques

✅ Identify ethical issues in conversational AI

✅ Understand the Microsoft Tay case study

---

# 1. What are Chatbots?

A chatbot is a computer program designed to communicate with humans using natural language.

The objective is to simulate a conversation that feels natural and meaningful.

---

## Examples

Modern chatbots include:

```text
ChatGPT

Microsoft Copilot

Google Gemini

Claude
```

Earlier examples include:

```text
ELIZA

PARRY
```

---

## Illustration

```text
User
   ↓
Question
   ↓
Chatbot
   ↓
Response
```

---

# 2. What are Dialogue Systems?

A dialogue system is a broader category that includes any system capable of conducting a conversation.

Chatbots are one type of dialogue system.

---

## Common Applications

```text
Virtual Assistants

Customer Service Bots

Travel Booking Systems

Healthcare Assistants

Educational Tutors
```

---

## Example

User:

```text
Book me a flight to Sydney.
```

System:

```text
What date would you like to travel?
```

The conversation continues until the task is completed.

---

# 3. Two Types of Conversational Agents

Modern conversational systems are generally divided into two categories.

---

# Chatbots

Designed for open conversation.

Primary goals:

```text
Engagement

Entertainment

Social Interaction
```

---

## Examples

```text
ChatGPT

BlenderBot

XiaoIce
```

---

# Task-Oriented Dialogue Systems

Designed to accomplish a specific goal.

Primary goals:

```text
Answer Questions

Complete Transactions

Perform Tasks
```

---

## Examples

```text
Siri

Alexa

Google Assistant
```

---

## Illustration

```text
Conversational Agents
        │
        ├── Chatbots
        │
        └── Task-Oriented Systems
```

---

# 4. The Evolution of Chatbots

Chatbot technology has evolved significantly.

---

## Stage 1: Rule-Based Systems

Responses are determined using predefined rules.

---

## Stage 2: Information Retrieval Systems

Responses are retrieved from existing conversations.

---

## Stage 3: Neural Generation Systems

Responses are generated dynamically.

---

## Stage 4: Large Language Models

Modern systems use transformers and massive datasets.

---

## Evolution Diagram

```text
Rule-Based
      ↓
Retrieval-Based
      ↓
Neural Networks
      ↓
Transformers
      ↓
Large Language Models
```

---

# 5. Rule-Based Chatbots

The earliest chatbots relied on manually created patterns.

---

## ELIZA

One of the earliest chatbots.

Example:

User:

```text
I am feeling sad.
```

ELIZA:

```text
Why do you feel sad?
```

---

## Characteristics

✅ Simple

✅ Easy to implement

---

## Limitations

❌ No real understanding

❌ Limited flexibility

❌ Difficult to scale

---

# 6. PARRY

PARRY expanded upon ELIZA by introducing a simple psychological model.

The system attempted to simulate a patient with paranoid tendencies.

---

## Importance

PARRY demonstrated that simple internal models could make conversations appear more realistic.

---

# 7. Task-Based Dialogue Systems

Task-oriented systems are built around specific objectives.

---

## Examples

```text
Travel Booking

Restaurant Reservations

Customer Support

Smart Home Control
```

---

The goal is not casual conversation.

The goal is:

```text
Task Completion
```

---

# 8. Frames and Slots

Most task-based systems use a structure known as a:

```text
Frame
```

---

A frame contains:

```text
Slots
```

that must be filled before completing a task.

---

## Example: Flight Booking

| Slot | Value |
|--------|--------|
| Departure City | Melbourne |
| Destination | Sydney |
| Date | 20 June |
| Time | 9:00 AM |

---

## Illustration

```text
Flight Booking Frame

Departure:
Destination:
Date:
Time:
```

---

# 9. Dialogue Flow

The system collects missing information gradually.

---

## Example

System:

```text
Where are you travelling from?
```

User:

```text
Melbourne
```

---

System:

```text
Where would you like to go?
```

User:

```text
Sydney
```

---

Eventually all slots are completed.

---

# 10. Human Conversation Fundamentals

Human conversations appear simple but are surprisingly complex.

Important concepts include:

- Turns
- Turn-taking
- Interruptions
- Context
- Shared understanding

---

# 11. Turns in Conversation

A turn is a single contribution made by a participant.

---

## Example

User:

```text
What time is it?
```

---

System:

```text
It is 3 PM.
```

---

Each contribution represents one turn.

---

## Illustration

```text
User Turn
      ↓
System Turn
      ↓
User Turn
      ↓
System Turn
```

---

# 12. Turn-Taking

Humans naturally know when to:

```text
Speak

Pause

Respond
```

---

Dialogue systems must learn similar behaviour.

---

## Challenges

- Interruptions
- Overlapping speech
- Long pauses
- Unclear endings

---

# 13. Interruptions and Barge-In

Users frequently interrupt systems while they are speaking.

This capability is known as:

```text
Barge-In
```

---

## Example

Assistant:

```text
Your flight departs at...
```

User:

```text
Wait, I need to change the destination.
```

---

Modern systems must handle this smoothly.

---

# 14. End-Point Detection

A dialogue system must detect when the user has finished speaking.

---

## Challenge

Humans often pause while thinking.

Example:

```text
I would like to... um...
book a flight.
```

---

The system must avoid responding too early.

---

# 15. Dialogue Acts (Speech Acts)

Not all sentences serve the same purpose.

Each utterance performs a specific function.

---

## Common Dialogue Acts

### Question

```text
What time is the meeting?
```

---

### Request

```text
Play some music.
```

---

### Statement

```text
I need to travel tomorrow.
```

---

### Acknowledgement

```text
Okay.

Thank you.

Got it.
```

---

# 16. Why Dialogue Acts Matter

Understanding the purpose of an utterance is crucial.

---

Example:

```text
Open the door.
```

This is:

```text
A Request
```

not merely information.

---

Dialogue systems must identify these intentions correctly.

---

# 17. Grounding in Conversations

Successful communication requires shared understanding.

This concept is known as:

```text
Grounding
```

---

## Example

System:

```text
Would you like to review your profile?
```

User:

```text
No.
```

---

Better Response:

```text
Okay, let's continue.
```

---

The acknowledgement signals successful understanding.

---

# 18. Corpus-Based Chatbots

Modern chatbots depend heavily on large datasets.

Training corpora often contain:

```text
Millions of Conversations

Forum Posts

Dialogue Transcripts

Social Media Discussions
```

---

Without large datasets, modern chatbots would not be possible.

---

# 19. Retrieval-Based Chatbots

Retrieval-based systems search for an existing response.

---

## Process

```text
User Message
        ↓
Find Similar Conversation
        ↓
Retrieve Response
        ↓
Output Response
```

---

## Example

User:

```text
How are you?
```

System finds a similar question and returns a matching response.

---

## Advantages

✅ Safe

✅ Predictable

✅ Factually grounded

---

## Limitations

❌ Cannot create new responses

❌ Limited creativity

---

# 20. Neural Retrieval Systems

Instead of keyword matching, modern retrieval systems use embeddings.

---

## Similarity Measures

Examples:

```text
Cosine Similarity

Transformer Embeddings
```

---

Systems identify semantically similar conversations even when wording differs.

---

# 21. Generative Chatbots

Generative systems create entirely new responses.

---

## Architecture

```text
Input Message
       ↓
Encoder
       ↓
Language Model
       ↓
Generated Response
```

---

## Example

User:

```text
Tell me a joke.
```

System:

```text
Why don't programmers like nature?
Too many bugs.
```

---

The response is generated rather than retrieved.

---

# 22. Neural Encoder-Decoder Models

Early generative chatbots used:

```text
Encoder-Decoder Networks
```

---

The encoder processes the user's message.

The decoder generates a response word-by-word.

---

## Illustration

```text
User Input
       ↓
Encoder
       ↓
Context Representation
       ↓
Decoder
       ↓
Response
```

---

# 23. Large Language Models

Modern conversational systems rely heavily on:

```text
Transformers
```

and

```text
Large Language Models (LLMs)
```

---

Examples:

```text
GPT

LLaMA

Gemini

Claude

Copilot
```

---

These systems generate responses using large amounts of learned language knowledge.

---

# 24. Challenges of Generative Chatbots

Although powerful, generative systems have limitations.

---

## Repetition

Example:

```text
See you later.

See you later.

See you later.
```

---

## Inconsistency

Example:

```text
I am 16 years old.

Later:

I don't know how old I am.
```

---

## Hallucination

Models may generate incorrect information confidently.

---

# 25. Retrieval-Augmented Responses

Some systems combine retrieval and generation.

---

## Workflow

```text
User Query
      ↓
Retrieve Documents
      ↓
Provide Context
      ↓
Generate Response
```

---

This helps improve factual accuracy.

---

# 26. Evaluating Dialogue Systems

Evaluating chatbots is much harder than evaluating classification systems.

---

Why?

Because many different responses can be correct.

---

## Example

Question:

```text
How are you?
```

Possible valid answers:

```text
I'm fine.

Doing well.

Great, thanks.
```

All are acceptable.

---

# 27. Human Evaluation

The most common evaluation method involves human judges.

---

## Metrics

### Fluency

Is the response grammatically correct?

---

### Coherence

Does the response make sense?

---

### Humanness

Does it sound human-like?

---

### Engagement

Is the conversation interesting?

---

### Consistency

Does the system maintain context?

---

# 28. Participant Evaluation

The user directly interacts with the chatbot.

Afterward they rate:

```text
Quality

Naturalness

Enjoyment

Engagement
```

---

# 29. Observer Evaluation

A third-party evaluator reads conversation transcripts.

The evaluator compares systems on:

```text
Interestingness

Humanness

Knowledge

Conversational Quality
```

---

# 30. Designing Better Dialogue Systems

Successful systems are usually designed using:

```text
User-Centered Design
```

---

## Process

1. Study the users
2. Understand user goals
3. Build prototypes
4. Test with users
5. Improve iteratively

---

# 31. Ethical Challenges in Chatbots

Conversational AI introduces significant ethical concerns.

---

# Safety

A chatbot should not provide harmful advice.

Examples:

```text
Medical Advice

Financial Advice

Emergency Situations
```

require special care.

---

# Privacy

Chatbots often collect sensitive personal information.

Examples:

```text
Names

Locations

Messages

Preferences
```

---

Systems must protect this data responsibly.

---

# Representational Harm

Chatbots should avoid:

```text
Stereotypes

Bias

Discrimination

Harassment
```

---

Poor training data can lead to harmful behaviour.

---

# 32. Case Study: Microsoft Tay

One of the most famous chatbot failures involved Microsoft's chatbot:

```text
Tay
```

---

## Objective

Tay was designed to learn conversational behaviour from interactions with Twitter users.

---

## Problem

Users deliberately manipulated the chatbot.

---

Result:

```text
Offensive Content

Abusive Language

Inappropriate Responses
```

began appearing rapidly.

---

Microsoft removed the chatbot within hours.

---

## Lesson

```text
User Behaviour Must Be Considered
During System Design
```

---

# 33. Privacy and Data Leakage

Conversational systems may accidentally expose information.

---

## Example

A system trained on user conversations might reveal:

```text
Personal Data

Passwords

Private Discussions
```

---

Developers must implement safeguards to prevent leakage.

---

# Conversation AI Ecosystem

```text
User
   ↓
Dialogue System
   ↓
Natural Language Understanding
   ↓
Dialogue Management
   ↓
Response Generation
   ↓
User
```

---

# Evolution of Conversational AI

```text
ELIZA
   ↓
PARRY
   ↓
Rule-Based Chatbots
   ↓
Retrieval Systems
   ↓
Neural Chatbots
   ↓
Transformers
   ↓
Large Language Models
```

---

# Summary

In this tutorial we explored:

- Chatbots
- Dialogue Systems
- Conversational Agents
- Rule-Based Systems
- ELIZA
- PARRY
- Task-Oriented Dialogue Systems
- Frames and Slots
- Turn-Taking
- Dialogue Acts
- Grounding
- Retrieval-Based Chatbots
- Neural Chatbots
- Encoder-Decoder Models
- Large Language Models
- Dialogue Evaluation
- User-Centered Design
- Ethical Challenges
- Microsoft Tay

Chatbots and Dialogue Systems represent one of the most visible applications of NLP. From simple rule-based systems to modern Large Language Models, conversational AI has evolved dramatically. Understanding both the technical foundations and ethical responsibilities of these systems is essential for developing safe, useful, and trustworthy conversational technologies.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define chatbots and dialogue systems.

✅ Distinguish chatbot and task-oriented systems.

✅ Explain rule-based chatbot architectures.

✅ Describe retrieval-based chatbots.

✅ Explain generative chatbots.

✅ Understand frames and slots.

✅ Explain turn-taking and dialogue acts.

✅ Describe grounding in conversations.

✅ Explain dialogue evaluation methods.

✅ Discuss ethical challenges in chatbot deployment.

✅ Explain the Microsoft Tay case study.

✅ Understand the evolution of modern conversational AI.
