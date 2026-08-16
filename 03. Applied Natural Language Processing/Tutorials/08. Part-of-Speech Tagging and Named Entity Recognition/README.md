# Tutorial 08: Part-of-Speech Tagging and Named Entity Recognition

## Overview

After learning how text can be cleaned, classified, and represented numerically, the next step is teaching computers to understand the grammatical and semantic structure of language.

Humans naturally recognize that words play different roles in a sentence:

```text
The dog runs quickly.
```

We immediately understand that:

- "dog" is a noun
- "runs" is a verb
- "quickly" is an adverb

Similarly, we can recognize important entities such as people, locations, companies, and organizations:

```text
Elon Musk founded SpaceX.
```

Here:

- Elon Musk → Person
- SpaceX → Organization

Part-of-Speech (POS) Tagging and Named Entity Recognition (NER) are two of the most fundamental language understanding tasks in NLP. They form the foundation for more advanced applications such as:

- Information Extraction
- Machine Translation
- Question Answering
- Search Engines
- Chatbots
- Knowledge Graphs

In this tutorial, we explore word classes, POS tagging, named entities, BIO tagging, and the machine learning techniques used to perform these tasks.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Understand word classes in English

✅ Distinguish open-class and closed-class words

✅ Explain Part-of-Speech tagging

✅ Understand POS ambiguity

✅ Explain the challenges of POS tagging

✅ Understand Named Entity Recognition (NER)

✅ Identify common entity types

✅ Explain BIO tagging

✅ Understand sequence labelling approaches

✅ Describe common POS tagging and NER algorithms

✅ Understand real-world applications of POS tagging and NER

---

# 1. Understanding Parts of Speech

One of the oldest ideas in linguistics is that words can be grouped into grammatical categories.

These categories are known as:

```text
Parts of Speech (POS)
```

or

```text
Word Classes
```

---

## Common Word Classes

Examples include:

```text
Noun

Verb

Adjective

Adverb

Pronoun

Preposition

Conjunction

Determiner
```

---

## Example

Sentence:

```text
The young boy runs quickly.
```

Analysis:

```text
The      → Determiner

young    → Adjective

boy      → Noun

runs     → Verb

quickly  → Adverb
```

---

## Illustration

```text
Sentence
      ↓
Identify Word Roles
      ↓
Part-of-Speech Tags
```

---

# 2. Open-Class vs Closed-Class Words

Linguists often divide words into two broad categories.

---

## Open-Class Words

These categories constantly accept new words.

Examples:

```text
Nouns

Verbs

Adjectives

Adverbs
```

---

Examples:

```text
smartphone

podcast

google (verb)

cryptocurrency
```

New words regularly enter these categories.

---

## Closed-Class Words

These categories rarely change.

Examples:

```text
the

a

an

on

under

she

he

they
```

---

## Illustration

```text
Words
  │
  ├── Open Class
  │      ├─ Nouns
  │      ├─ Verbs
  │      ├─ Adjectives
  │      └─ Adverbs
  │
  └── Closed Class
         ├─ Determiners
         ├─ Pronouns
         ├─ Prepositions
         └─ Conjunctions
```

---

# 3. What is Part-of-Speech Tagging?

Part-of-Speech Tagging is the process of assigning a grammatical label to every word in a sentence.

---

## Example

Sentence:

```text
The students completed the assignment.
```

POS Tags:

```text
The          DET

students     NOUN

completed    VERB

the          DET

assignment   NOUN
```

---

## Illustration

```text
Input Sentence
       ↓
POS Tagger
       ↓
Tagged Sentence
```

---

# 4. Why Is POS Tagging Important?

Many NLP systems rely on grammatical information.

POS tagging improves:

---

## Parsing

Understanding sentence structure.

---

## Machine Translation

Different languages often arrange words differently.

Example:

```text
Adjective + Noun
```

versus

```text
Noun + Adjective
```

---

## Sentiment Analysis

Adjectives frequently carry sentiment.

Examples:

```text
amazing

excellent

terrible

awful
```

---

## Text-to-Speech Systems

