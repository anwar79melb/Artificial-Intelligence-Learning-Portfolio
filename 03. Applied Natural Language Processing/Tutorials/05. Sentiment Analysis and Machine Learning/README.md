# Tutorial 05: Sentiment Analysis and Machine Learning

## Overview

Not all text simply conveys information. Much of human language expresses opinions, emotions, attitudes, and personal preferences. Every day, people share their thoughts about products, movies, restaurants, political issues, brands, and public events through reviews, social media posts, blogs, and online discussions.

Sentiment Analysis is one of the most important applications of Natural Language Processing because it allows computers to automatically identify and classify opinions expressed in text.

Businesses use sentiment analysis to understand customer satisfaction, governments use it to monitor public opinion, and researchers use it to study human behaviour and social trends.

In this tutorial, we will explore the foundations of sentiment analysis, common sentiment datasets, sentiment classification using machine learning, and the role of Naïve Bayes in predicting positive and negative opinions.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define sentiment analysis

✅ Explain why sentiment analysis is important

✅ Distinguish positive, negative, and neutral sentiment

✅ Identify common sentiment datasets

✅ Understand sentiment classification workflows

✅ Apply machine learning techniques to sentiment prediction

✅ Understand Multinomial Naïve Bayes for sentiment analysis

✅ Explain Laplace smoothing

✅ Understand Binary Multinomial Naïve Bayes

✅ Evaluate sentiment classification systems

---

# 1. What is Sentiment Analysis?

Sentiment Analysis is the process of identifying and extracting opinions, emotions, and attitudes expressed in text.

It is sometimes called:

```text
Opinion Mining
```

because its primary goal is to discover how people feel about a particular subject.

---

## Simple Definition

```text
Text
   ↓
Sentiment Analysis
   ↓
Sentiment Label
```

Example labels:

```text
Positive

Negative

Neutral
```

---

## Illustration

```text
"I absolutely love this phone!"
             ↓
        Positive

"This product is terrible."
             ↓
        Negative
```

---

# 2. Why is Sentiment Analysis Important?

Modern organizations receive huge volumes of opinions every day.

Examples include:

- Product reviews
- Social media posts
- Customer feedback
- Survey responses
- News comments
- Online discussions

Manually reading all of this information is impossible.

Sentiment Analysis automates the process.

---

## Illustration

```text
Thousands of Reviews
         ↓
 Sentiment Analysis
         ↓
Customer Insights
```

---

# 3. Business Applications of Sentiment Analysis

Organizations use sentiment analysis for:

### Customer Feedback Analysis

Understanding customer satisfaction.

---

### Product Evaluation

Determining public reactions to products.

---

### Brand Monitoring

Tracking public opinion toward companies.

---

### Market Research

Identifying trends and consumer preferences.

---

### Social Media Monitoring

Tracking conversations about brands and events.

---

# 4. Real-World Examples

## Movie Reviews

Question:

```text
Is this review positive or negative?
```

Review:

```text
The movie was brilliant.
```

Prediction:

```text
Positive
```

---

## Product Reviews

Question:

```text
What do customers think about the new smartphone?
```

Thousands of reviews can be analyzed automatically.

---

## Politics

Question:

```text
How do voters feel about a candidate?
```

Social media posts can provide valuable clues.

---

# 5. Positive and Negative Reviews

Consider the following examples.

---

## Positive Example

```text
The movie had amazing characters and excellent storytelling.
```

Sentiment:

```text
Positive
```

---

## Negative Example

```text
The film was disappointing and extremely boring.
```

Sentiment:

```text
Negative
```

---

## Restaurant Example

```text
Awesome food and wonderful service.
```

Sentiment:

```text
Positive
```

---

## Another Example

```text
The pizza was awful and overpriced.
```

Sentiment:

```text
Negative
```

---

# 6. Sentiment Indicators

Certain words often provide strong clues regarding sentiment.

---

## Positive Words

Examples:

```text
amazing

awesome

fantastic

great

excellent

love
```

---

## Negative Words

Examples:

```text
terrible

pathetic

awful

worst

boring

hate
```

---

## Illustration

```text
Positive Words
      ↓
Positive Sentiment

Negative Words
      ↓
Negative Sentiment
```

---

# 7. Beyond Positive and Negative

Human emotions are complex.

