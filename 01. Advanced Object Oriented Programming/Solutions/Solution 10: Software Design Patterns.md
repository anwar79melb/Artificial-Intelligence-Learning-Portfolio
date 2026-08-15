# Solution 10: Software Design Patterns

## Overview

This document provides suggested solutions for **Exercise 10: Software Design Patterns**.

The purpose of this exercise is to develop an understanding of:

- Reusable software design solutions
- Object creation strategies
- Structural design patterns
- Maintainable software architecture
- Real-world applications of design patterns

Design patterns are not programming languages or libraries. They are proven approaches to solving recurring software design problems.

---

# Question 1

## Research and Explain

```text
Singleton Pattern

Adapter Pattern

Factory Pattern
```

For each pattern provide:

```text
Purpose

Advantages

Disadvantages

Use Cases
```

---

# Solution

# 1. Singleton Pattern

## Purpose

The Singleton Pattern ensures that a class has only one instance throughout the lifetime of an application.

Only one object can exist.

All parts of the application access the same instance.

---

## Concept

Without Singleton:

```python
db1 = Database()

db2 = Database()

db3 = Database()
```

Multiple objects exist.

---

With Singleton:

```python
db1 = Database()

db2 = Database()

db3 = Database()
```

All variables refer to:

```text
The Same Object
```

---

## UML

```text
+--------------------+
|     Singleton      |
+--------------------+
| _instance          |
+--------------------+
| get_instance()     |
+--------------------+
```

---

## Advantages

### Ensures a Single Instance

Example:

```text
Application Settings

Database Configuration
```

---

### Global Access Point

Any part of the program can access the same object.

---

### Saves Resources

Avoids unnecessary object creation.

---

## Disadvantages

### Difficult to Test

Global state can make unit testing more difficult.

---

### Tight Coupling

Parts of the system may become overly dependent on the Singleton object.

---

### Potential Concurrency Issues

Special handling may be required in multithreaded applications.

---

## Real-World Use Cases

```text
Database Connections

Logging Systems

Application Configuration

Printer Spoolers

Cache Managers
```

---

# 2. Adapter Pattern

## Purpose

The Adapter Pattern allows incompatible interfaces to work together.

It acts as a translator between two components.

---

## Real-World Analogy

Suppose:

```text
Laptop Charger
```

uses:

```text
Australian Plug
```

but the hotel provides:

```text
European Socket
```

An adapter allows them to work together.

---

## UML

```text
Client
  |
Adapter
  |
Existing Class
```

---

## Advantages

### Reuse Existing Code

Existing implementations do not need modification.

---

### Improves Compatibility

Different systems can communicate easily.

---

### Reduces Development Time

Developers can integrate older systems quickly.

---

## Disadvantages

### Extra Layer

Adds additional complexity.

---

### More Objects

Additional classes may be required.

---

## Real-World Use Cases

```text
Legacy System Integration

Database Drivers

Payment Gateways

Third-Party APIs

Hardware Interfaces
```

---

## Example

Suppose an old payment gateway uses:

```python
make_payment()
```

but the new application expects:

```python
pay()
```

An adapter can bridge the difference.

---

# 3. Factory Pattern

## Purpose

The Factory Pattern creates objects without exposing object creation details to the client.

Instead of using:

```python
ClassName()
```

directly, a factory decides what object to create.

---

## UML

```text
Client

   |

Factory

   |

-----------------
|       |       |

A       B       C
```

---

## Advantages

### Decouples Object Creation

Client code does not depend on specific classes.

---

### Easier Maintenance

Object creation logic exists in one location.

---

### Supports Extensibility

New object types can be added easily.

---

## Disadvantages

### Additional Complexity

More classes are required.

---

### Overkill for Small Systems

Simple applications may not need a factory.

---

## Real-World Use Cases

```text
Document Editors

Payment Systems

GUI Components

Game Development

Report Generation Systems
```

---

# Example

Suppose an application supports:

```text
PDF Reports

Excel Reports

CSV Reports
```

The factory creates the appropriate report type automatically.

---

# Comparison Table

| Pattern | Main Purpose |
|----------|-------------|
| Singleton | One object only |
| Adapter | Interface conversion |
| Factory | Object creation |

