# Tutorial 06: Inheritance and Class Relationships

## Overview

As software systems grow, we often encounter classes that share similar characteristics.

Consider the following examples:

```text
Employee
Manager
SalesPerson
Secretary
```

All of these classes may have:

```text
Name
Employee ID
Email
Contact Number
```

Without a proper design, we would need to repeatedly define the same attributes and methods in multiple classes.

This creates:

- Duplicate code
- Maintenance difficulties
- Increased complexity
- Greater risk of bugs

Object-Oriented Programming solves this problem through **inheritance**.

Inheritance allows classes to share common functionality while still supporting specialized behaviour.

In this tutorial, we will explore:

- Classification
- Generalization
- Specialization
- Class Hierarchies
- Associations
- Aggregation
- Inheritance
- Method Overriding

These concepts are fundamental to designing scalable and maintainable software systems.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Identify classes in a problem domain.
- Understand class relationships.
- Build class hierarchies.
- Apply inheritance correctly.
- Differentiate between "is-a" and "has-a" relationships.
- Implement inheritance in Python.
- Use constructors in inherited classes.
- Apply method overriding.
- Design object-oriented solutions using UML concepts.

---

# Understanding Classification

Software design begins by identifying objects that exist within a problem domain.

This process is called **classification**.

Classification groups similar objects into categories known as classes.

---

## Real-World Example: Furniture Store

Suppose we examine a furniture store.

People working in the store include:

```text
Customers
SalesPersons
Managers
Secretaries
```

Individual people:

```text
Alex
Julia
Chris

Lawrence
Peter

Anna
John

Angela
```

can be grouped into classes according to their roles.

---

### Classification Diagram

```text
Customer
│
├── Alex
├── Julia
└── Chris

SalesPerson
│
├── Lawrence
└── Peter

Manager
│
├── Anna
└── John

Secretary
│
└── Angela
```

Classification helps us organize software systems by identifying meaningful categories.

---

# Another Example: Shapes

Consider various geometric shapes.

```text
Circle
Rectangle
Triangle
Square
Rhombus
```

These objects can also be grouped into meaningful categories.

This process allows us to identify relationships between classes.

---

# Generalization

Once classes have been identified, we often discover shared characteristics.

Generalization extracts common features from multiple classes and places them into a more general superclass.

---

## Example

Consider:

```text
SalesPerson
Manager
Secretary
```

All three contain:

```text
Name
Employee Number
```

Instead of repeating these attributes, we create:

```text
Employee
```

---

### Generalization Diagram

```text
         Employee
         /   |   \
        /    |    \
       /     |     \
Manager  SalesPerson  Secretary
```

Now:

```text
Employee
```

contains shared information while subclasses contain specialized behaviour.

---

# Why Generalization Is Important

Without generalization:

```text
Manager
    Name
    Employee Number

SalesPerson
    Name
    Employee Number

Secretary
    Name
    Employee Number
```

Notice the duplication.

With generalization:

```text
Employee
    Name
    Employee Number
```

The duplicated information exists only once.

Advantages:

✅ Less code

✅ Easier maintenance

✅ Improved consistency

✅ Better software design

---

# Specialization

Specialization is the opposite process.

Instead of finding similarities, we identify differences.

Specialization creates more specific subclasses from a general class.

---

## Example

Suppose we have:

```text
Employee
```

Some employees are:

```text
Managers
Secretaries
SalesPersons
Technicians
```

Each specialized role may introduce new behaviour.

For example:

```text
Manager
    Allowance

SalesPerson
    Commission

Technician
    Skill Level
```

---

### Specialization Diagram

```text
           Employee
                |
    -------------------------
    |      |      |        |
Manager Secretary Sales   Technician
                    Person
```

Specialization allows software to model real-world differences effectively.

---

# Understanding Class Hierarchies

A class hierarchy is a structured arrangement of classes showing inheritance relationships.

The hierarchy usually flows:

```text
General
      ↓
Specific
```

---

## Furniture Store Hierarchy

```text
              Person
                 |
        -----------------
        |               |
     Customer       Employee
                        |
          --------------------------
          |          |            |
      Manager   SalesPerson   Secretary
```