Not every expression fits neatly into positive or negative categories.

Researchers often analyze broader affective states.

---

## Emotion Examples

```text
Happy

Sad

Angry

Fearful

Proud

Excited
```

---

## Mood Examples

```text
Cheerful

Gloomy

Depressed

Irritable
```

---

## Interpersonal Attitudes

```text
Friendly

Supportive

Warm

Cold

Hostile
```

---

Sentiment analysis is often viewed as a simplified form of emotion analysis.

---

# 8. Popular Sentiment Analysis Datasets

Machine learning requires labelled training data.

Several benchmark datasets are widely used.

---

# Amazon Product Reviews Dataset

Contains millions of Amazon reviews across many product categories.

Useful for:

- Product review analysis
- Rating prediction
- Recommendation systems

---

## Typical Labels

```text
Positive

Negative
```

or

```text
1–5 Star Ratings
```

---

# Stanford Sentiment Treebank (SST)

Created using movie reviews collected from Rotten Tomatoes.

Provides detailed sentiment labels.

---

## Example Labels

```text
Very Negative

Negative

Neutral

Positive

Very Positive
```

---

# IMDb Movie Reviews Dataset

One of the most popular sentiment analysis datasets.

Contains approximately:

```text
50,000 Movie Reviews
```

---

## Classification Task

```text
Positive

Negative
```

---

# Paper Reviews Dataset

Contains conference paper reviews.

Sentiment Scale:

```text
-2 = Very Negative

-1 = Negative

 0 = Neutral

 1 = Positive

 2 = Very Positive
```

---

# Twitter Airline Sentiment Dataset

Contains tweets discussing major airlines.

Labels include:

```text
Positive

Neutral

Negative
```

---

## Illustration

```text
Twitter Posts
      ↓
Sentiment Dataset
      ↓
Machine Learning
```

---

# 9. Sentiment Analysis as a Classification Problem

Most sentiment analysis systems treat sentiment prediction as a classification task.

---

## Input

```text
Review
Tweet
Comment
Post
```

---

## Output

```text
Positive

Negative

Neutral
```

---

## Workflow

```text
Text
   ↓
Feature Extraction
   ↓
Machine Learning
   ↓
Sentiment Prediction
```

---

# 10. Machine Learning for Sentiment Analysis

The most common workflow is:

---

## Step 1

Collect labelled data.

Example:

```text
Review → Positive

Review → Negative
```

---

## Step 2

Convert text into features.

Examples:

```text
Bag of Words

TF-IDF
```

---

## Step 3

Train a classifier.

Examples:

```text
Naïve Bayes

Logistic Regression

Neural Networks
```

---

## Step 4

Predict sentiment for new documents.

---

# 11. Naïve Bayes for Sentiment Analysis

Naïve Bayes is one of the most popular classical sentiment classifiers.

---

## Why?

Because it is:

✅ Fast

✅ Simple

✅ Effective for text

✅ Easy to interpret

---

## Illustration

```text
Review
      ↓
Word Counts
      ↓
Naïve Bayes
      ↓
Positive / Negative
```

---

# 12. Training a Naïve Bayes Sentiment Model

Suppose we have the following labelled reviews.

---

## Positive Reviews

```text
I love this movie.

Amazing storyline.

Fantastic acting.
```

---

## Negative Reviews

```text
Terrible film.

Worst movie ever.

Very disappointing.
```

---

The classifier learns which words tend to occur in each sentiment class.

---

# 13. Prior Probability

Before reading a review, the classifier calculates:

```text
P(Positive)

P(Negative)
```

based on the training dataset.

---

## Example

Training Data:

```text
60 Positive Reviews

40 Negative Reviews
```

Then:

```text
P(Positive) = 0.6

P(Negative) = 0.4
```

---

# 14. Likelihood Probability

The classifier estimates:

```text
P(word | Positive)

P(word | Negative)
```

---

## Example

Word:

```text
fantastic
```

Likely appears more frequently in positive reviews.

Therefore:

```text
P(fantastic | Positive)
```

will be larger than:

```text
P(fantastic | Negative)
```

---

# 15. The Zero Probability Problem

Suppose:

```text
fantastic
```

never appears in negative reviews.

Then:

```text
P(fantastic | Negative) = 0
```

---

