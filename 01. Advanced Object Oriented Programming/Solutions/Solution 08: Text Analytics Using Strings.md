# Solution 08: Text Analytics Using Strings

## Overview

This document provides suggested solutions for **Exercise 08: Text Analytics**.

The purpose of this exercise is to strengthen understanding of:

- Strings
- User Input
- Loops
- Functions
- Dictionaries
- Text Processing
- Problem Solving

Text processing is one of the most important skills in modern computing because it forms the foundation of:

```text
Natural Language Processing (NLP)

Search Engines

Chatbots

Large Language Models

Sentiment Analysis

Document Classification
```

---

# Problem Statement

Create a program that accepts a paragraph from the user and reports:

```text
Total Characters

Total Words

Total Sentences

Longest Word

Shortest Word
```

---

## Extension Activity

Display the frequency of every word.

Example:

```text
Python → 4

Programming → 2

AI → 3
```

---

## Advanced Challenge

Determine:

```text
Most Frequently Used Word
```

without using external libraries.

---

# Understanding the Problem

Suppose a user enters:

```text
Python is powerful. Python is easy to learn.
AI uses Python.
```

We want to automatically determine:

```text
Characters

Words

Sentences

Longest Word

Shortest Word

Word Frequencies
```

This type of analysis appears frequently in:

```text
Search Engines

Text Mining

Machine Learning

ChatGPT-like Systems
```

---

# Part A: Basic Text Statistics

---

# Step 1: Accept User Input

```python
paragraph = input(
    "Enter a paragraph:\n"
)
```

Example:

```text
Python is powerful. Python is easy to learn.
```

---

# Step 2: Count Characters

The built-in:

```python
len()
```

function returns the number of characters.

---

## Example

```python
character_count = len(
    paragraph
)
```

---

## Sample Result

```text
42
```

---

# Step 3: Count Words

Words can be separated using:

```python
split()
```

---

## Example

```python
words = paragraph.split()
```

Result:

```python
[
    "Python",
    "is",
    "powerful.",
    "Python",
    "is",
    "easy",
    "to",
    "learn."
]
```

---

### Count Words

```python
word_count = len(words)
```

Result:

```text
8
```

---

# Step 4: Count Sentences

A simple approach is to count sentence-ending punctuation.

Common punctuation:

```text
.

!

?
```

---

## Example

```python
sentence_count = (

    paragraph.count(".")

    +

    paragraph.count("!")

    +

    paragraph.count("?")
)
```

---

### Sample Result

Input:

```text
Python is powerful.
Python is easy.
AI uses Python.
```

Output:

```text
3 Sentences
```

---

# Step 5: Find Longest Word

Start with the first word.

---

## Algorithm

```text
Assume first word is longest.

Compare every remaining word.

Replace when a longer word is found.
```

---

## Implementation

```python
longest_word = words[0]

for word in words:

    if len(word) > len(longest_word):

        longest_word = word
```

---

# Step 6: Find Shortest Word

Apply the same approach.

---

## Implementation

```python
shortest_word = words[0]

for word in words:

    if len(word) < len(shortest_word):

        shortest_word = word
```

---

# Complete Solution

```python
paragraph = input(
    "Enter a paragraph:\n"
)

character_count = len(
    paragraph
)

words = paragraph.split()

word_count = len(words)

sentence_count = (

    paragraph.count(".")
    +
    paragraph.count("!")
    +
    paragraph.count("?")
)

longest_word = words[0]

shortest_word = words[0]

for word in words:

    if len(word) > len(longest_word):

        longest_word = word

    if len(word) < len(shortest_word):

        shortest_word = word

print("\nTEXT ANALYSIS")
print("-------------------")

print(
    "Characters:",
    character_count
)

print(
    "Words:",
    word_count
)

print(
    "Sentences:",
    sentence_count
)

print(
    "Longest Word:",
    longest_word
)

print(
    "Shortest Word:",
    shortest_word
)
```

---

# Sample Output

Input:

```text
Python is powerful. Python is easy to learn.
```

Output:

```text
TEXT ANALYSIS
-------------------

Characters: 42

Words: 8

Sentences: 2

Longest Word: powerful.

Shortest Word: is
```

---

# Improving the Solution

Notice:

```text
powerful.
```

includes punctuation.

This is not ideal.

We can clean the text first.

---

# Removing Punctuation

```python
clean_text = paragraph.replace(
    ".",
    ""
)

clean_text = clean_text.replace(
    ",",
    ""
)

clean_text = clean_text.replace(
    "!",
    ""
)

clean_text = clean_text.replace(
    "?",
    ""
)
```

Then:

```python
words = clean_text.split()
```

Now:

```text
powerful
```

becomes the longest word.

---

# Part B: Word Frequency Analysis

---

# Understanding Frequency Analysis

Suppose:

```text
Python is powerful.
Python is easy.
Python is popular.
```

Word frequencies:

```text
Python → 3

is → 3

powerful → 1

easy → 1

popular → 1
```

---

# Why Frequency Analysis Matters

Word frequency analysis appears in:

```text
Search Engines

Chatbots

Document Classification

Sentiment Analysis

Large Language Models
```

---

# Dictionary Solution

A dictionary is ideal because it stores:

```text
Word → Count
```

---

## Algorithm

For every word:

### If word exists

Increment count.

---

### Otherwise

Create entry with count 1.

---

## Implementation

```python
frequency = {}

for word in words:

    word = word.lower()

    if word in frequency:

        frequency[word] += 1

    else:

        frequency[word] = 1
```

---

# Display Frequencies

```python
for word in frequency:

    print(
        word,
        "→",
        frequency[word]
    )
```

---

# Example Output

```text
python → 3

is → 3

powerful → 1

easy → 1

popular → 1
```

---

# Complete Frequency Program

```python
paragraph = input(
    "Enter text:\n"
)

paragraph = paragraph.lower()

paragraph = paragraph.replace(
    ".",
    ""
)

paragraph = paragraph.replace(
    ",",
    ""
)

words = paragraph.split()

frequency = {}

for word in words:

    if word in frequency:

        frequency[word] += 1

    else:

        frequency[word] = 1

print("\nWORD FREQUENCIES")
print("--------------------")

for word in frequency:

    print(
        word,
        "→",
        frequency[word]
    )
```

---

# Part C: Most Frequently Used Word

---

# Problem

Determine:

```text
Word With Highest Frequency
```

without external libraries.

---

# Algorithm

1. Start with the first word.
2. Track the highest count.
3. Compare each frequency.
4. Replace if larger.

---

# Implementation

```python
most_frequent_word = ""

highest_count = 0

for word in frequency:

    if frequency[word] > highest_count:

        highest_count = (
            frequency[word]
        )

        most_frequent_word = word
```

---

# Display Result

```python
print(
    "Most Frequent Word:",
    most_frequent_word
)

print(
    "Occurrences:",
    highest_count
)
```

---

# Example Output

Input:

```text
Python is powerful.
Python is easy.
Python is popular.
```

Result:

```text
Most Frequent Word:
python

Occurrences:
3
```

---

# Complete Advanced Solution

```python
paragraph = input(
    "Enter text:\n"
)

paragraph = paragraph.lower()

for symbol in ".!?,":

    paragraph = paragraph.replace(
        symbol,
        ""
    )

words = paragraph.split()

frequency = {}

for word in words:

    if word in frequency:

        frequency[word] += 1

    else:

        frequency[word] = 1

most_frequent_word = ""

highest_count = 0

for word in frequency:

    if frequency[word] > highest_count:

        highest_count = (
            frequency[word]
        )

        most_frequent_word = word

print("\nWORD COUNTS")
print("----------------")

for word in frequency:

    print(
        word,
        "→",
        frequency[word]
    )

print("\nMost Frequent Word:")
print(most_fquent_word)

print(
    "Occurrences:",
    highest_count
)
```

---

# Time Complexity Analysis

Let:

```text
n = number of words
```

---

## Word Counting

Loop:

```python
for word in words
```

Complexity:

```text
O(n)
```

---

## Finding Most Frequent Word

Another loop:

```python
for word in frequency
```

Complexity:

```text
O(n)
```

---

## Total Complexity

```text
O(n)
```

which is highly efficient.

---

# Real-World Extension

Modern NLP systems often calculate:

```text
Word Frequency

Sentence Frequency

Term Frequency (TF)

TF-IDF

Document Similarity
```

The frequency dictionary constructed in this exercise forms the basis of those more advanced algorithms.

---

# Reflection

This exercise combines many concepts from previous tutorials:

### Input & Output

```python
input()

print()
```

---

### Strings

```python
replace()

split()

lower()
```

---

### Lists

```python
words
```

---

### Dictionaries

```python
frequency
```

---

### Loops

```python
for
```

---

### Conditional Statements

```python
if

else
```

---

# Self-Evaluation Checklist

After completing Exercise 08, you should be able to:

✅ Process user-entered text.

✅ Count characters.

✅ Count words.

✅ Count sentences.

✅ Find longest words.

✅ Find shortest words.

✅ Build frequency dictionaries.

✅ Determine most frequent words.

✅ Understand the fundamentals of text analytics.

✅ Recognize how these concepts relate to Natural Language Processing.

---

# Key Takeaways

This exercise introduces the foundation of text analytics.

The techniques learned here appear throughout:

```text
Natural Language Processing

Search Engines

Text Mining

Machine Learning

Artificial Intelligence

Large Language Models
```

Although the program is relatively simple, the ideas behind it are used in many modern AI applications and form the first step toward more advanced NLP systems.
