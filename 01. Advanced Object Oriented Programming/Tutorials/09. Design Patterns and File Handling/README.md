# Tutorial 09: Design Patterns and File Handling in Python

## Overview

As software projects grow in size and complexity, writing code that simply works is no longer enough.

Professional software engineers focus on creating systems that are:

- Reusable
- Flexible
- Maintainable
- Scalable

To achieve these goals, developers use proven design techniques called **Design Patterns**.

At the same time, real-world applications rarely store all information in memory. Data often needs to persist after a program closes.

Examples include:

- User accounts
- Book records
- Employee information
- Banking transactions
- Machine learning datasets

This is where **File Operations** become important.

In this tutorial, we will explore:

- The purpose of software design patterns
- Common design patterns used in real-world systems
- The Adapter Pattern
- The Singleton Pattern
- File handling in Python
- Reading and writing files
- Processing data stored in text files

These concepts help bridge the gap between academic programming exercises and professional software development.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Explain what a design pattern is.
- Understand the purpose of reusable software design solutions.
- Identify situations where design patterns can be applied.
- Understand the Adapter Pattern.
- Understand the Singleton Pattern.
- Open and manage files in Python.
- Read information from files.
- Write information to files.
- Apply file processing techniques to practical problems.

---

# Why Design Patterns Matter

Imagine you have been programming for several years.

Eventually, you begin noticing that many software problems repeat themselves.

For example:

```text
How do we create only one object?
How do we adapt an existing class?
How do objects communicate?
How do we handle different algorithms?
```

Instead of reinventing solutions every time, software engineers reuse proven approaches.

These reusable approaches are called:

```text
Design Patterns
```

---

# What Is a Design Pattern?

A design pattern is a reusable solution to a commonly occurring software design problem.

A design pattern is:

✅ A guideline

✅ A blueprint

✅ A best practice

A design pattern is NOT:

❌ A complete program

❌ A specific implementation

❌ A library

Think of a design pattern as an architectural solution that helps organize software effectively.

---

# Real-World Analogy

Suppose you are building a house.

Every house is different.

However, many houses share common design ideas:

```text
Doors

Windows

Bathrooms

Electrical Systems
```

Architects reuse proven solutions rather than redesigning everything from scratch.

Software engineers work the same way.

---

# Why Use Design Patterns?

Design patterns provide several advantages.

---

## Reusability

Solutions can be reused across projects.

---

## Maintainability

Code becomes easier to understand and update.

---

## Communication

Developers can communicate using a common vocabulary.

For example:

```text
Singleton

Factory

Observer

Adapter
```

Immediately conveys specific design ideas.

---

## Reduced Complexity

Design patterns simplify recurring design problems.

---

# Categories of Design Patterns

Most design patterns fall into three broad categories.

---

## Creational Patterns

Focus on object creation.

Examples:

```text
Singleton

Factory

Builder
```

---

## Structural Patterns

Focus on class and object organization.

Examples:

```text
Adapter

Decorator

Composite
```

---

## Behavioral Patterns

Focus on object communication.

Examples:

```text
Observer

Strategy

Command

State
```

---

# Common Design Patterns

As you develop more complex systems, you will encounter patterns such as:

```text
Adapter
Iterator
Decorator
Observer
Strategy
State
Singleton
Factory
Composite
Command
Template
Flyweight
```

You do not need to memorize all of them immediately.

Instead, focus on understanding why design patterns exist.

---

# The Adapter Pattern

One of the simplest patterns to understand is the **Adapter Pattern**.

---

## Motivation

Suppose you already have an existing class.

However, a new system expects a different interface.

Instead of rewriting the original class, we create an adapter.

---

## Everyday Example

Consider international travel.

Your laptop charger may use:

```text
Australian Plug
```

but the hotel provides:

```text
European Socket
```

An adapter allows the two systems to work together.

---

## Visual Representation

```text
Device
   |
Adapter
   |
Power Socket
```

The adapter bridges two incompatible interfaces.

