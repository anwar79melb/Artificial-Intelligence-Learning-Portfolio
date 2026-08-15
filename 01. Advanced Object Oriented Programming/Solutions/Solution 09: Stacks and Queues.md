# Solution 09: Stacks and Queues

## Overview

This document provides suggested solutions for **Exercise 09: Stacks and Queues**.

This exercise focuses on:

- Stack Data Structures
- Queue Data Structures
- Class Design
- Encapsulation
- Real-World Applications
- Problem Solving

Stacks and Queues are among the most important linear data structures in computer science and appear frequently in:

```text
Operating Systems

Web Browsers

Booking Systems

Customer Service Systems

Compilers

Database Systems
```

---

# Question 1

## Implement a Stack Class

### Required Methods

```python
push()

pop()

top()

is_empty()
```

---

# Understanding a Stack

A stack follows:

```text
Last In First Out (LIFO)
```

or

```text
First In Last Out (FILO)
```

---

## Example

Suppose we push:

```text
A

B

C
```

The stack becomes:

```text
TOP

C
B
A
```

Removing an element:

```text
pop()
```

returns:

```text
C
```

because it was added last.

---

# UML Design

```text
+----------------------+
|        Stack         |
+----------------------+
| items : List         |
+----------------------+
| push()              |
| pop()               |
| top()               |
| is_empty()          |
+----------------------+
```

---

# Implementation

```python
class Stack:

    def __init__(self):

        self.items = []

    def push(self, item):

        self.items.append(item)

    def pop(self):

        if self.is_empty():

            return None

        return self.items.pop()

    def top(self):

        if self.is_empty():

            return None

        return self.items[-1]

    def is_empty(self):

        return len(self.items) == 0
```

---

# Testing the Stack

```python
stack = Stack()

stack.push("A")
stack.push("B")
stack.push("C")

print(stack.top())

print(stack.pop())

print(stack.top())
```

---

# Sample Output

```text
C

C

B
```

---

# Discussion

This implementation uses Python's built-in list.

Operations:

```python
append()
```

and

```python
pop()
```

naturally support stack behaviour.

---

# Question 2

## Browser History Simulator

### Requirements

```text
Visit Page

Back

Display Current Page
```

Use a Stack.

---

# Analysis

Browser history behaves like a stack.

Example:

```text
Visit Google

Visit YouTube

Visit GitHub
```

History:

```text
TOP

GitHub

YouTube

Google
```

Pressing:

```text
Back
```

returns:

```text
YouTube
```

---

# Design

The current page should always be:

```python
top()
```

of the stack.

---

# Implementation

```python
class BrowserHistory:

    def __init__(self):

        self.history = Stack()

    def visit(self, page):

        self.history.push(page)

    def back(self):

        self.history.pop()

    def current_page(self):

        return self.history.top()
```

---

# Testing the Browser

```python
browser = BrowserHistory()

browser.visit("Google")

browser.visit("YouTube")

browser.visit("GitHub")

print(
    browser.current_page()
)
```

Output:

```text
GitHub
```

---

## Going Back

```python
browser.back()

print(
    browser.current_page()
)
```

Output:

```text
YouTube
```

---

# Discussion

This demonstrates a practical application of:

```text
Stacks

Classes

Composition
```

where:

```python
BrowserHistory
```

contains a:

```python
Stack
```

---

# Question 3

## Implement a Queue Class

### Required Methods

```python
enqueue()

dequeue()

first()

is_empty()
```

---

# Understanding a Queue

Queues follow:

```text
First In First Out (FIFO)
```

---

## Example

Insert:

```text
Alex

John

Emma
```

Queue:

```text
Front

Alex
John
Emma

Rear
```

Removing an item returns:

```text
Alex
```

because Alex entered first.

---

# UML Design

```text
+----------------------+
|        Queue         |
+----------------------+
| items : List         |
+----------------------+
| enqueue()            |
| dequeue()            |
| first()              |
| is_empty()           |
+----------------------+
```

---

# Implementation

```python
class Queue:

    def __init__(self):

        self.items = []

    def enqueue(self, item):

        self.items.append(item)

    def dequeue(self):

        if self.is_empty():

            return None

        return self.items.pop(0)

    def first(self):

        if self.is_empty():

            return None

        return self.items[0]

    def is_empty(self):

        return len(self.items) == 0
```

---

# Testing the Queue

```python
queue = Queue()

queue.enqueue("Alex")

queue.enqueue("John")

queue.enqueue("Emma")

print(queue.first())
```

Output:

```text
Alex
```

---

## Remove Customer

