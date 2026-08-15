# Tutorial 04: Text Classification and Machine Learning

## Overview

One of the most important applications of Natural Language Processing is enabling computers to automatically assign categories to text. Every day, thousands of emails, news articles, customer reviews, social media posts, and documents are generated. Manually organizing this information is impossible at scale.

Text Classification uses machine learning techniques to automatically determine the category or label of a piece of text. Applications range from spam filtering and sentiment analysis to language identification and topic detection.

In this tutorial, we explore the foundations of text classification, focusing on document representation, the Bag of Words model, Naïve Bayes classification, evaluation metrics, model validation, and performance assessment.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain text classification

✅ Understand supervised machine learning for NLP

✅ Describe the Bag of Words representation

✅ Understand the intuition behind Naïve Bayes

✅ Explain prior and likelihood probabilities

✅ Understand Multinomial Naïve Bayes

✅ Handle unknown words and stopwords

✅ Evaluate text classifiers using precision, recall, and F1-score

✅ Understand confusion matrices

✅ Explain cross-validation

✅ Compare classification models objectively

---

# 1. What is Text Classification?

Text classification is the task of assigning one or more predefined categories to a document.

---

## Examples

### Spam Detection

```text
Email
   ↓
Spam Classifier
   ↓
Spam / Not Spam
```

---

### News Categorization

```text
Article
   ↓
Classifier
   ↓
Sports
Politics
Business
Technology
```

---

### Language Identification

```text
Document
   ↓
Classifier
   ↓
English
French
Spanish
German
```

---

### Sentiment Analysis

```text
Review
   ↓
Classifier
   ↓
Positive / Negative
```

---

## Illustration

```text
Input Document
        ↓
Machine Learning Model
        ↓
Predicted Category
```

---

# 2. Types of Text Classification Tasks

Text classification can appear in many forms.

Common applications include:

- Sentiment Analysis
- Spam Detection
- Language Identification
- Authorship Attribution
- Topic Classification
- News Categorization
- Content Moderation

---

## Example

Document:

```text
The team won the championship after an amazing season.
```

Classification:

```text
Sports
```

---

# 3. Classification as a Machine Learning Problem

A classifier receives:

### Input

A document:

```text
d
```

and

### Possible Classes

```text
C = {c₁, c₂, ..., cₙ}
```

---

### Output

One predicted class:

```text
c ∈ C
```

---

## Illustration

```text
Document d
      ↓
Classifier
      ↓
Predicted Class c
```

---

# 4. Rule-Based Classification

Before machine learning became dominant, many systems relied on manually created rules.

---

## Example

Spam Rule

```text
IF

"you have been selected"

AND

"claim prize"

THEN

Spam
```

---

## Advantages

✅ Easy to understand

✅ Works well in limited domains

---

## Limitations

❌ Difficult to maintain

❌ Expensive to create

❌ Poor scalability

❌ Struggles with changing language

---

# 5. Supervised Machine Learning

Modern text classification relies primarily on supervised learning.

The idea is simple:

Provide the algorithm with many examples that already have labels.

---

## Training Data

```text
(Document₁, Class₁)

(Document₂, Class₂)

(Document₃, Class₃)

...
```

---

The algorithm learns patterns and builds a classifier.

---

## Illustration

```text
Labelled Documents
          ↓
Training
          ↓
Classifier
          ↓
Predictions
```

---

# 6. Common Classification Algorithms

Several machine learning algorithms can be used.

Examples include:

- Naïve Bayes
- Logistic Regression
- Decision Trees
- Random Forest
- k-Nearest Neighbours
- Neural Networks

In this tutorial we focus on:

```text
Naïve Bayes
```

because it is one of the most popular and effective classical NLP algorithms.

---

# 7. The Bag of Words Model

Before text can be classified, it must be represented numerically.

The most common classical representation is:

```text
Bag of Words (BoW)
```

---

## Core Idea

A document is represented by:

```text
Word Counts
```

rather than grammar or word order.

---

## Example

Sentence:

```text
I love machine learning
```

Vocabulary:

```text
I
love
machine
learning
hate
```

Bag of Words Representation:

```text
I          = 1
love       = 1
machine    = 1
learning   = 1
hate       = 0
```

---

## Illustration

```text
Sentence
      ↓
Count Words
      ↓
Feature Vector
```

---

# 8. Advantages and Limitations of Bag of Words

## Advantages

✅ Simple

✅ Easy to implement

✅ Effective baseline

---

## Limitations

### Word Order Is Lost

These sentences become identical:

```text
Dog bites man
```

and

```text
Man bites dog
```

---

### Context Is Ignored

The model sees word frequencies only.

---

