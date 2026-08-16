# Tutorial 07: Deep Learning Architectures for Sequence Processing

## Overview

Traditional machine learning techniques such as Bag of Words, TF-IDF, and Naïve Bayes have been highly successful for many NLP tasks. However, these methods often ignore one of the most important characteristics of language:

```text
Language is sequential.
```

Consider the following sentences:

```text
The dog chased the cat.
```

and

```text
The cat chased the dog.
```

A Bag of Words representation would treat these sentences as almost identical because they contain the same words.

Humans, however, immediately understand that the meanings are very different due to the order of words.

To address this limitation, Deep Learning introduced architectures specifically designed to process sequences. These architectures can remember previous information, capture context, and learn relationships across long stretches of text.

This tutorial introduces the key deep learning models used in NLP:

- Recurrent Neural Networks (RNNs)
- Language Models
- Sequence Classification
- Sequence Labelling
- Stacked RNNs
- Bidirectional RNNs
- Long Short-Term Memory (LSTM)
- Gated Recurrent Units (GRU)
- Transformers

These models form the foundation of modern NLP systems such as BERT, GPT, ChatGPT, and many advanced language technologies.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain why sequence processing is important

✅ Understand the limitations of traditional neural networks

✅ Describe Recurrent Neural Networks (RNNs)

✅ Explain RNN-based language models

✅ Understand sequence classification and sequence labelling

✅ Explain stacked and bidirectional RNNs

✅ Describe the vanishing gradient problem

✅ Explain Long Short-Term Memory (LSTM)

✅ Understand Gated Recurrent Units (GRU)

✅ Explain self-attention and Transformers

✅ Understand the evolution of modern NLP architectures

---

# 1. Why Language Requires Sequence Processing

Human language unfolds over time.

When reading this sentence:

```text
The weather today is beautiful.
```

we process each word sequentially and continuously update our understanding.

---

## Traditional Machine Learning Problem

Methods such as:

```text
Bag of Words

TF-IDF

Naïve Bayes
```

typically ignore word order.

Example:

```text
Cats chase dogs.
```

and

```text
Dogs chase cats.
```

may appear very similar numerically.

---

## Illustration

```text
Word 1 → Word 2 → Word 3 → Word 4
```

Language understanding depends heavily on this order.

---

# 2. Fixed-Window Language Models

Before RNNs became popular, many neural language models used:

```text
Sliding Windows
```

to process text.

---

## Example

Sentence:

```text
The cat sat on the mat
```

Window Size = 3

Processing:

```text
The cat sat

cat sat on

sat on the

on the mat
```

---

## Illustration

```text
[The cat sat]
      ↓
Prediction

[cat sat on]
      ↓
Prediction

[sat on the]
      ↓
Prediction
```

---

## Limitation

The model can only see a small portion of the sentence.

Words outside the window are ignored.

---

# 3. Challenges with Sliding Windows

Suppose we encounter:

```text
The flights that the airline was cancelling were full.
```

Understanding:

```text
were
```

depends on:

```text
flights
```

which may appear far away.

---

Window-based systems struggle because:

```text
Long-Distance Dependencies
```

are difficult to capture.

---

## Key Problem

```text
Important Words
      ↓
Too Far Away
      ↓
Context Lost
```

---

# 4. Recurrent Neural Networks (RNNs)

Recurrent Neural Networks were introduced to handle sequential data naturally.

Unlike traditional networks, RNNs contain:

```text
Memory
```

through recurrent connections.

---

## Core Idea

At every step, the network receives:

```text
Current Input
```

and

```text
Previous Hidden State
```

---

## Illustration

```text
Word₁
   ↓
  RNN
   ↓
Hidden State₁
        │
        ▼

Word₂
   ↓
  RNN
   ↓
Hidden State₂
```

---

The hidden state acts as memory.

---

# 5. How RNNs Work

At each time step:

```text
Current Word
```

and

```text
Previous Memory
```

are combined.

---

## Illustration

```text
Current Input
        +
Previous State
        ↓
Hidden Layer
        ↓
Output
```

---

This process repeats for every word in the sequence.

---

# 6. Why RNNs Are Powerful

Unlike fixed-window models:

```text
RNNs
```

can theoretically remember information from anywhere in the sequence.

---

Example:

```text
The book that I bought yesterday was excellent.
```

The model can retain information about:

```text
book
```

while processing:

```text
excellent
```

later in the sentence.

---

# 7. RNNs as Language Models