```python
print(queue.dequeue())

print(queue.first())
```

Output:

```text
Alex

John
```

---

# Discussion

The first element added is the first element removed.

This is:

```text
FIFO
```

behaviour.

---

# Question 4

## Customer Service Queue System

### Requirements

```text
Add Customer

Serve Customer

Display Waiting Customers
```

---

# Analysis

Customer service systems typically operate using queues.

Reason:

```text
First Arrived

First Served
```

---

# UML Design

```text
+--------------------------+
| CustomerServiceSystem    |
+--------------------------+
| queue : Queue            |
+--------------------------+
| add_customer()           |
| serve_customer()         |
| display_customers()      |
+--------------------------+
```

---

# Implementation

```python
class CustomerServiceSystem:

    def __init__(self):

        self.queue = Queue()

    def add_customer(
        self,
        customer_name
    ):

        self.queue.enqueue(
            customer_name
        )

    def serve_customer(self):

        customer = (
            self.queue.dequeue()
        )

        if customer:

            print(
                customer,
                "served."
            )

    def display_customers(self):

        print(
            "\nWaiting Customers:"
        )

        for customer in self.queue.items:

            print(customer)
```

---

# Testing the System

```python
system = CustomerServiceSystem()

system.add_customer("Alex")

system.add_customer("Emma")

system.add_customer("John")

system.display_customers()
```

---

# Output

```text
Waiting Customers:

Alex

Emma

John
```

---

# Serve Customer

```python
system.serve_customer()
```

Output:

```text
Alex served.
```

---

# Display Updated Queue

```python
system.display_customers()
```

Output:

```text
Waiting Customers:

Emma

John
```

---

# Discussion

This application demonstrates:

```text
Queues

Classes

Methods

Object-Oriented Design
```

working together.

---

# Reflection Question

## Compare Stack and Queue

---

# Stack

### Processing Rule

```text
LIFO

(Last In First Out)
```

---

## Example

```text
Pile of plates

Browser history

Undo operation
```

---

## Removal Order

```text
Most Recent Item
```

is processed first.

---

# Queue

### Processing Rule

```text
FIFO

(First In First Out)
```

---

## Example

```text
Bank queue

Ticket system

Customer service
```

---

## Removal Order

```text
Oldest Item
```

is processed first.

---

# Comparison Table

| Feature | Stack | Queue |
|----------|--------|--------|
| Rule | LIFO | FIFO |
| Insert | Top | Rear |
| Remove | Top | Front |
| Real-World Example | Browser History | Customer Service |
| Typical Operations | Push / Pop | Enqueue / Dequeue |

---

# When Should You Use a Stack?

Use a stack when:

```text
Recent items should be processed first.
```

Examples:

```text
Undo operations

Function calls

Expression evaluation

Browser history
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

Task scheduling

Print queues

Booking systems
```

---

# Extension Exercise

## Queue Using deque

The queue implementation above uses:

```python
list.pop(0)
```

which becomes inefficient for very large collections.

A better solution uses:

```python
collections.deque
```

---

## Improved Queue

```python
from collections import deque

class Queue:

    def __init__(self):

        self.items = deque()

    def enqueue(self, item):

        self.items.append(item)

    def dequeue(self):

        if len(self.items) == 0:

            return None

        return self.items.popleft()

    def first(self):

        if len(self.items) == 0:

            return None

        return self.items[0]
```

This is the preferred implementation in professional systems.

---

# Complexity Analysis

## Stack

| Operation | Complexity |
|-----------|------------|
| Push | O(1) |
| Pop | O(1) |
| Top | O(1) |

---

## Queue (List Version)

| Operation | Complexity |
|-----------|------------|
| Enqueue | O(1) |
| Dequeue | O(n) |

---

## Queue (deque Version)

| Operation | Complexity |
|-----------|------------|
| Enqueue | O(1) |
| Dequeue | O(1) |

---

# Self-Evaluation Checklist

After completing Exercise 09, you should be able to:

✅ Explain LIFO and FIFO.

✅ Implement a Stack class.

✅ Implement a Queue class.

✅ Design systems using stack behaviour.

✅ Design systems using queue behaviour.

✅ Understand browser history implementation.

✅ Understand customer service queue implementation.

✅ Compare stack and queue applications.

✅ Analyze operation complexity.

---

# Key Takeaways

This exercise introduced two of the most important linear data structures:

```text
Stack

Queue
```

These structures are widely used in:

```text
Software Engineering

Web Development

Operating Systems

Artificial Intelligence

Database Systems

Cloud Computing
```

Understanding when and why to use them is an essential skill for every software engineer.
