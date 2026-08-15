# Tutorial 02: Build Your Own Corpus (BYOC)

## Overview

Before any Natural Language Processing system can be developed, it requires data. Whether the goal is sentiment analysis, chatbot development, topic modelling, machine translation, or question answering, the quality of the results depends heavily on the quality of the text used during training and analysis.

This tutorial introduces the concept of a **corpus**, the foundation of almost every NLP project. You will learn what a corpus is, the characteristics of a good corpus, and how textual data can be collected from online sources such as Twitter (X), Facebook, Reddit, and public web repositories.

A common principle in data science states:

```text
Garbage In
      ↓
Garbage Out
```

No matter how sophisticated a machine learning model is, poor-quality data will lead to poor-quality results. Therefore, building a reliable corpus is one of the most important stages in any NLP workflow.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define a corpus and corpora

✅ Explain the role of corpora in NLP

✅ Identify common sources of text data

✅ Describe the characteristics of a good corpus

✅ Understand how social media data can be collected

✅ Understand API-based data collection

✅ Explain corpus construction workflows

✅ Evaluate the strengths and limitations of different data sources

✅ Understand ethical considerations when collecting online text data

---

# 1. What is a Corpus?

A **corpus** is a collection of textual documents used for language analysis and NLP tasks.

The plural form of corpus is:

```text
Corpora
```

---

## Simple Definition

```text
Corpus = Collection of Text Documents
```

These documents may be stored as:

- Text files
- Articles
- News reports
- Social media posts
- Emails
- Research papers
- Reviews
- Chat conversations

---

## Illustration

```text
Document 1
Document 2
Document 3
Document 4
      ↓
    Corpus
```

---

## Example

Imagine collecting:

```text
100,000 Movie Reviews
```

and storing them together.

The combined collection becomes a:

```text
Movie Review Corpus
```

which can later be used for:

- Sentiment analysis
- Recommendation systems
- Review classification

---

# 2. Why Do We Need a Corpus?

Machines learn from data.

Before an NLP model can perform tasks such as:

- Text Classification
- Sentiment Analysis
- Machine Translation
- Chatbots
- Question Answering

it must first observe large amounts of language data.

---

## Illustration

```text
Raw Text
     ↓
Corpus
     ↓
Preprocessing
     ↓
Machine Learning
     ↓
NLP Tasks
```

---

## Example

To build:

```text
Spam Detection
```

we need:

```text
Thousands of Spam Emails

and

Thousands of Legitimate Emails
```

These messages form the corpus used for training.

---

# 3. Sources of Corpora

Corpora can be obtained from many different sources.

---

## Public Web Data

Examples:

- Websites
- Blogs
- Forums
- News Articles

---

## Social Media

Examples:

- Twitter (X)
- Facebook
- Reddit
- LinkedIn
- Instagram comments

---

## Academic Repositories

Examples:

- Wikipedia
- Open Research Datasets
- Government Archives

---

## Business Data

Examples:

- Customer reviews
- Support tickets
- Call transcripts

---

## Illustration

```text
Websites
     │
Social Media
     │
Research Data
     │
Business Records
     │
     ▼
   Corpus
```

---

# 4. Existing Corpora Available Online

In many projects, you may not need to build a corpus from scratch.

Large corpora are already available online.

---

## English Corpora

Many English-language corpora are available through public repositories.

These collections contain:

- Books
- Newspapers
- Academic writing
- Spoken language
- Web text

---

## Wikipedia Corpus

One of the largest publicly available text corpora.

Characteristics:

```text
Millions of Articles

Billions of Words

Multiple Languages
```

Wikipedia is frequently used in:

- Language modelling
- Question answering
- Information retrieval
- Knowledge extraction

---

## Illustration

```text
Wikipedia
      ↓
Millions of Articles
      ↓
Large NLP Corpus
```

---

# 5. Corpora in NLP Libraries

Many NLP tools already include built-in corpora.

Examples include:

### NLTK

Provides corpora such as:

- Gutenberg
- Reuters
- Brown Corpus
- Movie Reviews

---

### spaCy

Provides pre-trained language models built from large corpora.

---

### Hugging Face Datasets

Provides thousands of ready-to-use datasets for:

- Classification
- Translation
- Summarisation
- Question Answering

---

# 6. Characteristics of a Good Corpus

Not all corpora are equally useful.

A high-quality corpus should satisfy several requirements.

---

## 1. Large Corpus Size

More data generally allows models to learn better language patterns.

Example:

```text
100 Reviews
```

is typically less useful than:

```text
100,000 Reviews
```

---

## 2. High-Quality Data

A corpus should contain:

✅ Relevant information

✅ Correct language usage

✅ Useful content

rather than random noise.

---

## 3. Clean Data

The corpus should contain minimal:

- Duplicates
- Corrupted records
- Incomplete entries
- Irrelevant information

---

## Illustration

```text
Large
   +
Clean
   +
Relevant
   +
High Quality
   ↓
Good Corpus
```

---

# 7. Building Your Own Corpus (BYOC)

Sometimes no suitable dataset exists.

In such situations, we create our own corpus.

This process is known as:

```text
Build Your Own Corpus (BYOC)
```

---

## Reasons for BYOC

You may require data specific to:

- A company
- A topic
- A language
- A region
- A customer group

---

## Example

Suppose you want to analyse:

```text
Public Opinion on Electric Vehicles
```

You may collect:

- Tweets
- Reddit discussions
- Facebook posts
- News comments

to create a specialised corpus.

---