The higher classes represent broader concepts.

Lower classes become increasingly specialized.

---

# Benefits of Class Hierarchies

Class hierarchies improve:

- Code organization
- Reusability
- Maintainability
- Understandability

They are among the most important tools used in software design.

---

# Understanding Relationships Between Classes

Classes rarely exist in isolation.

Software systems often involve relationships between multiple classes.

Common relationships include:

1. Inheritance
2. Association
3. Aggregation

---

# Association

Association represents a relationship between two classes.

A class is associated with another class when objects interact.

---

## Example: Student and Course

```text
Student
    takes
Course
```

---

## Example: Customer and SalesPerson

```text
Customer
    served by
SalesPerson
```

---

### Association Diagram

```text
Customer -------- SalesPerson
```

The relationship indicates interaction rather than ownership.

---

# Multiplicity

Multiplicity describes how many objects participate in a relationship.

Examples:

```text
One Customer
can place

Many Orders
```

Diagram:

```text
Customer 1 ------ * Order
```

Meaning:

```text
One customer

Many orders
```

---

## Another Example

```text
Course 1 ------ * Students
```

Meaning:

```text
One course

Many students
```

Understanding multiplicity helps software engineers design databases and object models correctly.

---

# Aggregation

Aggregation is a special type of association.

Aggregation represents:

```text
Has-A Relationship
```

Examples:

```text
Computer has a Processor

Order has Products

Library has Books
```

---

## Library Example

```text
Library
    has
Books
```

Diagram:

```text
Library
    |
    |
   Books
```

Books belong to the library, but can still exist independently.

---

# Summary of Relationships

| Relationship | Meaning |
|-------------|----------|
| Inheritance | Is-A |
| Association | Uses / Interacts With |
| Aggregation | Has-A |

Understanding these distinctions is critical in designing object-oriented systems.

---

# Case Study: Online Bookstore

Suppose we are designing an online bookstore.

System requirements:

```text
Customers browse products.

Customers place orders.

Products include:

Books
Music CDs
Software
```

---

# Step 1: Identify Classes

Look for nouns in requirements.

Possible classes:

```text
Customer

Order

Book

MusicCD

Software

Address
```

A useful software engineering technique is:

```text
Nouns → Classes

Verbs → Methods
```

Example:

```text
Book
Customer
Order
```

become classes.

Actions:

```text
Browse
Order
Ship
Register
```

become methods.

---

# Step 2: Generalization

Consider:

```text
Book

MusicCD

Software
```

Shared properties:

```text
Title

Publisher

ISBN

Price
```

Create a superclass:

```text
Item
```

---

### Resulting Hierarchy

```text
              Item
                |
      ---------------------
      |         |         |
     Book    MusicCD   Software
```

This removes duplicated attributes.

---

# Introduction to Inheritance

Inheritance allows one class to acquire the properties and behaviours of another class.

Inheritance represents:

```text
IS-A
```

relationships.

Examples:

```text
Manager IS-A Employee

Book IS-An Item

SalesPerson IS-An Employee
```

---

# Inheritance in Python

Python uses parentheses after the subclass name.

General syntax:

```python
class ChildClass(
    ParentClass
):
    pass
```

---

## Example

```python
class Employee:

    pass
```

```python
class Manager(
    Employee
):

    pass
```

Here:

```text
Manager

inherits from

Employee
```

---

# Property Inheritance

Suppose:

```python
class Employee:

    def __init__(
        self,
        name
    ):

        self.name = name
```

Manager automatically receives:

```text
name
```

without redefining it.

---

## Visual Representation

```text
Employee
│
├── name
│
└── get_name()

        ↓

Manager
│
├── inherits name
│
└── inherits get_name()
```

---

# Constructors in Inheritance

Subclasses often add additional data.

Example:

```python
class Employee:

    def __init__(
        self,
        name
    ):

        self.name = name
```

```python
class Manager(
    Employee
):

    def __init__(
        self,
        name,
        allowance
    ):

        super().__init__(name)

        self.allowance = allowance
```

---

# Understanding super()

The function:

```python
super()
```

allows a subclass to access functionality from its parent class.

Example:

```python
super().__init__(name)
```

calls the parent constructor.

This avoids rewriting code.

---

# Why Inheritance Matters

Inheritance improves:

## Reusability

Write common functionality once.

Reuse everywhere.

---

## Maintainability

Fixing a superclass immediately benefits all subclasses.

---

## Scalability

Adding new subclasses becomes easier.

---

# Contract and Implementation

Every class provides:

### Contract

What the class promises to do.

Example:

```python
get_pay()
```

---

### Implementation

How the task is actually performed.

Different subclasses may implement the same contract differently.

---

# Method Overriding

Method overriding allows subclasses to replace a superclass implementation.

---

## Problem Scenario

Suppose:

```python
Employee
```

contains:

```python
get_pay()
```

However:

```text
Managers receive allowance.

SalesPersons receive commission.
```

The same salary calculation no longer works.

---

# Base Implementation

```python
class Employee:

    def get_pay(self):

        return self.salary
```

---

# Overridden Implementation

```python
class SalesPerson(
    Employee
):

    def get_pay(self):

        return (
            self.salary +
            self.commission
        )
```

Now:

```python
get_pay()
```

behaves differently depending on the object.

---

# Visualizing Overriding

```text
Employee
    get_pay()

        ↓

SalesPerson
    get_pay()

        ↓

Different implementation
```

The method name remains identical.

The behaviour changes.

---

# Why Override Methods?

Method overriding becomes necessary when:

```text
Superclass behaviour
does not satisfy
subclass requirements.
```

Benefits:

✅ More flexibility

✅ Better reuse

✅ Cleaner design

✅ Supports polymorphism

---

# Is-A vs Has-A Relationships

One of the most important design decisions in software engineering involves determining relationship types.

---

## Is-A Relationship

Use inheritance.

Example:

```text
Manager IS-An Employee
```

```python
class Manager(
    Employee
)
```

---

## Has-A Relationship

Use aggregation/composition.

Example:

```text
Customer HAS-An Order
```

```python
class Customer:

    self.orders = []
```

---

# Choosing the Correct Relationship

Question:

```text
Can I say:

Manager IS-An Employee?
```

Yes.

Inheritance is appropriate.

---

Question:

```text
Can I say:

Customer IS-An Order?
```

No.

A customer owns orders.

Therefore:

```text
Has-A Relationship
```

should be used instead.

---

# Mini Project: School Management System

Design the following classes:

```text
Person

Student

Teacher

Course

Department
```

Requirements:

1. Identify inheritance relationships.
2. Identify associations.
3. Identify aggregations.
4. Create a UML diagram.
5. Implement the hierarchy using Python.

---

# Common Beginner Mistakes

## Inheriting When a Has-A Relationship Exists

Incorrect:

```python
class Customer(Order)
```

Customer is not an order.

---

## Forgetting super()

Subclasses often forget to initialize parent attributes.

---

## Excessive Inheritance

Not everything should inherit.

Sometimes composition is the better choice.

---

## Breaking the Meaning of IS-A

Always ask:

```text
Does this truly represent
an IS-A relationship?
```

If not, reconsider the design.

---

# Summary

In this tutorial, you learned:

✅ How objects are classified into classes.

✅ The concepts of generalization and specialization.

✅ How class hierarchies are created.

✅ The difference between inheritance, association, and aggregation.

✅ How inheritance works in Python.

✅ The role of constructors in inherited classes.

✅ How method overriding modifies inherited behaviour.

✅ The difference between IS-A and HAS-A relationships.

These concepts form the foundation for advanced object-oriented software design and prepare us for polymorphism, design patterns, and larger software architectures.

---

# Knowledge Check

1. What is classification?
2. What is the difference between generalization and specialization?
3. What is a class hierarchy?
4. What is an association relationship?
5. What is aggregation?
6. What does inheritance provide?
7. What is method overriding?
8. What is the difference between IS-A and HAS-A relationships?
9. When should `super()` be used?
10. Why does inheritance improve maintainability?

---

# Next Tutorial

In **Tutorial 07: Polymorphism and Strings**, we will explore how objects can take different forms through polymorphism and how Python handles text processing using strings.
