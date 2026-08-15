# Tutorial 08: Fundamental Data Structures – Stacks and Queues

## Overview

As software systems become larger and more complex, choosing the right way to store and organize data becomes increasingly important.

Imagine building:

- A web browser
- A ticket booking platform
- A customer service system
- A banking application
- A messaging platform

In all these systems, information must be stored and retrieved efficiently.

Simply storing data in variables or lists is not always enough.

To solve specific problems efficiently, computer scientists have developed specialized data structures.

In this tutorial, we focus on two of the most important linear data structures:

- Stack
- Queue

Although simple in concept, these structures are widely used in operating systems, compilers, web browsers, database systems, artificial intelligence applications, and enterprise software.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Understand why data structures are important.
- Explain the concepts of Stack and Queue.
- Describe LIFO and FIFO processing.
- Implement a Stack using Python.
- Implement a Queue using Python.
- Understand practical applications of both structures.
- Analyze common performance considerations.
- Apply Stack and Queue concepts to real-world problems.

---

# Why Data Structures Matter

Suppose we are developing a Library Management System.

We may need to:

```text
Store books.

Process borrowing requests.

Track user activity.

Maintain transaction histories.
```

As the amount of data grows, efficiency becomes critical.

Two important factors influence software performance:

### Time Efficiency

How quickly an operation can be completed.

Examples:

```text
Finding a record

Removing an item

Adding new data
```

---

### Space Efficiency

How much memory a solution consumes.

Examples:

```text
Large datasets

Customer records

Machine learning data
```

---

# Data Structures and Algorithms

A common misconception is that only algorithms determine performance.

In reality:

```text
Algorithms determine
HOW we process data.

Data Structures determine
HOW we store data.
```

Both work together.

Even an excellent algorithm can perform poorly if the underlying data structure is inappropriate.

---

# Introduction to Stacks

A Stack is one of the simplest and most useful data structures.

It follows a rule known as:

```text
Last In, First Out (LIFO)
```

or

```text
First In, Last Out (FILO)
```

---

# Real-World Analogy: Stack of Books

Imagine a stack of books on a desk.

```text
    Book D
    Book C
    Book B
    Book A
```

The last book placed on the stack:

```text
Book D
```

is the first book removed.

This is exactly how a stack works.

---

# Visualizing a Stack

```text
          TOP

        +------+
        |  D   |
        +------+
        |  C   |
        +------+
        |  B   |
        +------+
        |  A   |
        +------+
```

The top element is the only element that can be directly accessed.

---

# Core Stack Operations

Every stack supports several fundamental operations.

---

## Push

Adds an item to the top of the stack.

```python
stack.push(item)
```

Before:

```text
A
B
```

After:

```text
A
B
C
```

---

## Pop

Removes and returns the top element.

```python
stack.pop()
```

Before:

```text
A
B
C
```

After:

```text
A
B
```

Returned:

```text
C
```

---

## Peek (Top)

Returns the top element without removing it.

```python
stack.top()
```

Result:

```text
C
```

---

## Is Empty

Determines whether the stack contains any elements.

```python
stack.is_empty()
```

Result:

```python
True
```

or

```python
False
```

---

## Length

Returns the number of elements.

```python
len(stack)
```

---

# Implementing a Stack in Python

Python's list data structure already provides the required functionality.

Specifically:

```python
append()
```

adds elements to the end.

And:

```python
pop()
```

removes the last element.

This naturally supports stack behavior.

---

# Simple Stack Class

```python
class Stack:

    def __init__(self):

        self._data = []

    def push(self, item):

        self._data.append(item)

    def pop(self):

        return self._data.pop()

    def top(self):

        return self._data[-1]

    def is_empty(self):

        return len(self._data) == 0

    def __len__(self):

        return len(self._data)
```

---

# Example Usage

```python
stack = Stack()

stack.push("A")

stack.push("B")

stack.push("C")

print(stack.pop())
```

Output:

```text
C
```

Remember:

```text
Last In

First Out
```

---

# Applications of Stacks

Many software systems use stacks behind the scenes.

---

# Application 1: Browser History

When visiting websites:

```text
Google

YouTube

GitHub

Stack Overflow
```

The browser keeps track of visited pages.

Pressing:

```text
Back
```

returns to the most recently visited page.

Behavior:

```text
GitHub

YouTube

Google
```

This is a classic stack.

---

## Visual Example

```text
TOP

StackOverflow
GitHub
YouTube
Google
```

Back button removes the top entry.

---

# Application 2: Undo Operations

Text editors such as:

```text
Microsoft Word

Google Docs

VS Code
```

maintain an undo history.

Each action is pushed onto a stack.

Example:

```text
Typed A

Typed B

Typed C
```

Undo removes:

```text
Typed C
```

first.

---

# Application 3: Function Calls

Python internally uses a stack when functions are called.

Example:

```python
main()

    calculate()

        process()
```

Python keeps track of execution using a call stack.

---

# Application 4: Expression Validation

Consider:

```text
()
{}
[]
```

Every opening symbol must match a closing symbol.

Correct:

```text
()(()){[()]}
```

Incorrect:

```text
({[])
```

Stacks provide an elegant solution to this problem.

---

# Balanced Parentheses Problem

Algorithm:

### Step 1

Whenever an opening symbol appears:

```text
(
[
{
```

Push it onto the stack.

---

### Step 2

Whenever a closing symbol appears:

```text
)
]
}
```

Pop the corresponding opening symbol.

---

### Step 3

If the stack becomes invalid at any stage, the expression is incorrect.

---

### Example

Expression:

```text
([()])
```

Stack evolution:

```text
(
([
([(
([
(
Empty
```

Valid.

---

# Complexity of Stack Operations

A major advantage of stacks is efficiency.

| Operation | Complexity |
|-----------|------------|
| Push | O(1) |
| Pop | O(1) |
| Top | O(1) |

These operations execute extremely quickly.

---

# Introduction to Queues

A Queue is another important linear data structure.

Unlike stacks, queues follow:

```text
First In, First Out (FIFO)
```

The first item entering the queue leaves first.

---

# Real-World Analogy: Supermarket Queue

Imagine customers waiting at a checkout.

```text
Alex

John

Emma

Sarah
```

Alex arrived first.

Alex is served first.

This is exactly how a queue operates.

---

# Visualizing a Queue

```text
FRONT

Alex -> John -> Emma -> Sarah

                         REAR
```

Insertion occurs at the rear.

Removal occurs at the front.

---

# Core Queue Operations

---

## Enqueue

Adds an item to the rear.

```python
queue.enqueue(item)
```

---

## Dequeue

Removes an item from the front.

```python
queue.dequeue()
```

---

## First

Returns the front element without removing it.

```python
queue.first()
```

---

## Is Empty

Checks whether the queue contains data.

```python
queue.is_empty()
```

---

## Length

Returns the number of elements.

```python
len(queue)
```

---

# Queue Example

Initial Queue:

```text
Front

Alex
John

Rear
```

Enqueue:

```text
Emma
```

Result:

```text
Alex
John
Emma
```

---

Dequeue:

```text
Alex
```

Result:

```text
John
Emma
```

---

# Implementing a Simple Queue

A beginner may try:

```python
queue = []

queue.append(item)

queue.pop(0)
```

While this works, it is not efficient.

---

# Why pop(0) Is Slow

Consider:

```text
A B C D E
```

Removing:

```text
A
```

requires shifting:

```text
B C D E
```

one position to the left.

This becomes increasingly expensive for large datasets.

---

# Better Queue Implementation

Python provides:

```python
collections.deque
```

which is optimized for queue operations.

---

# Example

```python
from collections import deque

queue = deque()

queue.append("Alex")

queue.append("John")

queue.append("Emma")

print(
    queue.popleft()
)
```