# 8. Social Media as a Data Source

Social media platforms generate enormous volumes of language data every day. 

Benefits include:

✅ Real-time content

✅ Large volume

✅ Diverse topics

✅ Rich sentiment information

---

## Challenges

Social media text often contains:

- Misspellings
- Slang
- Emojis
- Abbreviations
- Informal language

This makes preprocessing especially important.

---

# 9. Collecting Data from Twitter (X)

Twitter has historically been one of the most popular sources for NLP research.

Why?

Because tweets capture:

```text
Public Opinions

Breaking News

Current Events

Customer Feedback
```

---

## Typical Workflow

```text
Twitter API
      ↓
Retrieve Tweets
      ↓
Filter Tweets
      ↓
Store Data
      ↓
Build Corpus
```

---

## Data That Can Be Collected

- Tweet text
- User information
- Hashtags
- Timestamps
- Locations
- Retweet counts

---

# 10. Accessing Twitter Data

Twitter data is typically collected using APIs.

A common Python library is:

```python
tweepy
```

---

## Illustration

```text
Python Script
      ↓
Twitter API
      ↓
Tweets
      ↓
Corpus
```

---

## Typical Requirements

To access Twitter data:

1. Create a developer account
2. Create an application
3. Obtain API keys
4. Authenticate requests

---

# 11. Twitter API Credentials

Typical credentials include:

```text
Consumer Key

Consumer Secret

Access Token

Access Token Secret
```

These credentials allow programs to securely communicate with the Twitter platform.

---

# 12. Collecting Data from Facebook

Facebook provides data access using:

```text
Facebook Graph API
```

---

## What is the Graph API?

The Graph API allows developers to programmatically access data stored within Facebook's ecosystem.

Possible tasks include:

- Retrieving posts
- Accessing page information
- Reading comments
- Collecting public content

---

# 13. Facebook Graph Structure

Facebook organizes information using:

---

## Nodes

Objects such as:

```text
User

Page

Photo

Comment
```

---

## Edges

Connections between objects.

Example:

```text
Page
   ↓
Comments
```

---

## Fields

Properties of objects.

Example:

```text
Page Name

Creation Date

User Information
```

---

## Illustration

```text
Node
  │
  ├── Fields
  │
  └── Edges
```

---

# 14. Collecting Data from Reddit

Reddit is another popular source of textual data.

Advantages include:

✅ Long-form discussions

✅ Topic-based communities

✅ Large public archives

✅ Rich conversational content

---

## Why Reddit?

Reddit discussions often provide:

- Detailed opinions
- Community interactions
- Question and answer threads
- Domain-specific knowledge

---

## Illustration

```text
Reddit
    ↓
Subreddits
    ↓
Posts
    ↓
Comments
    ↓
Corpus
```

---

# 15. Reddit JSON Access

Many Reddit pages provide structured data in:

```text
JSON Format
```

This allows developers to easily retrieve:

- Posts
- Threads
- Comments
- Metadata

using scripts and APIs.

---

# 16. Corpus Construction Workflow

Regardless of the platform, corpus construction generally follows the same process.

---

## Step 1

Select a data source.

```text
Twitter

Facebook

Reddit

Wikipedia
```

---

## Step 2

Collect documents.

---

## Step 3

Store raw data.

---

## Step 4

Clean the data.

---

## Step 5

Remove duplicates.

---

## Step 6

Prepare for NLP processing.

---

## Illustration

```text
Data Source
      ↓
Collection
      ↓
Storage
      ↓
Cleaning
      ↓
Corpus
      ↓
NLP Analysis
```

---

# 17. Challenges in Corpus Construction

Building a corpus is often more difficult than training models.

Common challenges include:

---

## Data Quality

Poor-quality text can degrade performance.

---

## Data Imbalance

One topic may dominate the corpus.

---

## Noise

Examples:

- Spam
- Duplicate posts
- Advertisements

---

## API Restrictions

Platforms often restrict:

- Request volume
- Data access
- Historical access

---

## Legal and Ethical Concerns

Some data may require:

- User consent
- Anonymization
- Privacy protection

---

# Real-World Example

Suppose we wish to analyse:

```text
Public Sentiment Toward AI
```

Potential corpus sources:

| Source | Content |
|----------|----------|
| Twitter | Short public opinions |
| Reddit | Long discussions |
| News Websites | Professional articles |
| Blogs | Expert viewpoints |
| Forums | Community discussions |

Combining these sources can create a comprehensive dataset for analysis.

---

# Summary

In this tutorial we explored:

- What a corpus is
- Why corpora are important
- Existing corpora
- Corpus construction
- Characteristics of a good corpus
- Data collection from Twitter
- Data collection from Facebook
- Data collection from Reddit
- API-based data gathering
- Social media corpora
- Corpus construction workflows
- Challenges in building NLP datasets

A corpus forms the foundation of every NLP project. Before text can be classified, analysed, translated, summarised, or used to train machine learning models, it must first be collected and organised into a high-quality dataset. Building a well-designed corpus is often one of the most important steps in the entire NLP pipeline.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define a corpus.

✅ Explain the difference between corpus and corpora.

✅ Identify common corpus sources.

✅ Describe the features of a good corpus.

✅ Explain why corpus quality matters.

✅ Describe Twitter-based data collection.

✅ Describe Facebook data collection.

✅ Describe Reddit data collection.

✅ Explain API-driven corpus collection.

✅ Design a basic corpus construction workflow.

✅ Identify challenges in corpus building.

✅ Select appropriate sources for an NLP project.