---

# Adapter Pattern in Software

Imagine a list already provides:

```python
append()
pop()
```

We wish to build a stack.

Rather than creating everything from scratch, we can adapt the list.

```text
List
   ↓

Adapter

   ↓

Stack
```

The underlying functionality remains the same.

The interface changes.

---

# Simple Stack Adapter Example

```python
class Stack:

    def __init__(self):

        self.data = []

    def push(self, item):

        self.data.append(item)

    def pop(self):

        return self.data.pop()
```

Internally:

```text
Stack uses List
```

Externally:

```text
User sees Stack
```

This is a practical example of adaptation.

---

# Understanding the Singleton Pattern

Another important design pattern is:

```text
Singleton
```

---

# What Problem Does Singleton Solve?

Sometimes a system should only create one instance of a class.

Examples:

```text
Database Connection

Application Configuration

Logging Service

Operating System Settings
```

Having multiple copies could cause inconsistency.

---

# Real-World Example

Consider a country's government.

At a specific moment:

```text
One Government
```

exists.

Everyone refers to the same government.

Not multiple independent governments.

This idea resembles the Singleton Pattern.

---

# Characteristics of a Singleton

A Singleton:

✅ Creates only one object

✅ Provides global access to that object

✅ Prevents additional instances

---

# Basic Singleton Example

```python
class Database:

    _instance = None

    def __new__(cls):

        if cls._instance is None:

            cls._instance = super().__new__(cls)

        return cls._instance
```

---

# Testing Singleton Behaviour

```python
db1 = Database()

db2 = Database()

print(db1 is db2)
```

Output:

```text
True
```

Both variables reference the same object.

---

# When to Use Singleton

Good use cases:

```text
Configuration Management

Logging Systems

Database Connections

Cache Management
```

Avoid using Singleton everywhere.

Like any design pattern, it should solve a real problem.

---

# Design Pattern Summary

Pattern | Purpose
---------|---------
Adapter | Convert one interface to another
Singleton | Create exactly one object
Factory | Create objects dynamically
Observer | Respond to changes automatically
Strategy | Select among multiple algorithms

Remember:

```text
Patterns are tools.

Not every problem needs a pattern.
```

---

# Introduction to File Operations

Until now, our programs stored information only during execution.

Example:

```python
name = "Alex"
```

When the program terminates:

```text
Data is lost.
```

To preserve information, we use files.

---

# What Is a File?

A file is a collection of data stored permanently on a storage device.

Examples:

```text
Text Files

CSV Files

PDF Files

Images

Databases
```

---

# Why File Operations Matter

Virtually all real-world applications require persistent storage.

Examples:

```text
Library Systems

Banking Systems

Hospital Systems

E-Commerce Platforms

Machine Learning Pipelines
```

The ability to read and write files is a fundamental software engineering skill.

---

# Opening Files

Python provides the built-in:

```python
open()
```

function.

General syntax:

```python
file = open(
    filename,
    mode
)
```

---

# Understanding File Modes

The second parameter determines how the file is accessed.

---

## Read Mode

```python
r
```

Purpose:

```text
Read Existing File
```

---

## Write Mode

```python
w
```

Purpose:

```text
Write New File

Overwrite Existing File
```

---

## Append Mode

```python
a
```

Purpose:

```text
Add New Content

Keep Existing Content
```

---

## Read and Write

```python
r+
```

Allows both reading and writing.

---

# Visual Comparison

```text
Mode   Action

r      Read Only

w      Write Only

a      Append

r+     Read + Write
```

---

# Opening a File for Reading

```python
file = open(
    "students.txt",
    "r"
)
```

---

# Opening a File for Writing

```python
file = open(
    "report.txt",
    "w"
)
```

---

# Closing Files

After finishing with a file:

```python
file.close()
```

should be used.

This releases system resources.

---

# Why Closing Matters

Failing to close files can lead to:

```text
Memory Waste

Data Corruption

Resource Leaks
```

