# Tutorial 06: Vector Semantics and Word Embeddings

## Overview

So far in this course, we have represented text using methods such as Bag of Words and word frequencies. While these approaches are useful, they have a major limitation:

```text
Words are treated as independent symbols.
```

For example:

```text
car

automobile
```

have very similar meanings, yet a Bag of Words model treats them as completely unrelated.

Modern NLP systems solve this problem using **Vector Semantics** and **Word Embeddings**, where words are represented as vectors in a mathematical space. Words with similar meanings are placed close together, while unrelated words are placed further apart.

This idea forms the foundation of many modern NLP systems, including:

- Search engines
- Recommendation systems
- Chatbots
- Machine Translation
- Question Answering
- Large Language Models (LLMs)

In this tutorial, we explore lexical semantics, TF-IDF, cosine similarity, vector representations, and Word2Vec embeddings.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Understand lexical semantics

✅ Explain word meaning and word senses

✅ Distinguish similarity and relatedness

✅ Understand semantic fields

✅ Explain vector semantics

✅ Understand word embeddings

✅ Represent text as vectors

✅ Compute cosine similarity conceptually

✅ Explain TF-IDF

✅ Understand sparse and dense vectors

✅ Describe Word2Vec

✅ Explain how modern embeddings are learned

---

# 1. Understanding Word Meaning

One of the fundamental questions in NLP is:

```text
What does a word mean?
```

At first glance this appears simple.

Consider:

```text
dog
```

Humans immediately understand the meaning.

Computers, however, only see:

```text
"d", "o", "g"
```

or perhaps a vocabulary index such as:

```text
word #4527
```

The challenge is teaching machines to represent meaning rather than simply storing words.

---

# 2. Lemmas and Word Senses

A word can often have multiple meanings.

---

## Lemma

A lemma is the dictionary form of a word.

Examples:

```text
run

walk

play
```

---

## Sense

A sense refers to a specific meaning of a word.

Example:

```text
mouse
```

Sense 1:

```text
Small Animal
```

Sense 2:

```text
Computer Device
```

---

## Illustration

```text
mouse
 ├── Animal
 └── Computer Device
```

This phenomenon is called:

```text
Polysemy
```

where one word has multiple senses.

---

# 3. Synonymy

Synonyms are words with very similar meanings.

Examples:

```text
car
automobile

big
large

couch
sofa
```

---

## Important Observation

Perfect synonyms rarely exist.

Even words with nearly identical meanings often differ in:

- Style
- Formality
- Context
- Social usage

---

## Example

```text
big sister
```

sounds natural.

---

```text
large sister
```

sounds unusual.

---

# 4. Similarity vs Relatedness

These concepts are often confused.

---

## Similar Words

Share similar meanings.

Examples:

```text
car
bus

doctor
physician

student
learner
```

---

## Related Words

Connected conceptually but not necessarily similar.

Examples:

```text
coffee
cup

doctor
hospital

teacher
classroom
```

---

## Illustration

```text
Similarity
     ↓
Same Meaning Area

Relatedness
     ↓
Connected Concepts
```

---

# 5. Semantic Fields

A semantic field is a collection of words belonging to the same conceptual area.

---

## Example: Hospital

```text
doctor

nurse

patient

surgery

hospital
```

---

## Example: Restaurant

```text
menu

food

chef

waiter

plate
```

---

## Example: House

```text
roof

door

kitchen

bedroom

window
```

---

Words within the same field frequently occur together.

---

# 6. Antonymy

Antonyms are words with opposite meanings.

Examples:

```text
hot       ↔ cold

up        ↔ down

fast      ↔ slow

light     ↔ dark
```

---

## Illustration

```text
Positive Direction
          ↑
        Hot
          │
          │
        Cold
          ↓
Negative Direction
```

---

# 7. Connotation and Sentiment

Words often carry emotional associations.

---

## Positive Connotations

Examples:

```text
love

happy

wonderful

excellent
```

---

## Negative Connotations

Examples:

```text
hate

toxic

awful

nightmare
```

---

Some words appear similar but differ emotionally.

Examples:

Positive:

```text
replica
```

Negative:

```text
forgery
```

---

Both refer to copies, but carry different connotations.

---

# 8. From Meaning to Mathematics

Traditional NLP approaches represent words as symbols.

Example:

```text
dog

cat

car
```

represented merely as vocabulary entries.

---

