# Tutorial 07: Polymorphism and String Processing in Python

## Overview

So far in this course, we have learned about:

- Classes and Objects
- Encapsulation
- Inheritance
- Class Relationships
- Method Overriding

One of the primary reasons inheritance exists is to support a powerful Object-Oriented Programming principle known as **Polymorphism**.

Polymorphism allows different types of objects to be treated through a common interface while still behaving according to their own implementation.

In practical software development, polymorphism improves:

- Flexibility
- Reusability
- Extensibility
- Maintainability

In addition to polymorphism, this tutorial explores another fundamental component of programming: **strings**.

Almost every application processes textual information, including:

- User names
- Email addresses
- Product descriptions
- Search queries
- Documents
- Social media content
- Natural Language Processing (NLP) datasets

Understanding string manipulation is therefore essential for software engineering, data analytics, and artificial intelligence.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Understand the concept of polymorphism.
- Explain how polymorphism works with inheritance.
- Develop polymorphic programs in Python.
- Understand string objects and their characteristics.
- Use string indexing and slicing.
- Apply common string operations.
- Manipulate textual data efficiently.
- Build applications involving text processing.

---

# What is Polymorphism?

The word **polymorphism** comes from two Greek words:

```text
Poly = Many

Morph = Forms
```

Therefore:

```text
Polymorphism = Many Forms
```

In Object-Oriented Programming, polymorphism means:

> Different objects can respond to the same message in different ways.

The interface remains the same.

The implementation varies.

---

# Why Do We Need Polymorphism?

Consider a company that employs:

```text
Managers

SalesPersons

Secretaries

Technicians
```

All employees receive salaries.

Therefore we may define:

```python
get_pay()
```

for every employee.

However:

```text
Managers
    Salary + Allowance

SalesPersons
    Salary + Commission

Technicians
    Salary + Overtime

Secretaries
    Salary Only
```

Even though every object uses:

```python
get_pay()
```

the calculation differs.

This is exactly where polymorphism becomes valuable.

---

# A Real-World Analogy

Imagine a remote control.

You press:

```text
Power Button
```

on different devices:

```text
Television

Air Conditioner

Projector
```

The command is identical:

```text
Power
```

But each device performs a different action.

This is very similar to polymorphism.

---

# Understanding Polymorphism Through Shapes

Suppose we design a drawing application.

All shapes share a common operation:

```python
get_area()
```

However:

```text
Rectangle
Circle
Triangle
Square
```

calculate area differently.

---

## Shape Hierarchy

```text
                Shape
                   |
    ---------------------------------
    |              |               |
 Rectangle      Circle        Triangle
```

Every shape supports:

```python
get_area()
```

but the implementation depends on the shape itself.

---

# Example: Base Class

```python
class Shape:

    def get_area(self):

        pass
```

The base class defines a contract.

Every shape agrees that:

```python
get_area()
```

will exist.

---

# Rectangle Implementation

```python
class Rectangle(Shape):

    def __init__(
        self,
        length,
        width
    ):

        self.length = length
        self.width = width

    def get_area(self):

        return (
            self.length *
            self.width
        )
```

---

# Circle Implementation

```python
import math

class Circle(Shape):

    def __init__(
        self,
        radius
    ):

        self.radius = radius

    def get_area(self):

        return (
            math.pi *
            self.radius ** 2
        )
```

---

# Using Polymorphism

```python
shapes = [

    Rectangle(10, 5),

    Circle(3)
]

for shape in shapes:

    print(
        shape.get_area()
    )
```

Observe:

```python
shape.get_area()
```

is identical.

Yet each object executes its own version.

That is polymorphism.

---

# Visualizing Polymorphism

```text
shape.get_area()

         |
         |

 ---------------------
 |         |         |
Rectangle Circle Triangle

   |         |         |

   v         v         v

 Area      Area      Area

(Rect)   (Circle) (Triangle)
```

One message.

Multiple behaviours.

---

# Benefits of Polymorphism

Polymorphism provides several advantages.

---

## 1. Improved Flexibility

New object types can be added without changing existing code.

Example:

```text
Rectangle

Circle

Triangle

Square
```

A square can be added later without modifying the rest of the system.

---

## 2. Better Maintainability

Programs contain less conditional logic.

Without polymorphism:

```python
if shape == "circle":

    ...

elif shape == "rectangle":

    ...

elif shape == "triangle":

    ...
```

As the application grows, this becomes difficult to maintain.

With polymorphism:

```python
shape.get_area()
```

The correct implementation executes automatically.

---

## 3. Increased Reusability

Existing interfaces can support future object types.

---

# Polymorphism and Method Overriding

Polymorphism and method overriding work together.

Recall what we learned previously:

```text
Inheritance
     ↓
Method Overriding
     ↓
Polymorphism
```

Overriding provides different implementations.

Polymorphism allows those implementations to be used through a common interface.

---

# Mini Project: Shape Calculator

Create the following hierarchy:

```text
Shape

Rectangle

Circle

Triangle

Square
```

Requirements:

- Each subclass must implement `get_area()`
- Store objects inside a list
- Display areas using a loop

Example:

```python
for shape in shapes:

    print(
        shape.get_area()
    )
```

No conditional statements should be required.

---

# Introduction to Strings

Most software applications process text.

Examples include:

```text
Names

Passwords

Emails

Messages

Documents

Reviews

Tweets

Chat Conversations
```

In Python, text is represented using strings.

---

# What is a String?

A string is a sequence of characters.

Examples:

```python
name = "Alex"

course = "Artificial Intelligence"

message = "Welcome!"
```

Characters may include:

```text
Letters

Numbers

Symbols

Spaces

Unicode Characters
```

---

# Creating Strings