Good programmers always close files when finished.

---

# Reading Entire Files

Suppose:

```text
students.txt
```

contains:

```text
Alex
John
Emma
```

Read all contents:

```python
file = open(
    "students.txt",
    "r"
)

content = file.read()

print(content)

file.close()
```

---

# Reading One Line at a Time

```python
line = file.readline()
```

Useful for processing large files.

---

# Reading All Lines

```python
lines = file.readlines()
```

Returns:

```python
[
    "Alex\n",
    "John\n",
    "Emma\n"
]
```

---

# Iterating Through Files

Files can be used directly in loops.

```python
for line in file:

    print(line)
```

This is often the preferred approach.

---

# Writing to Files

Suppose we wish to create a report.

Example:

```python
file = open(
    "report.txt",
    "w"
)

file.write(
    "Welcome to Python"
)

file.close()
```

---

# Appending to Files

Suppose a log file already exists.

```python
file = open(
    "log.txt",
    "a"
)

file.write(
    "\nNew Entry"
)

file.close()
```

Existing content remains untouched.

---

# Using Context Managers

Modern Python typically uses:

```python
with
```

Example:

```python
with open(
    "data.txt",
    "r"
) as file:

    content = file.read()
```

Benefits:

✅ Automatically closes file

✅ Cleaner syntax

✅ Safer code

---

# Practical Example: Finding the Longest Line

Suppose a text file contains:

```text
Python

Artificial Intelligence

Data
```

Goal:

```text
Find Longest Line
```

---

# Solution

```python
with open(
    "data.txt",
    "r"
) as file:

    longest = ""

    for line in file:

        if len(line) > len(longest):

            longest = line

print(longest)
```

---

# Practical Example: Gas Price Analysis

Suppose we have a file containing:

```text
USA 8.20

Belgium 3.81

USA 8.08

Belgium 3.84
```

We may wish to:

```text
Calculate Averages

Generate Reports

Store Results
```

This type of processing forms the basis of:

```text
Data Analytics

Machine Learning

Business Intelligence
```

---

# Mini Project: Student Record Manager

Create a system that:

### Reads

```text
Student Data
```

from a file.

### Processes

```text
Average Marks
```

### Writes

```text
Summary Report
```

to an output file.

Concepts used:

```text
Classes

Functions

Lists

Files

Dictionaries
```

---

# Common Beginner Mistakes

## Forgetting to Close Files

Always:

```python
file.close()
```

or use:

```python
with
```

---

## Using Wrong Mode

Example:

```python
w
```

will overwrite existing content.

---

## Reading Non-Existent Files

```python
open(
    "missing.txt",
    "r"
)
```

Produces:

```text
FileNotFoundError
```

---

## Forgetting Newline Characters

Writing repeatedly:

```python
file.write("Alex")
file.write("John")
```

Produces:

```text
AlexJohn
```

Often:

```python
file.write("Alex\n")
```

is required.

---

# Summary

In this tutorial, you learned:

✅ What software design patterns are.

✅ Why reusable design solutions matter.

✅ How the Adapter Pattern works.

✅ How the Singleton Pattern works.

✅ How files provide persistent data storage.

✅ How to open, read, write, and append files.

✅ Why context managers are preferred.

✅ How file processing supports real-world applications.

These concepts are frequently used in enterprise systems, data processing applications, and software engineering projects.

---

# Knowledge Check

1. What is a design pattern?
2. What problem does the Adapter Pattern solve?
3. What problem does the Singleton Pattern solve?
4. Why are design patterns useful?
5. What is the difference between write mode and append mode?
6. What happens when a file is opened in write mode?
7. Why should files be closed?
8. What is the advantage of using a context manager?
9. Which function reads all lines from a file?
10. How can file operations support data analytics applications?

---

# Next Tutorial

In **Tutorial 10: Object Persistence through Serialization and Deserialization**, we will learn how entire Python objects can be stored and reconstructed, enabling applications to save complex data structures and object states.