# 9. Introduction to Naïve Bayes

Naïve Bayes is a probabilistic classifier based on:

```text
Bayes' Theorem
```

Despite its simplicity, it performs surprisingly well on many NLP tasks.

---

## Why Is It Called "Naïve"?

The algorithm assumes:

```text
All Features Are Independent
```

given a class.

This assumption is rarely true, but often works well in practice.

---

# 10. Intuition Behind Naïve Bayes

Suppose we want to classify a movie review.

Review:

```text
Fantastic acting and great story.
```

Words such as:

```text
fantastic

great

excellent

amazing
```

are frequently associated with:

```text
Positive Reviews
```

---

Naïve Bayes calculates:

```text
P(Class | Document)
```

and chooses the class with the highest probability.

---

## Illustration

```text
Document
      ↓
Calculate Probabilities
      ↓
Positive = 0.92

Negative = 0.08
      ↓
Prediction = Positive
```

---

# 11. Prior Probability

The first component of Naïve Bayes is:

```text
Prior Probability
```

This represents how common a class is before observing the document.

---

## Example

Training Dataset

```text
70 Positive Reviews

30 Negative Reviews
```

Prior Probabilities:

```text
P(Positive) = 70/100

P(Negative) = 30/100
```

---

# 12. Likelihood Probability

Next, Naïve Bayes calculates the probability of words given each class.

Example:

```text
fantastic
```

may occur frequently in positive reviews but rarely in negative reviews.

---

## Example

```text
P(fantastic | Positive)
```

might be high.

---

```text
P(fantastic | Negative)
```

might be low.

---

# 13. Multinomial Naïve Bayes

For text data, the most common version is:

```text
Multinomial Naïve Bayes
```

---

## Core Idea

Count how often words appear within each class.

---

### Positive Reviews

```text
great = 50

excellent = 30

fantastic = 40
```

---

### Negative Reviews

```text
terrible = 60

awful = 55

boring = 45
```

---

These counts help estimate probabilities.

---

# 14. The Problem of Zero Probabilities

Consider:

```text
fantastic
```

appears zero times in negative reviews.

Then:

```text
P(fantastic | Negative) = 0
```

This causes a problem.

---

## Why?

Multiplying by zero makes the entire probability equal zero.

---

## Solution

Use:

```text
Laplace Smoothing
```

---

# 15. Laplace Smoothing

Laplace smoothing simply adds 1 to every word count.

---

## Example

Before:

```text
fantastic = 0
```

After:

```text
fantastic = 1
```

---

## Benefits

✅ Avoids zero probabilities

✅ Improves generalization

✅ Handles unseen words

---

# 16. Unknown Words

Test documents often contain words never seen during training.

Example:

Training Vocabulary:

```text
great

excellent

awesome
```

---

Test Document:

```text
spectacular
```

---

Common strategy:

```text
Ignore Unknown Words
```

during classification.

---

# 17. Stopwords

Stopwords are extremely common words such as:

```text
the
a
and
is
of
```

---

Historically, stopwords were removed.

Example:

```text
The movie was amazing
```

↓

```text
movie amazing
```

---

## Modern Observation

For many tasks:

```text
Removing Stopwords
```

does not significantly improve performance.

Many systems simply keep all words.

---

# 18. Binary Naïve Bayes

In sentiment analysis, occurrence is often more important than frequency.

---

## Example

```text
fantastic fantastic fantastic
```

provides little additional information compared to:

```text
fantastic
```

---

Binary Naïve Bayes records only:

```text
Present = 1

Absent = 0
```

instead of actual frequency counts.

---

# 19. Why Naïve Bayes Works Well

Despite its simplicity, Naïve Bayes offers:

✅ Fast training

✅ Fast prediction

✅ Low memory usage

✅ Strong performance on text

✅ Robustness to irrelevant features

---

## Illustration

```text
Simple
      +
Fast
      +
Accurate
      ↓
Naïve Bayes
```

---

# 20. Evaluating Classification Models

After training a model, we must evaluate performance.

One common tool is the:

```text
Confusion Matrix
```

---

# 21. Confusion Matrix

For binary classification:

| Actual | Predicted Positive | Predicted Negative |
|----------|----------|----------|
| Positive | True Positive (TP) | False Negative (FN) |
| Negative | False Positive (FP) | True Negative (TN) |

---

## Illustration

```text
Actual Positive
        ↓
Predicted Positive
        ↓
True Positive
```

---

# 22. Accuracy

Accuracy measures overall correctness.

---

## Formula

```text
Accuracy

=
Correct Predictions
-------------------
Total Predictions
```

---

## Problem

Accuracy can be misleading.

---

## Example

Suppose:

```text
1,000,000 Tweets
```

Only:

```text
100 Relevant Tweets
```

A classifier that predicts:

```text
Not Relevant
```

for everything achieves:

```text
99.99% Accuracy
```

but is practically useless.

---

# 23. Precision

Precision asks:

```text
Of the items predicted positive,

how many were actually positive?
```

---

## Formula

```text
Precision

= TP / (TP + FP)
```

---

## Example

High precision means:

```text
Few False Positives
```

---

# 24. Recall

Recall asks:

```text
Of all actual positive items,

how many were found?
```

---

## Formula

```text
Recall

= TP / (TP + FN)
```

---

## Example

High recall means:

```text
Few False Negatives
```

---

# 25. F1 Score

Precision and Recall often conflict.

The F1 Score combines both.

---

## Formula

```text
F1

=
2 × Precision × Recall
-----------------------
Precision + Recall
```

---

## Illustration

```text
Precision
       +
Recall
       ↓
   F1 Score
```

---

# 26. Training, Validation, and Testing

A good model should generalize well to unseen data.

---

## Typical Split

```text
Training Set
     ↓
Validation Set
     ↓
Test Set
```

---

### Training Set

Used for learning.

---

### Validation Set

Used for tuning.

---

### Test Set

Used for final evaluation.

---

# 27. Cross-Validation

Sometimes datasets are small.

In this case:

```text
k-Fold Cross Validation
```

is used.

---

## Process

```text
Split Data
      ↓
Train on Different Portions
      ↓
Average Results
```

---

## Advantages

✅ More reliable estimates

✅ Better use of limited data

---

# 28. Multi-Class Classification

Many NLP tasks involve more than two classes.

Example:

```text
Sports

Politics

Business
```

---

Instead of a 2×2 confusion matrix, we use:

```text
Multi-Class Confusion Matrix
```

---

# 29. Macro vs Micro Averaging

For multi-class evaluation, metrics can be combined.

---

## Macro Average

Calculate metrics for each class separately.

Then average them.

---

## Micro Average

Combine all decisions into a single confusion matrix.

Then compute metrics.

---

## Difference

```text
Macro
   ↓
Treats Classes Equally

Micro
   ↓
Treats Individual Predictions Equally
```

---

# 30. Model Comparison and Statistical Significance

Suppose:

```text
Model A = 91%

Model B = 92%
```

Is Model B really better?

Maybe.

Maybe not.

The difference could simply be random.

---

To verify improvements, researchers perform:

```text
Statistical Significance Testing
```

---

## Goal

Determine whether:

```text
Observed Improvement
```

is genuine or due to chance.

---

# Complete Text Classification Pipeline

```text
Raw Documents
       ↓
Preprocessing
       ↓
Tokenization
       ↓
Bag of Words
       ↓
Feature Vector
       ↓
Naïve Bayes Training
       ↓
Prediction
       ↓
Evaluation
```

---

# Real-World Example

Suppose we want to classify movie reviews.

Review:

```text
This movie was absolutely fantastic.
```

---

Feature Extraction:

```text
fantastic = 1

movie = 1

absolutely = 1
```

---

Classification:

```text
Positive = 0.96

Negative = 0.04
```

---

Prediction:

```text
Positive Review
```

---

# Summary

In this tutorial we explored:

- Text Classification
- Supervised Learning
- Rule-Based Classification
- Bag of Words
- Naïve Bayes
- Prior Probability
- Likelihood Probability
- Multinomial Naïve Bayes
- Laplace Smoothing
- Unknown Words
- Stopwords
- Binary Naïve Bayes
- Confusion Matrices
- Accuracy
- Precision
- Recall
- F1 Score
- Cross Validation
- Multi-Class Evaluation
- Statistical Significance Testing

Text classification is one of the foundational tasks in NLP. By converting text into numerical representations and applying machine learning algorithms such as Naïve Bayes, computers can automatically categorize documents, emails, reviews, and many other forms of textual information. Understanding these concepts provides the foundation for more advanced NLP applications such as sentiment analysis, spam detection, topic modelling, and intelligent information systems.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define text classification.

✅ Explain supervised machine learning.

✅ Describe the Bag of Words model.

✅ Explain the Naïve Bayes classifier.

✅ Understand prior and likelihood probabilities.

✅ Explain Laplace smoothing.

✅ Handle unknown words.

✅ Explain stopwords.

✅ Differentiate Multinomial and Binary Naïve Bayes.

✅ Construct a confusion matrix.

✅ Calculate precision.

✅ Calculate recall.

✅ Calculate F1-score.

✅ Explain cross-validation.

✅ Evaluate machine learning classifiers effectively.