Correct pronunciation often depends on grammatical role.

Example:

```text
lead
```

can be:

```text
Verb

or

Metal
```

depending on context.

---

# 5. POS Ambiguity

Many words belong to multiple word classes.

---

## Example: "book"

Sentence 1:

```text
Book that flight.
```

Tag:

```text
Verb
```

---

Sentence 2:

```text
Hand me that book.
```

Tag:

```text
Noun
```

---

## Illustration

```text
book
  │
  ├── Noun
  └── Verb
```

---

# 6. Why POS Tagging Is Difficult

Not all words have a single grammatical role.

---

## Example: "back"

Sentence:

```text
a back seat
```

Tag:

```text
Adjective
```

---

Sentence:

```text
sit in the back
```

Tag:

```text
Noun
```

---

Sentence:

```text
they back the proposal
```

Tag:

```text
Verb
```

---

Sentence:

```text
back then
```

Tag:

```text
Adverb
```

---

One word may have multiple possible tags.

---

# 7. Sources of Information for POS Tagging

POS taggers rely on several clues.

---

## Prior Probabilities

Some words strongly favour particular tags.

Example:

```text
will
```

often functions as:

```text
Auxiliary Verb
```

---

## Neighbouring Words

Context helps disambiguate meaning.

Example:

```text
the ___
```

The following word is likely a noun.

---

## Morphology

Prefixes and suffixes provide clues.

Examples:

```text
quickly
```

Suffix:

```text
-ly
```

often indicates:

```text
Adverb
```

---

## Capitalization

Example:

```text
Melbourne
```

Capitalization suggests:

```text
Proper Noun
```

---

# 8. POS Tagging Algorithms

Modern POS tagging is treated as a sequence labelling problem.

---

## Classical Approaches

### Hidden Markov Models (HMM)

Uses probabilities and state transitions.

---

### Conditional Random Fields (CRF)

Models tag dependencies explicitly.

---

## Deep Learning Approaches

### Recurrent Neural Networks

Process words sequentially.

---

### Transformers

Models such as:

```text
BERT

RoBERTa

DistilBERT
```

achieve excellent performance.

---

# 9. What is a Named Entity?

A Named Entity refers to a real-world object that can be identified by name.

---

## Common Entity Types

### Person (PER)

Examples:

```text
Albert Einstein

Taylor Swift
```

---

### Organization (ORG)

Examples:

```text
Microsoft

Google

NASA
```

---

### Location (LOC)

Examples:

```text
Melbourne

Sydney

London
```

---

### Geo-Political Entity (GPE)

Examples:

```text
Australia

Canada

Japan
```

---

# 10. Named Entity Recognition (NER)

Named Entity Recognition automatically:

1. Identifies entities.
2. Determines their type.

---

## Example

Sentence:

```text
Steve Jobs founded Apple in California.
```

Output:

```text
Steve Jobs    → PERSON

Apple         → ORGANIZATION

California    → LOCATION
```

---

## Illustration

```text
Sentence
     ↓
NER System
     ↓
Named Entities
```

---

# 11. Why Is NER Important?

NER serves as a building block for many applications.

---

## Information Extraction

Extract facts from text.

---

## Question Answering

Question:

```text
Who founded Microsoft?
```

NER identifies:

```text
Microsoft
```

as an organization.

---

## Sentiment Analysis

Determine sentiment toward:

```text
People

Companies

Products
```

---

## Search Engines

Improve retrieval and ranking.

---

# 12. Challenges in NER

NER is more difficult than POS tagging.

---

## Entity Boundaries

The system must determine:

```text
Where An Entity Starts

and

Where It Ends
```

---

Example:

```text
University of Melbourne
```

Should be treated as:

```text
One Entity
```

rather than:

```text
University

Melbourne
```

---

## Type Ambiguity

Example:

```text
Washington
```

Could refer to:

```text
Person

City

State
```

depending on context.

---

# 13. Multi-Word Entities

Many entities span multiple words.

Examples:

```text
New York City

University of Melbourne

United Nations
```

---

## Illustration

```text
New York City
│    │    │
└────┴────┘

Single Entity
```