Output:

```text
Alex
```

---

# Circular Queue Concept

For high-performance systems, queues often use circular storage.

Instead of continually shifting data:

```text
A B C D
```

removed positions are reused.

---

## Traditional Queue Problem

Repeated:

```text
Enqueue

Dequeue

Enqueue

Dequeue
```

can create wasted space.

---

## Circular Queue Solution

Treat storage as a circle.

```text
0 → 1 → 2 → 3
↑           ↓
←-----------←
```

When the end is reached:

```text
Next position = Beginning
```

This greatly improves memory utilization.

---

# Applications of Queues

Queues appear throughout computer science.

---

# Application 1: Customer Service Systems

Support tickets arrive in order.

```text
Ticket 1

Ticket 2

Ticket 3
```

Processing follows arrival order.

---

# Application 2: Print Queues

Documents wait to be printed.

```text
Document A

Document B

Document C
```

First submitted.

First printed.

---

# Application 3: Operating Systems

CPU scheduling often uses queues.

Processes wait until resources become available.

---

# Application 4: Web Servers

Incoming requests frequently enter processing queues.

Example:

```text
Request 1

Request 2

Request 3
```

Requests are handled sequentially.

---

# Application 5: Ticket Booking Systems

Consider:

```text
Concert Booking

Flight Reservations

Cinema Tickets
```

Customers are placed in a queue.

The first customer receives service first.

---

# Stack vs Queue

| Feature | Stack | Queue |
|----------|---------|--------|
| Processing Order | LIFO | FIFO |
| Insert Location | Top | Rear |
| Remove Location | Top | Front |
| Real-World Example | Stack of Books | Supermarket Queue |

---

# When Should You Use a Stack?

Use a stack when:

```text
Latest item should be processed first.
```

Examples:

```text
Undo operations

Browser history

Function calls

Expression evaluation
```

---

# When Should You Use a Queue?

Use a queue when:

```text
Items should be processed in arrival order.
```

Examples:

```text
Customer service

Printing

Task scheduling

Resource allocation
```

---

# Mini Project: Browser History Simulator

Build a stack-based system.

Requirements:

```text
Visit website

Go back

View current page
```

Concepts:

```text
Classes

Stacks

Methods
```

---

# Mini Project: Service Counter Simulator

Build a queue-based system.

Requirements:

```text
Add customer

Serve next customer

Display waiting customers
```

Concepts:

```text
Queues

Classes

Lists

Methods
```

---

# Common Beginner Mistakes

## Confusing FIFO and LIFO

Remember:

```text
Stack = LIFO

Queue = FIFO
```

---

## Using pop(0) on Large Lists

This works but can become inefficient.

Prefer:

```python
deque
```

for production-quality queue implementations.

---

## Accessing Empty Structures

Attempting:

```python
stack.pop()
```

or

```python
queue.dequeue()
```

on an empty collection should be handled carefully.

---

# Summary

In this tutorial, you learned:

✅ Why data structures matter.

✅ The principles behind stacks and queues.

✅ How LIFO and FIFO processing work.

✅ Core stack operations.

✅ Core queue operations.

✅ How stacks and queues are implemented in Python.

✅ Real-world applications of both structures.

✅ Why circular queues improve efficiency.

Stacks and queues are among the most important foundational data structures and frequently appear in interviews, system design discussions, and real-world software systems.

---

# Knowledge Check

1. What does LIFO mean?
2. What does FIFO mean?
3. When should a stack be used?
4. When should a queue be used?
5. Why is browser history typically implemented using a stack?
6. Why is customer service typically implemented using a queue?
7. What is the purpose of a circular queue?
8. Why is `pop(0)` inefficient on large lists?
9. What operation adds data to a stack?
10. What operation removes data from a queue?

---

# Next Tutorial

In **Tutorial 09: Design Patterns and File Handling**, we will explore reusable software design solutions and learn how Python applications interact with external files for persistent data storage.
