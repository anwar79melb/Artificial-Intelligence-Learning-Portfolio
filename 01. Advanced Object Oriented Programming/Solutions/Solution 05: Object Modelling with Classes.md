# Solution 05: Object Modelling with Classes

## Overview

This document provides suggested solutions for **Exercise 05: Classes and Objects**.

The purpose of these exercises is to assess understanding of:

- Classes
- Objects
- Attributes
- Methods
- Constructors
- Encapsulation
- UML Modelling
- Object-Oriented Design

These concepts form the foundation of Object-Oriented Programming and are essential for developing maintainable software systems.

---

# Question 1

## Design a Class Called Book

### Requirements

Attributes:

```text
ISBN
Title
Author
Price
```

Methods:

```text
Display Information

Apply Discount

Update Price
```

Develop a complete Python implementation.

---

# Solution

## Step 1: Identify Attributes

The class must store:

```text
ISBN

Title

Author

Price
```

These become instance attributes.

---

## Step 2: Identify Behaviours

The class should provide methods to:

```text
Display Information

Apply Discount

Update Price
```

These become member functions (methods).

---

## UML Design

```text
+----------------------+
|         Book         |
+----------------------+
| isbn                 |
| title                |
| author               |
| price                |
+----------------------+
| display_info()       |
| apply_discount()     |
| update_price()       |
+----------------------+
```

---

## Python Implementation

```python
class Book:

    def __init__(
        self,
        isbn,
        title,
        author,
        price
    ):

        self.isbn = isbn
        self.title = title
        self.author = author
        self.price = price

    def display_info(self):

        print("\nBOOK DETAILS")
        print("----------------")
        print(f"ISBN   : {self.isbn}")
        print(f"Title  : {self.title}")
        print(f"Author : {self.author}")
        print(f"Price  : ${self.price:.2f}")

    def apply_discount(
        self,
        percentage
    ):

        discount_amount = (
            self.price *
            percentage / 100
        )

        self.price -= discount_amount

    def update_price(
        self,
        new_price
    ):

        self.price = new_price
```

---

## Creating an Object

```python
book1 = Book(

    "9780135166307",

    "Python Programming",

    "John Smith",

    89.95
)
```

---

## Display Book Information

```python
book1.display_info()
```

Output:

```text
BOOK DETAILS
----------------
ISBN   : 9780135166307
Title  : Python Programming
Author : John Smith
Price  : $89.95
```

---

## Applying a Discount

```python
book1.apply_discount(10)

book1.display_info()
```

Output:

```text
BOOK DETAILS
----------------
ISBN   : 9780135166307
Title  : Python Programming
Author : John Smith
Price  : $80.96
```

---

## Updating Price

```python
book1.update_price(99.95)

book1.display_info()
```

Output:

```text
BOOK DETAILS
----------------
ISBN   : 9780135166307
Title  : Python Programming
Author : John Smith
Price  : $99.95
```

---

# Discussion

This solution demonstrates:

```text
Class Definition

Constructor Usage

Object Creation

Method Invocation

Object State Updates
```

The Book class can now be reused throughout larger systems such as:

```text
Library Management Systems

Bookstores

Inventory Systems

E-Commerce Platforms
```

---

# Question 2

## Design a UML Class Diagram for Student

Include:

```text
Attributes

Methods

Constructor
```

---

# Solution

## Requirements Analysis

A Student typically requires:

### Attributes

```text
student_id

name

email

course

gpa
```

---

### Methods

```text
display_details()

update_gpa()

enrol_course()
```

---

## UML Diagram

```text
+----------------------------------+
|             Student              |
+----------------------------------+
| student_id : String              |
| name : String                    |
| email : String                   |
| course : String                  |
| gpa : Float                      |
+----------------------------------+
| Student()                        |
| display_details()                |
| update_gpa()                     |
| enrol_course()                   |
+----------------------------------+
```

---

## UML Explanation

### Class Name

```text
Student
```

represents the blueprint.

---

### Attributes

Represent the student's data.

```text
student_id
name
email
course
gpa
```

---

### Methods

Represent behaviours.

