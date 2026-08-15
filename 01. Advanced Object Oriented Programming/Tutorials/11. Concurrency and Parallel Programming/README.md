# Tutorial 11: Concurrency and Parallel Programming in Python

## Overview

As software systems become more sophisticated, they are often expected to perform multiple activities simultaneously.

Consider the following examples:

- A web browser downloading multiple images while displaying a webpage.
- A music streaming application playing audio while loading new content.
- A cloud application handling thousands of user requests at the same time.
- An AI system processing large datasets in parallel.
- A web crawler downloading information from hundreds of websites.

If tasks were executed strictly one after another, many applications would feel slow and unresponsive.

To solve this problem, modern computing relies on **Concurrency** and **Parallel Processing**.

In this tutorial, we will explore:

- Why concurrency is important.
- Tasks, Threads, and Processes.
- Shared memory and message passing.
- Multi-threading in Python.
- Multi-processing in Python.
- When to use threads versus processes.
- Real-world concurrency applications.

Understanding concurrency is an essential skill for software engineers, AI engineers, data scientists, and cloud developers.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Understand the motivation behind concurrent programming.
- Explain the difference between concurrency and parallelism.
- Understand threads and processes.
- Create threads using Python's `threading` module.
- Use `join()` to synchronize tasks.
- Understand shared memory concepts.
- Create processes using Python's `multiprocessing` module.
- Compare threading and multiprocessing.
- Identify real-world use cases of concurrency.

---

# Why Concurrency Exists

To understand concurrency, let's first examine a common misconception.

Many people assume that computers become faster every year because processors continuously increase their clock speeds.

Historically this was true.

---

# The Evolution of CPU Performance

Between approximately:

```text
1970 - 2005
```

computer performance improved primarily through:

```text
Faster CPU Speeds
```

Increases in processing power followed a trend commonly associated with:

```text
Moore's Law
```

which observed that the number of transistors on integrated circuits tended to increase rapidly over time.

---

# The Challenge

Eventually hardware manufacturers encountered physical limitations:

- Power consumption
- Heat generation
- Hardware complexity
- Manufacturing constraints

As a result:

```text
CPU clock speeds
stopped increasing dramatically.
```

---

# The Modern Solution

Instead of building faster processors:

```text
Manufacturers added more CPU cores.
```

Today, modern computers may contain:

```text
2 cores

4 cores

8 cores

16 cores

32+ cores
```

To fully utilize this hardware, software must execute multiple tasks concurrently.

---

# What Is Concurrency?

Concurrency refers to the ability of a system to handle multiple tasks during the same period of time.

In simple terms:

```text
Multiple tasks
appear to run simultaneously.
```

---

# Real-World Analogy

Imagine a chef preparing a large meal.

Instead of:

```text
Cook rice

Then wash vegetables

Then prepare sauce

Then cook meat
```

the chef may:

```text
Cook rice

While vegetables are being prepared

While sauce is heating

While meat marinates
```

Multiple activities progress together.

This resembles concurrency.

---

# Concurrency vs Parallelism

Although the terms are often used interchangeably, they are not identical.

---

## Concurrency

```text
Multiple tasks
making progress together.
```

Tasks may share resources and alternate execution.

---

## Parallelism

```text
Multiple tasks
executing at exactly
the same time.
```

Parallelism usually requires multiple CPU cores.

---

# Visualization

Concurrency:

```text
Task A

Task B

Task A

Task B

Task A
```

Tasks alternate execution.

---

Parallelism:

```text
Core 1 → Task A

Core 2 → Task B
```

Both execute simultaneously.

---

# Understanding Tasks

A **task** is a unit of work performed by a program.

Examples include:

```text
Loading a webpage

Downloading a file

Training a model

Reading a database

Sending an email
```

In concurrent systems, multiple tasks may execute together.

---

# Two Types of Tasks

Modern operating systems support:

```text
Threads

Processes
```

Both enable concurrent execution.

However, they behave differently.

---

# Understanding Processes

A process is an independent running program.

Examples:

```text
Chrome

Spotify

Visual Studio Code

Python
```

