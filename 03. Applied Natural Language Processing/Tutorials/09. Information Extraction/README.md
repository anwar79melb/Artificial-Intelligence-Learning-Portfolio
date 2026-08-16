# Tutorial 09: Information Extraction

## Overview

Organizations generate enormous volumes of unstructured text every day through news articles, emails, reports, social media posts, research publications, and business documents. While this information contains valuable knowledge, it is often buried within paragraphs of natural language.

**Information Extraction (IE)** is the process of automatically converting unstructured text into structured information that computers can understand, store, analyze, and use for decision-making.

Rather than simply reading text, Information Extraction seeks to answer questions such as:

- Who is involved?
- What happened?
- When did it happen?
- Where did it happen?
- What relationships exist?
- What facts can be stored in a database?

Information Extraction forms the foundation for many advanced NLP applications, including:

- Knowledge Graphs
- Question Answering Systems
- Search Engines
- Business Intelligence
- Cybersecurity Monitoring
- Healthcare Analytics
- Conversational AI

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define Information Extraction

✅ Explain Relation Extraction

✅ Understand Knowledge Graphs

✅ Explain Event Extraction

✅ Identify Temporal Expressions

✅ Understand Template Filling

✅ Describe supervised and unsupervised relation extraction

✅ Explain Open Information Extraction

✅ Evaluate Information Extraction systems

✅ Understand real-world applications of Information Extraction

---

# 1. What is Information Extraction?

Information Extraction (IE) transforms unstructured text into structured information that can be stored and processed automatically.

---

## Example

Raw Text:

```text
Microsoft announced a new AI platform in Sydney on Tuesday.
```

Structured Information:

```text
Organization: Microsoft

Event: Product Announcement

Location: Sydney

Date: Tuesday
```

---

## Illustration

```text
Raw Text
      ↓
Information Extraction
      ↓
Structured Data
      ↓
Database / Knowledge Base
```

---

# 2. Why Information Extraction Matters

Imagine an investment company that wants to monitor airline fare increases.

Thousands of news articles are published daily.

Instead of manually reading every article, an Information Extraction system can automatically identify:

```text
Airline Name

Fare Increase

Date

Affected Routes

Competitors
```

and store the information in a structured database. 【1-88d031】

---

## Example Workflow

```text
News Articles
       ↓
Information Extraction
       ↓
Database
       ↓
Analysis and Reporting
```

---

# 3. Information Extraction Pipeline

Most Information Extraction systems follow a sequence of steps.

```text
Raw Text
     ↓
Tokenization
     ↓
POS Tagging
     ↓
Named Entity Recognition
     ↓
Relation Extraction
     ↓
Event Extraction
     ↓
Structured Knowledge
```

---

## Visual Concept



---

# 4. Components of Information Extraction

Information Extraction generally consists of:

### Named Entity Recognition

Identify entities.

Example:

```text
Google
Australia
Elon Musk
```

---

### Relation Extraction

Identify relationships between entities.

---

### Event Extraction

Identify actions and events.

---

### Temporal Extraction

Identify dates and times.

---

### Template Filling

Populate predefined structures automatically.

---

# 5. Relation Extraction

Relation Extraction identifies relationships that exist between entities within text.

---

## Example

Sentence:

```text
Bill Gates founded Microsoft.
```

Entities:

```text
Bill Gates

Microsoft
```

Relationship:

```text
FounderOf
```

---

## Structured Output

```text
(Bill Gates)
      │
 FounderOf
      │
(Microsoft)
```

---

# 6. Types of Semantic Relationships

Many kinds of relationships can occur in language.

---

## Employment

```text
Satya Nadella works for Microsoft.
```

Relationship:

```text
WorksFor
```

---

## Location

```text
John lives in Melbourne.
```

Relationship:

```text
LivesIn
```

---

## Family

```text
Sarah is Tom's sister.
```

Relationship:

```text
SiblingOf
```

---

## Ownership