---

# 14. BIO Tagging

To turn NER into a sequence-labelling problem, we use:

```text
BIO Tags
```

---

## B

Beginning of an entity.

---

## I

Inside an entity.

---

## O

Outside any entity.

---

# 15. BIO Tagging Example

Sentence:

```text
Barack Obama lives in Washington.
```

Tagged:

```text
Barack        B-PER

Obama         I-PER

lives         O

in            O

Washington    B-LOC
```

---

## Illustration

```text
B = Begin

I = Inside

O = Outside
```

---

# 16. Why BIO Tagging Works

BIO tagging converts an NER task into:

```text
One Tag Per Word
```

which allows standard sequence-learning algorithms to be used.

---

## Workflow

```text
Sentence
      ↓
Tokenization
      ↓
BIO Tags
      ↓
NER Model
```

---

# 17. Machine Learning for NER

NER is typically solved using supervised learning.

---

## Training Data

Example:

```text
Barack      B-PER

Obama       I-PER

visited     O

Australia   B-LOC
```

---

The model learns patterns and predicts tags for unseen text.

---

# 18. Common NER Algorithms

---

## Hidden Markov Models

Early probabilistic method.

---

## Conditional Random Fields

Widely used before deep learning.

---

## RNN-Based Models

Learn sequential relationships.

---

## Transformer Models

Examples:

```text
BERT

RoBERTa

DistilBERT
```

These methods currently dominate practical NLP systems.

---

# 19. POS Tagging vs NER

| Feature | POS Tagging | NER |
|----------|----------|----------|
| Goal | Grammar | Entity Detection |
| Output | Noun, Verb, Adjective | Person, Location, Organization |
| Every Word Tagged | Yes | Yes (BIO Format) |
| Focus | Syntax | Meaning |

---

## Example

Sentence:

```text
Google hired John Smith.
```

---

POS Tags:

```text
Google     NOUN

hired      VERB

John       PROPN

Smith      PROPN
```

---

NER Tags:

```text
Google     ORG

John Smith PERSON
```

---

# 20. NLP Pipeline Integration

POS tagging and NER are typically used together.

---

## Illustration

```text
Raw Text
     ↓
Tokenization
     ↓
Part-of-Speech Tagging
     ↓
Named Entity Recognition
     ↓
Information Extraction
     ↓
Knowledge Discovery
```

---

# Real-World Example

Sentence:

```text
Satya Nadella announced a new Microsoft initiative in Singapore.
```

---

POS Tags:

```text
Satya       PROPN

Nadella     PROPN

announced   VERB

Microsoft   PROPN

Singapore   PROPN
```

---

NER Output:

```text
Satya Nadella → PERSON

Microsoft     → ORGANIZATION

Singapore     → LOCATION
```

---

The extracted entities can then be used for:

- Information Extraction
- Knowledge Graph Construction
- Search Systems
- Business Intelligence

---

# Summary

In this tutorial we explored:

- Parts of Speech
- Open-Class and Closed-Class Words
- Part-of-Speech Tagging
- POS Ambiguity
- POS Tagging Algorithms
- Named Entities
- Named Entity Recognition (NER)
- Entity Types
- Multi-Word Entities
- BIO Tagging
- Sequence Labelling
- NER Algorithms

Part-of-Speech Tagging and Named Entity Recognition are among the most important foundational tasks in NLP. Together, they help computers understand not only the grammatical structure of text but also the important real-world entities contained within it. These capabilities form the basis for many advanced NLP applications, including information extraction, question answering, search engines, and conversational AI.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define Parts of Speech.

✅ Differentiate open-class and closed-class words.

✅ Explain POS tagging.

✅ Describe POS ambiguity.

✅ Explain why POS tagging is useful.

✅ Identify common named entity types.

✅ Explain Named Entity Recognition.

✅ Describe BIO tagging.

✅ Explain sequence labelling.

✅ Compare POS tagging and NER.

✅ Identify major machine learning approaches for POS tagging and NER.

✅ Understand how POS tagging and NER support advanced NLP applications.