Using double quotes:

```python
name = "Python"
```

Using single quotes:

```python
name = 'Python'
```

Both are valid.

---

# Strings are Objects

Like lists and dictionaries, strings are objects.

They possess:

- Attributes
- Methods

This is why strings support operations such as:

```python
upper()

lower()

replace()
```

---

# Strings Are Immutable

One of the most important properties of strings is:

```text
Strings cannot be modified
after creation.
```

This property is known as immutability.

---

## Example

```python
word = "Python"

word[0] = "J"
```

Result:

```text
TypeError
```

Python does not allow individual characters to be changed.

---

# Character Positions

Strings use indexing just like lists.

Example:

```python
word = "Python"
```

Indexes:

```text
P   y   t   h   o   n

0   1   2   3   4   5
```

---

# Accessing Characters

```python
word = "Python"

print(word[0])
```

Output:

```text
P
```

---

# Negative Indexing

Strings also support negative indexes.

Example:

```python
word[-1]
```

Output:

```text
n
```

---

# String Slicing

Strings support slicing in the same way as lists.

General syntax:

```python
string[start:stop:step]
```

---

## Example

```python
course =

"Artificial Intelligence"

print(course[0:10])
```

Output:

```text
Artificial
```

---

# Extracting the First Word

```python
text =

"Advanced Python Programming"

print(text[:8])
```

Output:

```text
Advanced
```

---

# Skipping Characters

```python
text = "Python"

print(text[::2])
```

Output:

```text
Pto
```

Python selects every second character.

---

# Built-In String Functions

Python provides several useful built-in functions.

---

## len()

Returns the number of characters.

```python
name = "Python"

len(name)
```

Output:

```text
6
```

---

## max()

Returns the character with the highest value.

```python
max("Python")
```

---

## min()

Returns the character with the lowest value.

```python
min("Python")
```

---

# String Concatenation

Strings can be joined together using:

```python
+
```

---

## Example

```python
first = "Artificial"

second = "Intelligence"

result = first + " " + second
```

Result:

```text
Artificial Intelligence
```

---

# String Repetition

The multiplication operator can duplicate strings.

Example:

```python
print("AI " * 3)
```

Output:

```text
AI AI AI
```

---

# Comparing Strings

Strings can be compared using comparison operators.

Example:

```python
"Apple" < "Banana"
```

Result:

```text
True
```

Python compares character values internally.

---

# Common String Methods

Python provides many useful string methods.

---

## Uppercase Conversion

```python
text = "python"

print(
    text.upper()
)
```

Output:

```text
PYTHON
```

---

## Lowercase Conversion

```python
text = "PYTHON"

print(
    text.lower()
)
```

Output:

```text
python
```

---

## Capitalization

```python
text = "python"

print(
    text.capitalize()
)
```

Output:

```text
Python
```

---

## Replacing Text

```python
text =

"Python Programming"

print(
    text.replace(
        "Python",
        "AI"
    )
)
```

Output:

```text
AI Programming
```

---

## Removing Extra Spaces

```python
text =

"   Python   "

print(
    text.strip()
)
```

Result:

```text
Python
```

---

## Splitting Strings

```python
sentence =

"Python is powerful"

words = sentence.split()
```

Result:

```python
['Python', 'is', 'powerful']
```

This is commonly used in text processing and NLP.

---

# String Processing in Real Applications

Strings are heavily used in:

### Web Applications

```text
Usernames
Passwords
URLs
```

### Business Systems

```text
Invoices
Emails
Reports
```

### Artificial Intelligence

```text
Sentiment Analysis

Document Classification

Chatbots

Language Models
```

### Cybersecurity

```text
Log Analysis

Threat Detection

Network Monitoring
```

---

# Mini Project: Simple Text Analyzer

Create a program that:

1. Accepts a sentence from the user.
2. Displays:
   - Total characters
   - Total words
   - Uppercase version
   - Lowercase version
3. Identifies the longest word.

This project combines:

```text
Input

Strings

Functions

Collections
```

---

# Common Beginner Mistakes

## Confusing Strings and Numbers

```python
"100" + "20"
```

Output:

```text
10020
```

Not:

```text
120
```

Convert first:

```python
int("100") + int("20")
```

---

## Trying to Modify a String

```python
word[0] = "A"
```

Produces an error because strings are immutable.

---

## Forgetting Parentheses

Incorrect:

```python
text.upper
```

Correct:

```python
text.upper()
```

---

## Misunderstanding Slicing

Remember:

```python
text[2:5]
```

includes:

```text
2
3
4
```

but not:

```text
5
```

---

# Summary

In this tutorial, you learned:

✅ What polymorphism is.

✅ How polymorphism relates to inheritance.

✅ Why method overriding enables polymorphism.

✅ How polymorphism improves software flexibility.

✅ What strings are and how they are stored.

✅ String indexing and slicing.

✅ Common string operations.

✅ Useful string methods.

✅ How strings are handled in real-world applications.

Polymorphism is one of the most powerful concepts in Object-Oriented Programming and forms the foundation of many software design patterns. Combined with strong string manipulation skills, it enables developers to build flexible and intelligent applications.

---

# Knowledge Check

1. What is polymorphism?
2. How does polymorphism relate to inheritance?
3. What is method overriding?
4. Why does polymorphism improve maintainability?
5. What does string immutability mean?
6. What is the difference between indexing and slicing?
7. What is returned by `text[::2]`?
8. Why are strings important in AI applications?
9. Which string method removes leading and trailing spaces?
10. What does the `split()` method do?

---

# Next Tutorial

In **Tutorial 08: Fundamental Data Structures**, we will explore stacks and queues, two important data structures that support efficient problem solving and form the basis of many software systems and algorithms.