One of the most important NLP tasks is:

```text
Language Modelling
```

---

## Goal

Predict the next word.

Example:

```text
I drink coffee every
```

Prediction:

```text
morning
```

---

## Illustration

```text
Input Words
      ↓
RNN
      ↓
Probability Distribution
      ↓
Next Word Prediction
```

---

# 8. Text Generation with RNNs

After training a language model, we can generate text.

---

## Process

Start with:

```text
<START>
```

Generate:

```text
Word 1
```

Then:

```text
Word 2
```

Then:

```text
Word 3
```

and continue.

---

## Illustration

```text
START
   ↓
Word₁
   ↓
Word₂
   ↓
Word₃
   ↓
END
```

---

This is known as:

```text
Autoregressive Generation
```

---

# 9. Applications of RNNs

RNNs can be used for many NLP tasks.

Examples:

- Language Modelling
- Sentiment Analysis
- Spam Detection
- POS Tagging
- Named Entity Recognition
- Machine Translation
- Question Answering

---

# 10. Sequence Labelling

Some NLP tasks require a label for every word.

This is called:

```text
Sequence Labelling
```

---

## Example

Part-of-Speech Tagging

Input:

```text
The dog runs
```

Output:

```text
The   → DET

dog   → NOUN

runs  → VERB
```

---

## Illustration

```text
Word
   ↓
RNN
   ↓
Label
```

for every token.

---

# 11. Sequence Classification

Other tasks require one label for an entire sequence.

---

## Example

Movie Review:

```text
This film was fantastic.
```

Output:

```text
Positive
```

---

## Workflow

```text
Sentence
     ↓
RNN Processes Entire Sequence
     ↓
Final Hidden State
     ↓
Classifier
     ↓
Prediction
```

---

# 12. Stacked RNNs

A single RNN layer may not capture enough complexity.

Solution:

```text
Stack Multiple RNN Layers
```

---

## Illustration

```text
Input Layer
      ↓
RNN Layer 1
      ↓
RNN Layer 2
      ↓
RNN Layer 3
      ↓
Output
```

---

## Advantages

- Better feature learning
- Higher abstraction levels
- Improved performance

---

# 13. Bidirectional RNNs

Traditional RNNs process text:

```text
Left → Right
```

only.

---

Example:

```text
The bank approved the loan.
```

Understanding:

```text
bank
```

 might benefit from future context.

---

## Solution

Use:

```text
Bidirectional RNN
```

---

# 14. How Bidirectional RNNs Work

They process text in:

### Forward Direction

```text
Left → Right
```

and

### Backward Direction

```text
Right → Left
```

simultaneously.

---

## Illustration

```text
Forward RNN
      →

Sentence

←
Backward RNN
```

---

Both contexts are combined.

---

# 15. Benefits of Bidirectional RNNs

The model can use:

```text
Past Context

and

Future Context
```

at the same time.

---

This greatly improves tasks such as:

- POS Tagging
- Named Entity Recognition
- Machine Translation

---

# 16. The Vanishing Gradient Problem

Although RNNs are powerful, they suffer from a major limitation.

---

## Problem

During training:

```text
Gradients
```

must pass through many time steps.

Repeated multiplication causes:

```text
Very Small Gradients
```

---

Eventually:

```text
Gradient ≈ 0
```

---

The network stops learning long-distance relationships.

---

## Illustration

```text
Long Sequence
        ↓
Repeated Updates
        ↓
Gradient Shrinks
        ↓
Memory Loss
```

---

# 17. Why Vanishing Gradients Matter

Consider:

```text
The flights that the airline was cancelling were full.
```

To correctly predict:

```text
were
```

the model must remember:

```text
flights
```

which appeared much earlier.

---

Traditional RNNs often forget such information.

---

# 18. Long Short-Term Memory (LSTM)

LSTM networks were designed specifically to solve the vanishing gradient problem.

---

## Core Idea

LSTMs introduce:

```text
Memory Cells
```

and

```text
Gates
```

that control information flow.

---

## Main Objective

Learn:

```text
What To Remember

and

What To Forget
```

---

# 19. LSTM Architecture

An LSTM contains three important gates.

---

## Forget Gate

Determines:

```text
What Information Should Be Removed
```

---

## Input Gate

Determines:

```text
What New Information Should Be Stored
```

---

## Output Gate

Determines:

```text
What Information Should Be Used
```

---

## Illustration

