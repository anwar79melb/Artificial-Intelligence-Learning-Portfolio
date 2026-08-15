# Tutorial 05: Object-Oriented Design with Classes

## Overview

In the previous tutorials, we learned how to:

- Store information using variables.
- Organize collections using lists, tuples, and dictionaries.
- Build reusable solutions using functions.

While these tools are powerful, they become difficult to manage when real-world systems grow in complexity.

Consider building:

- A Library Management System
- A Banking System
- A Hospital Management System
- An Online Shopping Platform

These systems involve many entities that interact with one another.

For example:

```text
Customers place orders.
Librarians manage books.
Students enrol in courses.
Doctors treat patients.
```

The challenge is not simply storing data but also representing relationships and behaviours.

Object-Oriented Programming (OOP) addresses this challenge by organizing software around objects and classes.

In this tutorial, we will move beyond procedural programming and begin designing software from an object-oriented perspective.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Understand the relationship between objects and classes.
- Model real-world entities as software objects.
- Define attributes and methods.
- Create classes in Python.
- Instantiate objects from classes.
- Use constructors to initialize objects.
- Understand instance attributes and class attributes.
- Understand encapsulation and object interaction.
- Design simple object-oriented solutions.

---

# From Real-World Objects to Software Objects

To understand Object-Oriented Programming, we must first observe the real world.

Consider a furniture store.

Inside the store we may find:

```text
Customers
Salespersons
Managers
Products
Orders
```

Each of these is an object.

---

# What Is an Object?

An object is an entity that possesses:

## Attributes

Properties that describe the object.

Examples:

```text
Name
Address
Price
Age
Salary
```

## Behaviours

Actions the object can perform.

Examples:

```text
Place Order
Borrow Book
Make Payment
Calculate Salary
```

---

# Example: Customer Object

A customer may have:

### Attributes

```text
Name
Address
Budget
```

### Behaviours

```text
Place Order
View Products
Make Payment
```

Diagram:

```text
+------------------+
|    Customer      |
+------------------+
| Name             |
| Address          |
| Budget           |
+------------------+
| PlaceOrder()     |
| MakePayment()    |
+------------------+
```

---

# Objects Have Identity

Even when two objects belong to the same category, they remain distinct.

Example:

```text
Customer A:

Name     = Alex
Budget   = $2000

Customer B:

Name     = Julia
Budget   = $1000
```

Although both are customers, each possesses its own data.

This idea is fundamental to object-oriented design.

---

# Grouping Similar Objects

Suppose a store has hundreds of customers.

Instead of creating each customer from scratch, we identify what customers have in common.

Common characteristics:

```text
Name
Address
Budget
PlaceOrder()
```

These shared characteristics form a blueprint.

This blueprint is called a class.

---

# What Is a Class?

A class is a template used to create objects.

Think of a class as an architectural blueprint.

Think of an object as a completed building.

```text
Blueprint
     ↓
Class

Actual Building
     ↓
Object
```

A single blueprint can be used to create many buildings.

Similarly:

```text
One Class
     ↓
Many Objects
```

---

# Visualizing Classes and Objects

```text
                Customer
                 (Class)

                    |
    ---------------------------------
    |               |               |
    v               v               v

  Alex           Julia          Michael

 Object         Object          Object
```

The class defines the structure.

Objects store the actual values.

---

# Class Versus Object

| Class | Object |
|---------|---------|
| Blueprint | Instance |
| Defines structure | Contains data |
| Created once | Created many times |
| Abstract concept | Real entity |

Example:

```text
Customer  → Class

Alex      → Object

Julia     → Object

Chris     → Object
```

---

# Understanding UML Diagrams

Software engineers commonly represent classes using UML (Unified Modeling Language).

A UML class diagram contains:

```text
Class Name
Attributes
Methods
```

Example:

```text
+----------------------+
|      Customer        |
+----------------------+
| name : String        |
| address : String     |
| budget : Float       |
+----------------------+
| placeOrder()         |
| makePayment()        |
+----------------------+
```

Many software designs begin with UML before coding starts.

---

# Creating Classes in Python

Python uses the `class` keyword.

General syntax:

```python
class ClassName:

    statements
```

Example:

```python
class Customer:

    pass
```

The keyword `pass` is a placeholder indicating an empty class.

---

# Attributes

Attributes represent data owned by an object.

Example:

```python
class Customer:

    name = ""

    address = ""
```

Attributes describe the object's state.

---

# Methods

Methods represent behaviours.

Example:

```python
class Customer:

    def place_order(self):

        print(
            "Order Placed"
        )
```

Methods define what an object can do.

---

# Understanding self

One concept that initially confuses beginners is the `self` parameter.

Consider:

```python
class Customer:

    def place_order(self):

        print("Order Placed")
```

`self` refers to the current object using the method.

Think of it as:

```text
"This Object"
```

Many programming languages use:

```java
this
```

Python makes it explicit through:

```python
self
```

---

# Why Is self Necessary?

Imagine two customer objects.

```python
alex = Customer()

julia = Customer()
```

When:

```python
alex.place_order()
```

is called,

Python knows the action belongs to:

```python
alex
```

because `self` points to that object.

---

# Creating Objects

Objects are created from classes.

This process is called instantiation.

Example:

```python
customer1 = Customer()

customer2 = Customer()
```

Now we have two separate objects.

---

# Assigning Values to Objects

```python
customer1.name = "Alex"

customer1.address = "Melbourne"
```

These values belong only to:

```python
customer1
```

Other objects are unaffected.

---

# The Need for Constructors

Creating objects manually becomes tedious.

Imagine:

```python
customer.name = "Alex"

customer.address = "Melbourne"

customer.budget = 2000
```

for every customer.

Constructors solve this issue.

---

# What Is a Constructor?

A constructor initializes an object when it is created.

Python uses a special method:

```python
__init__()
```

---

# Constructor Syntax

```python
class Customer:

    def __init__(
        self,
        name,
        address
    ):

        self.name = name

        self.address = address
```

---

# Creating Objects with a Constructor

```python
customer1 = Customer(
    "Alex",
    "Melbourne"
)

customer2 = Customer(
    "Julia",
    "Sydney"
)
```

Now each object is properly initialized automatically.

---

# Complete Example

```python
class Customer:

    def __init__(
        self,
        name,
        budget
    ):

        self.name = name

        self.budget = budget

    def display(self):

        print(
            self.name,
            self.budget
        )
```

Creating objects:

```python
customer = Customer(
    "Alex",
    2000
)

customer.display()
```

Output:

```text
Alex 2000
```

---

# Object Interaction

Object-oriented systems are built around communication between objects.

Example:

```text
Customer
    |
    | places order
    V
SalesPerson
```

Objects communicate through method calls.

This communication is often called messaging.

---

# Understanding Messages

A message generally consists of:

```text
Object Reference
Method Name
Arguments
```

Example:

```python
salesperson.take_order(
    "Desk Chair"
)
```

Here:

```text
salesperson → Object Reference

take_order  → Method

"Desk Chair" → Argument
```

---

# Real-World Example

Imagine:

```python
lawrence.take_order(
    "Sofa",
    "1 Robinson Rd",
    "2026-08-15"
)
```

The customer asks for a sofa.

The salesperson receives the request.

The salesperson returns a result.

This closely mirrors real-world interactions.

---

# Instance Attributes

Most attributes belong to individual objects.

Example:

```python
self.name

self.address

self.budget
```

Different customers have different values.

These are called instance attributes.

---

# Class Attributes

Some information belongs to the class itself rather than individual objects.

Example:

```python
class Customer:

    total_customers = 0
```

This attribute is shared by every customer object.

---

# Example

```python
class Customer:

    total_customers = 0

    def __init__(self):

        Customer.total_customers += 1
```

Each time a customer is created:

```text
total_customers
```

increases.

---

# Instance vs Class Attributes

| Instance Attribute | Class Attribute |
|-------------------|----------------|
| Belongs to one object | Shared by all objects |
| Different values | Same value |
| self.attribute | Class.attribute |

Example:

```python
self.name
```

vs

```python
Customer.total_customers
```

---

# Encapsulation

One of the most important principles of OOP is encapsulation.

Encapsulation means:

```text
Hide internal complexity.
Expose useful functionality.
```

---

# ATM Analogy

Consider an ATM.

Users can:

```text
Deposit
Withdraw
Check Balance
```

They cannot directly access:

```text
Bank Database
Security Systems
Network Services
```

The system hides its internal implementation.

---

# Encapsulation in Software

```text
      User

        |

        v

 -------------------
 |     Object      |
 -------------------

 Hidden Data
 Hidden Logic

 Public Methods
```

Users interact through methods rather than manipulating internal data directly.

---

# Benefits of Encapsulation

Encapsulation provides:

- Security
- Simplicity
- Maintainability
- Better software design

---

# Designing a Library Member Class

Let's model something familiar.

```text
Library Member
```

Attributes:

```text
Member ID
Name
Email
Borrowed Books
```

Methods:

```text
BorrowBook()
ReturnBook()
DisplayDetails()
```

UML:

```text
+----------------------+
|    LibraryMember     |
+----------------------+
| member_id            |
| name                 |
| email                |
+----------------------+
| borrow_book()        |
| return_book()        |
| display_details()    |
+----------------------+
```

---

# Mini Project

Design a class named:

```text
Book
```

Requirements:

Attributes:

```text
Title
Author
ISBN
Available Copies
```

Methods:

```text
Borrow()
Return()
Display()
```

Implement the solution in Python using:

```python
class Book
```

and a constructor.

---

# Common Beginner Mistakes

## Forgetting self

Incorrect:

```python
def display():

    print(name)
```

Correct:

```python
def display(self):

    print(self.name)
```

---

## Confusing Classes and Objects

Class:

```python
Customer
```

Object:

```python
alex
```

---

## Forgetting to Create Objects

Defining a class alone does not create an object.

```python
class Customer:
    pass
```

Objects must still be instantiated.

---

## Accessing Attributes Incorrectly

Use:

```python
self.attribute
```

inside class methods.

---

# Summary

In this tutorial, you learned:

✅ What objects are.

✅ How objects model real-world entities.

✅ The relationship between classes and objects.

✅ How UML diagrams describe software structures.

✅ How to create classes in Python.

✅ How to define attributes and methods.

✅ The purpose of constructors.

✅ The role of `self`.

✅ The difference between instance and class attributes.

✅ How encapsulation improves software design.

These concepts form the foundation of Object-Oriented Programming and prepare us for more advanced topics such as inheritance, class relationships, and polymorphism.

---

# Knowledge Check

1. What is the difference between a class and an object?
2. What role does a constructor play?
3. Why is `self` required in Python?
4. What is encapsulation?
5. What is the difference between an instance attribute and a class attribute?
6. What is object instantiation?
7. Why do software engineers use UML diagrams?

---

# Next Tutorial

In **Tutorial 06: Inheritance and Class Relationships**, we will explore how classes can inherit from one another, how software engineers build class hierarchies, and how inheritance promotes code reuse and maintainability.