```text
Tesla acquired SolarCity.
```

Relationship:

```text
Acquired
```

---

# 7. Why Relation Extraction Is Important

Relation Extraction allows computers to move beyond recognizing entities and begin understanding facts.

---

## Example

Named Entity Recognition finds:

```text
Apple

Tim Cook
```

---

Relation Extraction determines:

```text
Tim Cook
     │
 CEOOf
     │
Apple
```

---

This enables:

- Search systems
- Knowledge bases
- Recommendation systems
- Question answering systems

---

# 8. Knowledge Graphs

A Knowledge Graph is a structured representation of entities and their relationships.

---

## Example

```text
Steve Jobs
      │
 FounderOf
      │
Apple
      │
 LocatedIn
      │
California
```

---

## Why Knowledge Graphs Matter

Knowledge Graphs are used by:

- Search engines
- Virtual assistants
- Recommendation platforms
- Question answering systems

---

## Illustration

```text
Entity
   ↓
Relationship
   ↓
Entity
```

---

# 9. Event Extraction

Event Extraction focuses on identifying actions and events described in text.

---

## Example

Sentence:

```text
United Airlines increased fares by $6.
```

Extracted Information:

```text
Organization:
United Airlines

Event:
Fare Increase

Amount:
$6
```

---

# 10. Why Event Extraction Matters

Organizations often need to monitor events automatically.

Examples:

```text
Product Launches

Acquisitions

Cybersecurity Attacks

Medical Discoveries

Natural Disasters
```

---

Instead of reading thousands of reports manually, event extraction systems can detect important events automatically.

---

# 11. Event Coreference

The same event may be described using multiple expressions.

---

## Example

```text
The company announced a merger.

The deal was finalized yesterday.

The agreement received regulatory approval.
```

These sentences may all refer to:

```text
The Same Merger Event
```

Event extraction systems attempt to connect these references.

---

# 12. Temporal Expressions

Temporal Expressions identify time-related information within text.

---

## Examples

```text
Monday

Tomorrow

Next Week

January 2026

3:30 PM
```

---

# 13. Why Temporal Information Matters

Events become far more useful when we know when they occurred.

---

## Example

Text:

```text
The fare increase took effect Thursday.

The announcement was made Friday.
```

Timeline:

```text
Thursday → Fare Increase

Friday → Announcement
```

---

Timeline information is vital for:

- News analysis
- Finance
- Healthcare
- Legal systems

---

# 14. Template Filling

Many documents follow recurring patterns.

Template Filling automatically extracts information and places it into predefined fields.

---

## Example

Text:

```text
United Airlines increased fares by $6 on Thursday.
```

Output:

```text
Airline:
United Airlines

Amount:
$6

Date:
Thursday
```

---

## Illustration

```text
Text Document
      ↓
Extract Facts
      ↓
Fill Template
```

---

# 15. Information Extraction vs Information Retrieval

These concepts are often confused.

---

## Information Retrieval (IR)

Goal:

```text
Find Relevant Documents
```

Example:

```text
Google Search
```

---

## Information Extraction (IE)

Goal:

```text
Extract Facts
```

Example:

```text
Who founded Microsoft?
```

Output:

```text
Bill Gates
```

---

# 16. Pattern-Based Relation Extraction

One of the earliest approaches uses manually designed patterns.

---

## Example

Sentence:

```text
Cats such as Persian and Siamese are popular pets.
```

Pattern:

```text
such as
```

Relationship:

```text
Persian → TypeOf → Cat

Siamese → TypeOf → Cat
```

---

These patterns are known as:

```text
Hearst Patterns
```

---

# 17. Supervised Relation Extraction

A more modern approach uses machine learning.

---

## Workflow

### Step 1

Annotate training data.

---

### Step 2

Identify entities.

---

### Step 3

Train a classifier.

---

### Step 4

Predict relationships in new text.

---

## Illustration

```text
Labelled Data
      ↓
Training
      ↓
Classifier
      ↓
Relation Prediction
```