```text
Input
   ↓
Forget Gate
   ↓
Memory Cell
   ↓
Output Gate
```

---

# 20. Benefits of LSTMs

✅ Handle long sequences

✅ Preserve important information

✅ Reduce vanishing gradients

✅ Improve performance significantly

---

Applications include:

- Translation
- Language Modelling
- Chatbots
- Speech Recognition

---

# 21. Gated Recurrent Units (GRU)

GRUs were introduced as a simpler alternative to LSTMs.

---

## Main Idea

Reduce complexity while maintaining performance.

---

GRUs use only:

### Reset Gate

Determines what past information to ignore.

---

### Update Gate

Determines what information to keep.

---

## Illustration

```text
Input
   ↓
Reset Gate
   ↓
Update Gate
   ↓
Output
```

---

# 22. LSTM vs GRU

| Feature | LSTM | GRU |
|----------|----------|----------|
| Memory Cell | Yes | No |
| Gates | 3 | 2 |
| Parameters | More | Fewer |
| Training Speed | Slower | Faster |
| Performance | Strong | Often Similar |

---

Both remain widely used.

---

# 23. Limitations of RNN-Based Models

Even LSTMs and GRUs have limitations.

---

## Sequential Processing

Words must be processed one by one.

---

## Slow Training

Long sequences require many sequential computations.

---

## Context Bottlenecks

Important information may still degrade over time.

---

# 24. The Rise of Transformers

Transformers revolutionized NLP.

The key innovation was:

```text
Self-Attention
```

---

Instead of relying on sequential memory, Transformers directly examine relationships between words.

---

# 25. Self-Attention

Self-attention allows a word to focus on any other word in a sentence.

---

Example:

```text
The animal didn't cross the street because it was tired.
```

To understand:

```text
it
```

the model can directly examine:

```text
animal
```

without passing information through many steps.

---

## Illustration

```text
Word
  ↘
   ↘
    ↘
 Other Words
```

---

# 26. Transformer Architecture

Transformers are built using:

- Self-Attention Layers
- Feedforward Layers
- Positional Encoding

---

## Workflow

```text
Input Tokens
      ↓
Embeddings
      ↓
Self-Attention
      ↓
Feedforward Layers
      ↓
Output
```

---

# 27. Advantages of Transformers

✅ Parallel processing

✅ Faster training

✅ Better long-range understanding

✅ Improved scalability

✅ State-of-the-art performance

---

These advantages led to the development of:

```text
BERT

GPT

T5

LLaMA

Claude

ChatGPT
```

---

# 28. Modern NLP Pipeline

Today, many NLP systems follow:

```text
Text
   ↓
Tokenization
   ↓
Embeddings
   ↓
Transformer
   ↓
Prediction
```

---

# Evolution of NLP Architectures

```text
Bag of Words
       ↓
Feedforward Networks
       ↓
RNN
       ↓
LSTM / GRU
       ↓
Transformer
       ↓
Large Language Models
```

---

# Real-World Applications

These architectures now power:

### Search Engines

Understanding search queries.

---

### Virtual Assistants

Siri, Alexa, Google Assistant.

---

### Machine Translation

Google Translate.

---

### Chatbots

Customer support and conversational agents.

---

### Large Language Models

ChatGPT, Copilot, Gemini, Claude.

---

# Summary

In this tutorial we explored:

- Sequence Processing
- Language Modelling
- Recurrent Neural Networks (RNNs)
- Sequence Labelling
- Sequence Classification
- Stacked RNNs
- Bidirectional RNNs
- Vanishing Gradients
- Long Short-Term Memory (LSTM)
- Gated Recurrent Units (GRU)
- Self-Attention
- Transformers

Deep learning fundamentally changed Natural Language Processing by enabling models to understand sequences, capture context, and learn complex linguistic patterns. The progression from RNNs to LSTMs, GRUs, and ultimately Transformers laid the foundation for the modern language models that power many AI applications today.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Explain why language is a sequential problem.

✅ Identify limitations of fixed-window models.

✅ Describe Recurrent Neural Networks.

✅ Explain language modelling with RNNs.

✅ Differentiate sequence classification and sequence labelling.

✅ Explain stacked RNNs.

✅ Explain bidirectional RNNs.

✅ Describe the vanishing gradient problem.

✅ Explain how LSTMs solve memory issues.

✅ Describe GRUs and compare them to LSTMs.

✅ Explain self-attention.

✅ Describe Transformer architectures.

✅ Explain the evolution of modern NLP models.