```text
display_details()

update_gpa()

enrol_course()
```

---

### Constructor

Used for initialization.

```text
Student()
```

In Python:

```python
__init__()
```

---

# Python Implementation

```python
class Student:

    def __init__(
        self,
        student_id,
        name,
        email,
        course,
        gpa
    ):

        self.student_id = student_id
        self.name = name
        self.email = email
        self.course = course
        self.gpa = gpa

    def display_details(self):

        print(
            self.student_id,
            self.name,
            self.course
        )

    def update_gpa(
        self,
        new_gpa
    ):

        self.gpa = new_gpa

    def enrol_course(
        self,
        new_course
    ):

        self.course = new_course
```

---

## Example Usage

```python
student = Student(

    "S1001",

    "Alex",

    "alex@email.com",

    "Artificial Intelligence",

    3.8
)

student.display_details()
```

Output:

```text
S1001 Alex Artificial Intelligence
```

---

# Question 3

## Explain the Role of the Constructor

```python
__init__()
```

Why is it useful in object-oriented software design?

---

# Solution

## What Is a Constructor?

A constructor is a special method that automatically executes when an object is created.

In Python, the constructor is:

```python
__init__()
```

---

## Example

```python
class Student:

    def __init__(
        self,
        student_id,
        name
    ):

        self.student_id = student_id

        self.name = name
```

Creating an object:

```python
student = Student(

    "S1001",

    "Alex"
)
```

automatically calls:

```python
__init__()
```

---

## Why Constructors Are Important

Without constructors:

```python
student = Student()

student.student_id = "S1001"

student.name = "Alex"
```

Every attribute must be assigned manually.

---

## With Constructors

```python
student = Student(

    "S1001",

    "Alex"
)
```

Everything is initialized immediately.

---

# Benefits of Constructors

---

## 1. Automatic Initialization

Objects begin life with meaningful values.

Example:

```python
book =
Book(
    "111",
    "Python",
    "John",
    49.95
)
```

All information is assigned during creation.

---

## 2. Improved Reliability

Developers can ensure required data is supplied.

Without constructors:

```python
Student()
```

may produce incomplete objects.

With constructors:

```python
Student(
    "S1001",
    "Alex"
)
```

required information must be provided.

---

## 3. Improved Readability

Large systems become easier to understand.

Example:

```python
employee = Employee(

    "E100",

    "John",

    70000
)
```

immediately reveals important information.

---

## 4. Supports Encapsulation

Constructors provide controlled access to internal state initialization.

This helps maintain object integrity.

---

## Real-World Analogy

Imagine purchasing a new car.

When delivered:

```text
Engine Installed

Seats Installed

Wheels Installed

Fuel Added
```

The car is ready to use.

A constructor performs a similar task for software objects.

---

## Constructor Workflow

```text
Create Object
       |
       v
Call Constructor
       |
       v
Initialize Attributes
       |
       v
Object Ready
```

---

# Reflection

This exercise introduced the essential building blocks of object-oriented design.

---

## Question 1

Focused on:

```text
Class Design

Attributes

Methods

Object Creation
```

---

## Question 2

Focused on:

```text
UML Modelling

Object Analysis

Software Design Documentation
```

---

## Question 3

Focused on:

```text
Constructors

Initialization

Object Lifecycle
```

---

# Self-Evaluation Checklist

After completing Exercise 05, you should be able to:

✅ Design classes from requirements.

✅ Identify attributes and methods.

✅ Create UML class diagrams.

✅ Implement classes in Python.

✅ Use constructors correctly.

✅ Instantiate objects.

✅ Modify object state through methods.

✅ Explain the purpose of constructors.

✅ Apply object-oriented thinking to software design.

---

# Key Takeaways

Classes and objects allow software developers to model real-world entities in a structured and maintainable way.

Important concepts reinforced in this exercise include:

```text
Classes

Objects

Attributes

Methods

Constructors

UML Design
```

These concepts serve as the foundation for more advanced topics such as:

```text
Inheritance

Polymorphism

Design Patterns

Software Architecture
```

which are explored in the subsequent exercises.