Each process owns:

```text
Memory

Resources

System State
```

Processes are isolated from one another.

---

# Understanding Threads

A thread is a smaller execution unit that exists within a process.

Think of a process as a company.

Think of threads as employees working inside that company.

---

# Visual Representation

```text
Process

│

├── Thread A

├── Thread B

├── Thread C

└── Thread D
```

All threads belong to the same process.

---

# Process vs Thread

| Feature | Process | Thread |
|----------|----------|----------|
| Memory | Separate | Shared |
| Creation Cost | Higher | Lower |
| Communication | More Complex | Easier |
| Resource Usage | Higher | Lower |
| Speed | Slower | Faster |

---

# Why Threads Are Useful

Threads are often called:

```text
Lightweight Processes
```

because:

- They start faster.
- They consume fewer resources.
- Communication between threads is easier.

---

# Understanding Shared Memory

One key characteristic of threads is:

```text
Threads share memory.
```

Suppose:

```python
counter = 100
```

If one thread modifies:

```python
counter += 1
```

other threads can immediately observe the change.

This is known as:

```text
Shared Memory
```

---

# Visualization

```text
Shared Memory

counter = 100

      ↑
      |
---------------------
|         |         |

Thread1 Thread2 Thread3
```

All threads access the same memory region.

---

# Thread-Local Variables

Not everything is shared.

Variables declared inside a thread typically belong only to that thread.

Example:

```python
def worker():

    x = 10
```

The variable:

```python
x
```

exists only inside the thread executing the function.

---

# Shared Memory vs Message Passing

There are two primary communication models.

---

## Shared Memory

```text
Threads

Share Variables

Share Objects

Share Data
```

Information is exchanged directly through memory.

---

## Message Passing

```text
Task A

sends message

Task B
```

Tasks communicate through messages rather than shared variables.

Message passing is common in process-based systems.

---

# Python Threading

Python provides a module named:

```python
threading
```

This module allows developers to create and manage threads.

---

# Creating a Thread

One approach is to create a function and assign it to a thread.

---

## Example

```python
import threading

def worker():

    print(
        "Task Running"
    )

thread = threading.Thread(
    target=worker
)
```

---

# Starting a Thread

Creating a thread is not enough.

We must start it:

```python
thread.start()
```

This begins execution.

---

# The Program Flow

```python
thread = threading.Thread(
    target=worker
)

thread.start()
```

Execution sequence:

```text
Create Thread

Start Thread

Run Function
```

---

# Waiting for a Thread

Sometimes the main program must wait until a thread finishes.

Python provides:

```python
join()
```

---

## Example

```python
thread.start()

thread.join()

print(
    "Finished"
)
```

---

# Why join() Matters

Without:

```python
join()
```

the main program may continue executing while child threads are still running.

With:

```python
join()
```

the main program waits for completion.

---

# Visualizing join()

```text
Main Thread

      |

Start Worker

      |

Wait

      |

Worker Finishes

      |

Continue
```

---

# Running Multiple Threads

Suppose we need to download several webpages.

Sequential approach:

```text
Download Page 1

Download Page 2

Download Page 3

Download Page 4
```

Potentially slow.

---

Threaded approach:

```text
Thread 1 → Page 1

Thread 2 → Page 2

Thread 3 → Page 3

Thread 4 → Page 4
```

Much more efficient for many network-related tasks.

---

# Example: Downloading Web Content

Imagine:

```text
7 different URLs
```

need to be downloaded.

Threads can be created for each download task.

Benefits:

```text
Reduced Waiting Time

Improved Responsiveness

Higher Throughput
```

---

# Threading Use Cases

Threads are particularly useful for:

```text
Web Requests

Downloading Files

Database Queries

Network Operations

User Interfaces
```

These tasks spend significant time waiting for external resources.

---

# Limitations of Threading

Although powerful, threading is not always the best solution.

Python includes a mechanism known as:

```text
Global Interpreter Lock (GIL)
```

which can limit performance for CPU-intensive workloads.

For such tasks, multiprocessing is often preferred.

---

# Introduction to Multiprocessing

Python provides another module:

```python
multiprocessing
```

Instead of creating threads:

```text
Creates Processes
```

Each process runs independently.

---

# Why Use Processes?

Processes have:

```text
Separate Memory

Separate Python Interpreters

True Parallel Execution
```

on multi-core systems.

---

# Creating a Process

Example:

```python
from multiprocessing import Process

def worker():

    print(
        "Process Running"
    )

process = Process(
    target=worker
)

process.start()
```

---

# Joining a Process

Just like threads:

```python
process.join()
```

waits for completion.

---

# Multiprocessing Workflow

```text
Create Process

Start Process

Execute Task

Wait Using Join

Finish
```

---

# Threads vs Processes

Choosing correctly is important.

---

## Use Threads For

```text
Downloading Files

Web Scraping

API Calls

Database Communication

I/O Operations
```

---

## Use Processes For

```text
Scientific Computing

Machine Learning

Image Processing

Data Mining

Mathematical Simulation
```

These tasks require significant CPU power.

---

# Example: AI Workloads

Suppose an AI model processes:

```text
1 Million Images
```

Using processes:

```text
Core 1 → Images 1-250,000

Core 2 → Images 250,001-500,000

Core 3 → Images 500,001-750,000

Core 4 → Images 750,001-1,000,000
```

Workloads execute in parallel.

---

# Measuring Performance

A common practice in concurrency is measuring execution time.

Python provides:

```python
import time
```

---

## Example

```python
start_time = time.time()

perform_task()

end_time = time.time()

print(
    end_time -
    start_time
)
```

This allows developers to compare:

```text
Sequential Execution

vs

Concurrent Execution
```

---

# Benefits of Concurrency

Concurrency improves:

### Performance

Better resource utilization.

---

### Responsiveness

Applications remain interactive.

---

### Scalability

More users and requests can be handled.

---

### Throughput

More work is completed in less time.

---

# Real-World Applications

Concurrency is used extensively in:

---

## Web Servers

Thousands of requests arrive simultaneously.

---

## Cloud Platforms

Many users access services concurrently.

---

## Online Gaming

Large numbers of players interact in real time.

---

## AI Systems

Models process massive datasets.

---

## Financial Systems

Millions of transactions occur simultaneously.

---

# Mini Project: Concurrent Website Downloader

Build an application that:

### Accepts

```text
Multiple URLs
```

### Creates

```text
One Thread Per URL
```

### Downloads

```text
Website Content
```

### Measures

```text
Execution Time
```

Compare:

```text
Single Thread

vs

Multiple Threads
```

and analyze performance differences.

---

# Common Beginner Mistakes

## Starting Threads Without Joining

The program may terminate before threads complete.

---

## Assuming Threads Are Always Faster

Performance depends on the task.

---

## Ignoring Shared Data

Multiple threads modifying the same variable can create problems.

---

## Creating Too Many Threads

Thousands of threads can overload a system.

---

# Summary

In this tutorial, you learned:

✅ Why concurrency is important.

✅ The difference between concurrency and parallelism.

✅ What tasks, threads, and processes are.

✅ How shared memory works.

✅ How to create threads using the `threading` module.

✅ How `join()` synchronizes execution.

✅ How to create processes using the `multiprocessing` module.

✅ When to use threading versus multiprocessing.

✅ Real-world applications of concurrent programming.

Concurrency is one of the most important concepts in modern computing and underpins web services, cloud infrastructure, artificial intelligence systems, operating systems, and enterprise applications.

---

# Knowledge Check

1. What is concurrency?
2. What is the difference between concurrency and parallelism?
3. What is a thread?
4. What is a process?
5. Why are threads called lightweight processes?
6. What is shared memory?
7. What does `join()` do?
8. When should multiprocessing be preferred over threading?
9. Why is concurrency important for modern hardware?
10. What are some real-world applications of concurrency?

---

# Next Tutorial

In **Tutorial 12: Course Review and Capstone Project Guidance**, we will consolidate the concepts learned throughout the course and design a complete object-oriented software project that combines programming fundamentals, data structures, file handling, serialization, and concurrency.