Modern NLP asks:

```text
Can meaning itself be represented mathematically?
```

The answer is:

```text
Yes.
```

through vector representations.

---

# 9. Distributional Semantics

A key idea in NLP is:

```text
Words that occur in similar contexts
tend to have similar meanings.
```

---

Example:

```text
The dog barked.

The cat meowed.
```

---

Both:

```text
dog

cat
```

appear in similar linguistic environments.

Therefore they likely share semantic properties.

---

## Illustration

```text
Similar Contexts
         ↓
Similar Meanings
```

---

# 10. Vector Semantics

Vector semantics represents words as points in a multidimensional space.

Instead of:

```text
dog
```

being simply a word, it becomes:

```text
[0.23, 0.81, -0.15, ...]
```

---

Each dimension captures some aspect of meaning.

---

## Illustration

```text
          cat
          ●

 dog ●

                    car ●
```

Words with related meanings become spatially closer.

---

# 11. What is an Embedding?

An embedding is a vector representation of a word.

The term "embedding" comes from the idea that words are embedded into a numerical space.

---

## Example

Rather than:

```text
car
```

we store:

```text
[0.81, 0.42, -0.17, ...]
```

---

This allows computers to compare meanings mathematically.

---

# 12. Why Are Embeddings Useful?

Consider sentiment analysis.

Training data:

```text
terrible
```

appears frequently.

---

Test data:

```text
awful
```

appears instead.

---

Bag of Words:

```text
Different Words
```

No relationship detected.

---

Embeddings:

```text
Similar Vectors
```

Model successfully generalizes.

---

# 13. Two Major Types of Embeddings

---

## Sparse Embeddings

Examples:

```text
Bag of Words

TF-IDF
```

---

Characteristics:

✅ Interpretable

✅ Easy to build

❌ High dimensional

❌ Many zeros

---

## Dense Embeddings

Examples:

```text
Word2Vec

GloVe

FastText
```

---

Characteristics:

✅ Compact

✅ Capture meaning

✅ Better generalization

---

# 14. Document Vectors

Documents can also be represented as vectors.

Suppose we have a vocabulary:

```text
dog
cat
car
```

---

Document:

```text
dog dog cat
```

becomes:

```text
[2,1,0]
```

---

Document:

```text
cat car
```

becomes:

```text
[0,1,1]
```

---

## Illustration

```text
Document
      ↓
Word Counts
      ↓
Vector
```

---

# 15. Measuring Similarity

Once words are converted into vectors, we need a way to compare them.

The most common metric is:

```text
Cosine Similarity
```

---

# 16. Cosine Similarity

Cosine similarity measures how closely two vectors point in the same direction.

---

## Interpretation

```text
1
```

Perfectly similar.

---

```text
0
```

No similarity.

---

```text
-1
```

Opposite directions.

---

## Illustration

```text
Small Angle
      ↓
High Similarity

Large Angle
      ↓
Low Similarity
```

---

# 17. Example of Cosine Similarity

Suppose:

```text
computer
```

and

```text
data
```

appear in similar contexts.

Their vectors point in similar directions.

Result:

```text
High Cosine Similarity
```

---

Meanwhile:

```text
computer
```

and

```text
banana
```

have very different contexts.

Result:

```text
Low Cosine Similarity
```

---

# 18. Problems with Raw Word Counts

Word frequency is useful but imperfect.

Consider:

```text
the
```

appearing thousands of times.

---

Does it tell us much about meaning?

Not really.

---

Meanwhile:

```text
quantum
```

may occur less frequently but is far more informative.

---

# 19. TF-IDF

TF-IDF stands for:

```text
Term Frequency
×
Inverse Document Frequency
```

---

It aims to reward:

```text
Important Words
```

and penalize:

```text
Overly Common Words
```

---

# 20. Term Frequency (TF)

Measures how often a word appears within a document.

---

Example:

Document:

```text
machine learning is fun

machine learning is useful
```

---

TF for:

```text
machine
```

is:

```text
2
```

---

Higher TF usually indicates greater importance.

---

# 21. Document Frequency (DF)

Measures the number of documents containing a word.

---

Example:

```text
the
```

might appear in:

```text
Every Document
```

---

while:

```text
neuroscience
```

might appear in:

```text
Only a Few Documents
```

---

# 22. Inverse Document Frequency (IDF)

IDF penalizes common words.

---

Words such as:

```text
the

is

and
```

receive very low IDF values.

---

Words such as:

```text
quantum

inflation

neuroscience
```

receive higher IDF values.

---

# 23. Final TF-IDF Weight

Combining both concepts:

```text
TF-IDF

=
TF × IDF
```

---

Result:

```text
Frequently Appears
        +
Rare Across Documents
        ↓
High Importance
```

---

# 24. Sparse vs Dense Vectors

## Sparse Vectors

Example:

```text
[0,0,0,1,0,0,0,0,3,0]
```

---

Characteristics:

- Mostly zeros
- Very large dimensions

---

## Dense Vectors

Example:

```text
[0.42, 0.87, -0.25, 0.11]
```

---

Characteristics:

- Compact
- Information-rich

---

# 25. Introduction to Word2Vec

Word2Vec is one of the most influential embedding methods.

Developed by Google researchers, it learns word meanings automatically from text.

---

## Main Idea

Rather than counting words:

```text
Predict Words
```

---

Words appearing in similar contexts learn similar vectors.

---

# 26. How Word2Vec Works

Suppose we have:

```text
The cat drinks milk.
```

---

Target Word:

```text
cat
```

---

Context Words:

```text
The

drinks

milk
```

---

The model learns relationships between:

```text
Target Word

and

Context Words
```

---

# 27. Skip-Gram Model

The most popular Word2Vec variant is:

```text
Skip-Gram
```

---

Goal:

```text
Given a Word
      ↓
Predict Nearby Words
```

---

Example:

```text
king
```

↓

Predict:

```text
queen

royal

crown
```

---

# 28. Negative Sampling

Training every word against the entire vocabulary is expensive.

Word2Vec solves this using:

```text
Negative Sampling
```

---

Idea:

Train on:

```text
Real Word Pairs
```

and

```text
Random Fake Word Pairs
```

---

The model learns to distinguish meaningful contexts from random ones.

---

# 29. Why Word2Vec Was Revolutionary

Word2Vec demonstrated that:

```text
Meaning
```

could emerge from:

```text
Statistical Patterns
```

alone.

---

It enabled:

✅ Better semantic understanding

✅ Similarity search

✅ Improved classification

✅ Improved language models

✅ Modern NLP pipelines

---

# 30. Beyond Word2Vec

Word2Vec led to more advanced embeddings such as:

---

## GloVe

Uses global co-occurrence statistics.

---

## FastText

Represents subword information.

---

## Contextual Embeddings

Examples:

```text
ELMo

BERT

GPT
```

---

Unlike Word2Vec, contextual embeddings depend on surrounding context.

---

# Complete Vector Semantics Pipeline

```text
Text
   ↓
Tokenization
   ↓
Vocabulary
   ↓
Vector Representation
   ↓
Similarity Computation
   ↓
Embedding Learning
   ↓
NLP Applications
```

---

# Real-World Example

Suppose we train embeddings on millions of documents.

Eventually the model learns:

```text
doctor
```

is close to:

```text
hospital

nurse

patient
```

---

while:

```text
football
```

is close to:

```text
goal

player

stadium
```

---

Without explicit human instruction, the system discovers semantic relationships automatically.

---

# Summary

In this tutorial we explored:

- Lexical Semantics
- Lemmas and Word Senses
- Synonymy
- Similarity and Relatedness
- Semantic Fields
- Antonymy
- Connotation
- Distributional Semantics
- Vector Semantics
- Word Embeddings
- Cosine Similarity
- TF-IDF
- Sparse and Dense Vectors
- Word2Vec
- Skip-Gram
- Negative Sampling

Vector semantics transformed NLP by allowing words to be represented mathematically while preserving aspects of meaning. These vector representations form the foundation of modern NLP systems and make it possible for machines to compare, classify, retrieve, and generate language more effectively.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Explain lexical semantics.

✅ Distinguish lemmas from word senses.

✅ Explain synonymy and antonymy.

✅ Differentiate similarity and relatedness.

✅ Describe semantic fields.

✅ Explain distributional semantics.

✅ Define vector semantics.

✅ Describe embeddings.

✅ Explain cosine similarity.

✅ Calculate TF-IDF conceptually.

✅ Distinguish sparse and dense vectors.

✅ Explain how Word2Vec works.

✅ Describe skip-gram training.

✅ Explain negative sampling.

✅ Understand the role of embeddings in modern NLP.