---

# 18. Machine Learning Models for Relation Extraction

Various algorithms can be used.

---

## Traditional Models

```text
Logistic Regression

Random Forest

Support Vector Machine
```

---

## Deep Learning Models

```text
RNN

LSTM

Transformer

BERT
```

---

# 19. Semi-Supervised Relation Extraction

Creating labelled datasets is expensive.

Semi-supervised approaches attempt to learn from a small amount of labelled data.

---

## Bootstrapping

Start with:

```text
A Few Seed Examples
```

and then automatically find:

```text
Additional Patterns

Additional Relationships
```

from large document collections.

---

# 20. Distant Supervision

Distant supervision uses existing databases and knowledge bases as training sources.

---

## Example

Knowledge Base:

```text
Bill Gates → Microsoft
```

---

The system searches text containing both entities and learns patterns automatically.

---

## Advantage

Large training datasets can be generated without extensive manual annotation.

---

# 21. Open Information Extraction (Open IE)

Traditional systems define relationships in advance.

Open Information Extraction removes this restriction.

---

## Example

Sentence:

```text
The company acquired a startup.
```

Open IE Output:

```text
(company,
 acquired,
 startup)
```

---

The system discovers relationships directly from text.

---

# 22. Advantages of Open IE

✅ No predefined relationships

✅ Works across domains

✅ Handles unseen relationship types

✅ Scales well to large datasets

---

# 23. Evaluating Information Extraction Systems

Evaluation determines how well the system performs.

---

## Precision

Measures:

```text
How Many Extracted Facts Are Correct?
```

---

## Recall

Measures:

```text
How Many Correct Facts Were Found?
```

---

## F1 Score

Balances:

```text
Precision

and

Recall
```

---

# 24. Example Evaluation

Suppose:

```text
100 Relationships Exist
```

System extracts:

```text
90 Relationships
```

of which:

```text
80 Are Correct
```

---

Metrics:

```text
Precision = 80 / 90

Recall = 80 / 100
```

---

These measures help compare different Information Extraction systems.

---

# 25. Real-World Applications

Information Extraction is used across many industries.

---

## Finance

Extract:

```text
Company Mergers

Acquisitions

Stock Events
```

---

## Healthcare

Extract:

```text
Diseases

Symptoms

Treatments
```

---

## News Analytics

Extract:

```text
People

Organizations

Events
```

---

## Cybersecurity

Extract:

```text
Threat Actors

Attack Methods

Vulnerabilities
```

---

## Question Answering Systems

Extract facts used to answer user queries.

---

# Complete Information Extraction Pipeline

```text
Raw Text
     ↓
Named Entity Recognition
     ↓
Relation Extraction
     ↓
Event Extraction
     ↓
Temporal Extraction
     ↓
Template Filling
     ↓
Knowledge Base
```

---

# Summary

In this tutorial we explored:

- Information Extraction
- Relation Extraction
- Knowledge Graphs
- Event Extraction
- Event Coreference
- Temporal Expressions
- Template Filling
- Hearst Patterns
- Supervised Relation Extraction
- Semi-Supervised Learning
- Distant Supervision
- Open Information Extraction
- Precision, Recall, and F1 Evaluation

Information Extraction is a critical step in transforming human language into structured knowledge. By identifying entities, relationships, events, and temporal information, NLP systems can build knowledge bases, power search engines, support question answering systems, and uncover valuable insights hidden within massive collections of text.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define Information Extraction.

✅ Explain Relation Extraction.

✅ Describe Knowledge Graphs.

✅ Explain Event Extraction.

✅ Identify Temporal Expressions.

✅ Explain Template Filling.

✅ Describe Hearst Patterns.

✅ Explain supervised relation extraction.

✅ Understand distant supervision.

✅ Describe Open Information Extraction.

✅ Evaluate Information Extraction systems using Precision, Recall, and F1-score.

✅ Explain the role of Information Extraction in modern NLP systems.
