# Tutorial 03: Basic Text Processing Techniques

## Overview

Before machine learning algorithms can analyze text, the text must first be cleaned, standardized, and transformed into a format that computers can process efficiently. This process is known as **text preprocessing**, and it forms the foundation of almost every Natural Language Processing (NLP) application.

Raw text collected from websites, social media, emails, or documents often contains noise such as punctuation, inconsistent capitalization, special characters, abbreviations, and redundant information. If these issues are not addressed, machine learning models may produce inaccurate results.

In this tutorial, we explore the fundamental text preprocessing techniques used in NLP, including:

- Regular Expressions
- Corpora and Vocabulary
- Tokenization
- Text Normalization
- Case Folding
- Stemming
- Lemmatization
- Sentence Segmentation

These techniques help transform messy textual data into structured information suitable for machine learning and deep learning applications.

---

## Learning Outcomes

After completing this tutorial, you should be able to:

✅ Understand the role of text preprocessing in NLP

✅ Use Regular Expressions for pattern matching

✅ Explain words, tokens, and types

✅ Perform tokenization

✅ Apply text normalization techniques

✅ Understand case folding

✅ Explain stemming and lemmatization

✅ Understand morphological analysis

✅ Describe sentence segmentation

✅ Select appropriate preprocessing methods for NLP projects

---

# Why Text Processing Matters

Computers do not naturally understand language.

Consider the following sentence:

```text
I absolutely LOVE this movie!!!
```

A human immediately understands:

- The word "LOVE" expresses positive emotion.
- Multiple exclamation marks emphasize enthusiasm.

A computer initially sees:

```text
Characters
```

rather than meaning.

Therefore, raw text must be processed before it can be analyzed.

---

## The NLP Pipeline

```text
Raw Text
     ↓
Text Processing
     ↓
Feature Extraction
     ↓
Machine Learning
     ↓
Prediction
```

---

# 1. Regular Expressions

One of the most useful tools in NLP is the **Regular Expression (Regex)**.

A Regular Expression is a pattern used to search, match, and manipulate text.

---

## Why Use Regular Expressions?

Regex allows us to:

- Find specific words
- Extract patterns
- Remove unwanted text
- Validate formats
- Preprocess documents

---

## Example

Searching for:

```text
woodchuck
```

will match:

```text
I saw a woodchuck yesterday.
```

---

## Illustration

```text
Text
   ↓
Regex Search
   ↓
Matched Pattern
```

---

# 2. Simple Regex Matching

The simplest regex consists of ordinary characters.

Example:

```regex
cat
```

Matches:

```text
The cat is sleeping.
```

---

```regex
hello
```

Matches:

```text
hello world
```

---

## Python Example

```python
import re

text = "The cat is sleeping"

match = re.search("cat", text)

print(match.group())
```

Output:

```text
cat
```

---

# 3. Case Sensitivity

Regular expressions are case-sensitive by default.

Example:

```regex
woodchuck
```

Matches:

```text
woodchuck
```

But not:

```text
Woodchuck
```

---

## Solution

Use character groups.

```regex
[wW]oodchuck
```

Matches:

```text
Woodchuck

woodchuck
```

---

# 4. Character Classes

Square brackets allow matching multiple characters.

---

## Example

```regex
[abc]
```

Matches:

```text
a

b

c
```

---

## Example

```regex
[0-9]
```

Matches:

Any digit:

```text
0 1 2 3 4 5 6 7 8 9
```

---

## Example

```regex
[A-Z]
```

Matches:

Any uppercase letter.

---

## Example

```regex
[a-z]
```

Matches:

Any lowercase letter.

---

# 5. Negation in Regex

A caret inside square brackets indicates negation.

---

## Example

```regex
[^A-Z]
```

Matches:

Anything except uppercase letters.

---

## Example

```regex
[^0-9]
```

Matches:

Anything except digits.

---

## Illustration

```text
[A-Z]
      ↓
Uppercase Letters

[^A-Z]
      ↓
Everything Else
```

---

# 6. Special Regex Operators

Several operators provide powerful matching capabilities.

---

## Question Mark (?)

Means:

```text
Zero Or One Occurrence
```

Example:

```regex
colou?r
```

Matches:

```text
color

colour
```

---

## Kleene Star (*)

Means:

```text
Zero Or More Occurrences
```

Example:

```regex
oo*h!
```

Matches:

```text
oh!

ooh!

oooh!
```

---

## Plus (+)

Means:

```text
One Or More Occurrences
```

Example:

```regex
[0-9]+
```

Matches:

```text
12

234

98765
```

---

# 7. Regex Anchors

Anchors define positions inside text.

---

## Start of Line

```regex
^
```

Example:

```regex
^The
```

Matches:

```text
The cat sat down.
```

Only when "The" occurs at the beginning.

---

## End of Line

```regex
$
```

Example:

```regex
world$
```

Matches:

```text
hello world
```

---

## Word Boundary

```regex
\b
```

Allows matching whole words only.

Example:

```regex
\bcat\b
```

Matches:

```text
cat
```

But not:

```text
catalog
```

---

# 8. Precision and Recall in Pattern Matching

When building regex patterns, two common errors occur.

---

## False Positives

We match text that should not be matched.

Example:

Searching:

```regex
the
```

may incorrectly match:

```text
other

there
```

---

## False Negatives

We fail to match text that should be matched.

Example:

```text
The
```

may be missed due to capitalization.

---

## Illustration

```text
Too Broad
      ↓
False Positives

Too Strict
      ↓
False Negatives
```

---

# 9. Words, Tokens, and Types

When analyzing text, we distinguish between:

---

## Token

A token is a specific occurrence of a word.

Example sentence:

```text
they lay back on the San Francisco grass and looked at the stars
```

Contains:

```text
15 Tokens
```

---

## Type

A type is a unique vocabulary item.

Example:

```text
cat cat dog
```

Tokens:

```text
3
```

Types:

```text
2
```

---

## Illustration

```text
cat cat dog
│   │   │
3 Tokens

cat dog
│    │
2 Types
```

---

# 10. What is a Corpus?

A corpus is not simply a collection of words.

Every corpus contains context.

A text is produced by:

- Specific authors
- Specific locations
- Specific time periods
- Specific purposes

---

## Example Factors

```text
Language

Genre

Region

Culture

Author Demographics
```

These factors influence language usage.

---

# 11. Text Normalization

Text normalization transforms text into a consistent format.

---

## Main Goals

### 1. Tokenization

Split text into units.

---

### 2. Word Normalization

Create consistent representations.

---

### 3. Sentence Segmentation

Detect sentence boundaries.

---

## Illustration

```text
Original Text
      ↓
Normalization
      ↓
Standardized Text
```

---

# 12. Tokenization

Tokenization splits text into smaller units called tokens.

---

## Example

Sentence:

```text
NLP is amazing.
```

Tokens:

```text
["NLP", "is", "amazing", "."]
```

---

## Illustration

```text
Sentence
      ↓
Tokenizer
      ↓
Tokens
```

---

# 13. Space-Based Tokenization

The simplest tokenizer uses spaces.

Example:

```text
Machine learning is fun
```

↓

```text
Machine

learning

is

fun
```

---

This works reasonably well for languages that separate words using spaces.

Examples:

- English
- French
- German
- Spanish

---

# 14. Challenges in Tokenization

Real-world text makes tokenization harder.

---

## Abbreviations

```text
Ph.D.

Dr.

M.P.H.
```

---

## URLs

```text
https://example.com
```

---

## Email Addresses

```text
someone@gmail.com
```

---

## Prices

```text
$45.50
```

---

## Dates

```text
01/02/2025
```

---

## Hashtags

```text
#NLP
```

---

Simple splitting may incorrectly break these elements.

---

# 15. Word Normalization

Words often appear in multiple formats.

Examples:

```text
USA

U.S.A.
```

---

```text
Fed

fed
```

---

A normalization strategy ensures equivalent forms are treated consistently.

---

# 16. Case Folding

Case folding converts text into lowercase.

---

## Example

Before:

```text
DOG

Dog

dog
```

After:

```text
dog

dog

dog
```

---

## Advantages

Reduces vocabulary size.