This makes the overall document probability equal zero.

---

## Problem

```text
Anything × 0 = 0
```

---

# 16. Laplace Smoothing

To solve this issue, we use:

```text
Laplace Smoothing
```

---

## Idea

Add one occurrence to every word count.

Example:

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

✅ Prevents zero probabilities

✅ Improves robustness

✅ Handles unseen events

---

# 17. Unknown Words

New documents often contain words not seen during training.

Example:

Training Vocabulary:

```text
great

awesome

fantastic
```

---

Test Review:

```text
spectacular
```

---

Common strategy:

```text
Ignore Unknown Words
```

during prediction.

---

# 18. Stopwords in Sentiment Analysis

Stopwords include:

```text
the

a

is

and

of
```

---

Historically, many NLP systems removed stopwords.

However, sentiment analysis often benefits from keeping them.

Example:

```text
not good
```

Removing:

```text
not
```

changes the meaning entirely.

---

# 19. Binary Multinomial Naïve Bayes

In sentiment analysis, occurrence often matters more than frequency.

---

## Example

Review A:

```text
fantastic
```

Review B:

```text
fantastic fantastic fantastic fantastic
```

---

The repeated appearances provide limited additional information.

---

Binary Naïve Bayes simply records:

```text
Word Appears = 1

Word Missing = 0
```

---

# 20. Why Binary Naïve Bayes Often Works Well

Many sentiment words are highly informative.

Examples:

```text
love

hate

amazing

terrible

excellent

awful
```

Whether the word appears is often more important than how many times it appears.

---

# 21. Complete Sentiment Analysis Pipeline

```text
Raw Text
      ↓
Preprocessing
      ↓
Tokenization
      ↓
Feature Extraction
      ↓
Naïve Bayes Training
      ↓
Sentiment Prediction
```

---

# Example Sentiment Classification

Review:

```text
The food was amazing and the staff were incredibly friendly.
```

---

Extracted Features:

```text
food

amazing

staff

friendly
```

---

Prediction:

```text
Positive Sentiment
```

---

Another Review:

```text
The service was terrible and the food was disappointing.
```

---

Prediction:

```text
Negative Sentiment
```

---

# Challenges in Sentiment Analysis

Although sentiment analysis appears straightforward, real-world language is difficult.

---

## Sarcasm

```text
Great! Another software bug.
```

Appears positive but is actually negative.

---

## Mixed Opinions

```text
The camera is fantastic but the battery life is terrible.
```

Contains both positive and negative sentiment.

---

## Context Dependency

```text
The movie was sick.
```

Depending on context:

```text
Positive

or

Negative
```

---

# Real-World Applications

Sentiment analysis is widely used in:

---

## E-Commerce

Product reviews and recommendations.

---

## Social Media Analytics

Public opinion monitoring.

---

## Finance

Market sentiment prediction.

---

## Politics

Election sentiment tracking.

---

## Customer Service

Complaint and satisfaction analysis.

---

# Summary

In this tutorial we explored:

- Sentiment Analysis
- Opinion Mining
- Positive and Negative Sentiment
- Emotional and Affective States
- Popular Sentiment Datasets
- Amazon Reviews Dataset
- Stanford Sentiment Treebank
- IMDb Reviews Dataset
- Twitter Airline Sentiment Dataset
- Machine Learning for Sentiment Analysis
- Naïve Bayes Classification
- Prior and Likelihood Probabilities
- Laplace Smoothing
- Stopwords
- Unknown Words
- Binary Multinomial Naïve Bayes

Sentiment Analysis is one of the most commercially valuable NLP applications. By automatically identifying opinions, emotions, and attitudes in text, organizations can better understand customers, monitor public sentiment, and make informed business decisions at scale.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define sentiment analysis.

✅ Explain why sentiment analysis is useful.

✅ Differentiate positive and negative sentiment.

✅ Identify major sentiment datasets.

✅ Explain sentiment classification workflows.

✅ Describe Naïve Bayes for sentiment prediction.

✅ Understand prior and likelihood probabilities.

✅ Explain Laplace smoothing.

✅ Handle unknown words and stopwords.

✅ Explain Binary Multinomial Naïve Bayes.

✅ Identify challenges in real-world sentiment analysis.

✅ Apply sentiment analysis concepts to practical NLP problems.