---

# Question 2

## Develop a Singleton Class Named ConfigurationManager

Only one configuration object should exist.

---

# Solution

## Design Analysis

The system should guarantee:

```text
Only One Configuration Object
```

regardless of how many times the class is instantiated.

---

## Implementation

```python
class ConfigurationManager:

    _instance = None

    def __new__(cls):

        if cls._instance is None:

            cls._instance = (
                super().__new__(cls)
            )

        return cls._instance

    def __init__(self):

        self.application_name = (
            "University System"
        )

        self.version = "1.0"
```

---

# Testing the Singleton

```python
config1 = ConfigurationManager()

config2 = ConfigurationManager()

print(config1 is config2)
```

---

# Output

```text
True
```

Both variables reference:

```text
The Same Object
```

---

# Demonstrating Shared State

```python
config1.version = "2.0"

print(config2.version)
```

Output:

```text
2.0
```

Because:

```text
config1

and

config2
```

refer to the same object.

---

# UML Diagram

```text
+---------------------------+
|   ConfigurationManager    |
+---------------------------+
| _instance                 |
| application_name          |
| version                   |
+---------------------------+
| __new__()                 |
+---------------------------+
```

---

# Discussion

This pattern is useful because:

```text
Every Component

Uses The Same Configuration
```

which guarantees consistency.

---

# Question 3

## Provide a Real-World Example Where the Adapter Pattern Would Improve Software Design

---

# Solution

## Scenario

Suppose a university previously used:

```text
Legacy Student Management System
```

The old system exposes:

```python
get_student_name()
```

---

A newly developed portal expects:

```python
get_name()
```

---

# Problem

The interfaces are incompatible.

Existing software cannot communicate correctly.

---

# Poor Solution

Rewrite the entire legacy system.

Problems:

```text
Expensive

Time-Consuming

High Risk
```

---

# Better Solution

Use an Adapter.

---

## Existing System

```python
class LegacyStudent:

    def get_student_name(
        self
    ):

        return "Alex"
```

---

## Adapter

```python
class StudentAdapter:

    def __init__(
        self,
        legacy_student
    ):

        self.legacy_student = (
            legacy_student
        )

    def get_name(self):

        return (
            self.legacy_student
            .get_student_name()
        )
```

---

## Usage

```python
student = LegacyStudent()

adapter = StudentAdapter(
    student
)

print(
    adapter.get_name()
)
```

Output:

```text
Alex
```

---

# UML Representation

```text
Client
   |
   |
StudentAdapter
   |
   |
LegacyStudent
```

---

# Benefits

Using the adapter:

✅ Existing code remains unchanged.

✅ New and old systems work together.

✅ Lower implementation cost.

✅ Reduced project risk.

---

# Reflection

Each design pattern solves a specific type of software problem.

---

## Singleton

Solves:

```text
Too Many Instances
```

---

## Adapter

Solves:

```text
Incompatible Interfaces
```

---

## Factory

Solves:

```text
Complex Object Creation
```

---

# Choosing the Correct Pattern

Ask:

### Do I need exactly one object?

Use:

```text
Singleton
```

---

### Do I need incompatible systems to communicate?

Use:

```text
Adapter
```

---

### Do I need flexible object creation?

Use:

```text
Factory
```

---

# Self-Evaluation Checklist

After completing Exercise 10, you should be able to:

✅ Explain what design patterns are.

✅ Explain how Singleton works.

✅ Explain how Adapter works.

✅ Explain how Factory works.

✅ Identify appropriate use cases.

✅ Implement a Singleton in Python.

✅ Build an Adapter class.

✅ Understand the benefits and limitations of design patterns.

✅ Apply design patterns to real-world software systems.

---

# Key Takeaways

Design patterns provide reusable solutions to recurring software problems.

The three patterns explored in this exercise are among the most commonly encountered in object-oriented software development:

```text
Singleton
    ↓
One Shared Object

Adapter
    ↓
Interface Conversion

Factory
    ↓
Object Creation
```

These design patterns help developers create software that is:

```text
Reusable

Scalable

Maintainable

Flexible
```

and are widely used in enterprise applications, cloud platforms, APIs, frameworks, and large-scale software systems.