Improves consistency.

---

## Disadvantages

May remove useful information.

Example:

```text
US
```

(country)

vs

```text
us
```

(pronoun)

---

# 17. Morphology

Words can often be decomposed into meaningful units.

These units are called:

```text
Morphemes
```

---

## Example

```text
cats
```

↓

```text
cat + s
```

---

## Components

### Stem

Core meaning.

```text
cat
```

---

### Affix

Grammatical addition.

```text
s
```

---

# 18. Lemmatization

Lemmatization converts words into their dictionary form.

This dictionary form is called:

```text
Lemma
```

---

## Example

```text
am

is

are

were
```

↓

```text
be
```

---

## Example

```text
running
```

↓

```text
run
```

---

## Advantages

Preserves correct linguistic meaning.

---

# 19. Stemming

Stemming removes prefixes and suffixes using heuristic rules.

---

## Example

```text
running
```

↓

```text
run
```

---

## Example

```text
studies
```

↓

```text
studi
```

---

Notice:

```text
studi
```

is not a real dictionary word.

---

## Illustration

```text
Running
     ↓
Stemmer
     ↓
Run

Studies
     ↓
Stemmer
     ↓
Studi
```

---

# 20. Porter Stemmer

One of the most popular stemming algorithms.

Uses multiple sets of rewriting rules.

Example transformations:

```text
connected
```

↓

```text
connect
```

---

```text
playing
```

↓

```text
play
```

---

# 21. Complex Morphology

Languages vary greatly in complexity.

English morphology is relatively simple.

Other languages can have very rich morphology.

---

## Example

Turkish

A single word may contain:

- Root
- Tense
- Number
- Person
- Case

all combined together.

This makes NLP more challenging.

---

# 22. Sentence Segmentation

Sentence segmentation identifies sentence boundaries.

---

## Example

Text:

```text
I love NLP. It is fascinating.
```

Segments:

```text
Sentence 1:
I love NLP.

Sentence 2:
It is fascinating.
```

---

# 23. Why Sentence Segmentation is Difficult

Periods do not always indicate sentence endings.

Examples:

```text
Dr. Smith arrived.
```

---

```text
The price increased by 3.5%.
```

---

```text
Apple Inc. released a product.
```

Systems must determine whether a period is:

```text
Abbreviation

Number

Sentence Boundary
```

---

# Complete Text Preprocessing Pipeline

```text
Raw Text
      ↓
Regular Expressions
      ↓
Tokenization
      ↓
Normalization
      ↓
Case Folding
      ↓
Stemming / Lemmatization
      ↓
Sentence Segmentation
      ↓
Processed Text
```

---

# Practical Example

Raw Text:

```text
Dr. Smith loves studying NLP technologies.
```

---

Tokenization:

```text
["Dr.", "Smith", "loves", "studying", "NLP", "technologies"]
```

---

Case Folding:

```text
["dr.", "smith", "loves", "studying", "nlp", "technologies"]
```

---

Lemmatization:

```text
["dr.", "smith", "love", "study", "nlp", "technology"]
```

---

The text is now far easier for machine learning models to process.

---

# Summary

In this tutorial we explored:

- Regular Expressions
- Regex operators
- Character classes
- Anchors
- Precision and recall concepts
- Words, types, and tokens
- Corpora
- Text normalization
- Tokenization
- Case folding
- Morphology
- Lemmatization
- Stemming
- Porter Stemmer
- Sentence segmentation

Text preprocessing is one of the most important stages in NLP. High-quality preprocessing improves consistency, reduces noise, and creates cleaner representations that enable machine learning and deep learning models to better understand language.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Explain the purpose of text preprocessing.

✅ Build basic Regular Expressions.

✅ Use character classes and anchors.

✅ Distinguish between tokens and types.

✅ Explain corpora and vocabulary.

✅ Perform tokenization.

✅ Explain text normalization.

✅ Apply case folding appropriately.

✅ Explain morphology and morphemes.

✅ Distinguish stemming from lemmatization.

✅ Describe the Porter Stemmer.

✅ Explain sentence segmentation challenges.

✅ Design a complete text preprocessing pipeline.
