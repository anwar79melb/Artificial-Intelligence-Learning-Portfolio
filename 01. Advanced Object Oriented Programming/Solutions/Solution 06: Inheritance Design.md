# Solution 06: Inheritance Design

## Overview

This document provides suggested solutions for **Exercise 06: Inheritance and Relationships**.

This exercise focuses on:

- Generalization
- Specialization
- Inheritance
- Constructors
- Method Reuse
- Object-Oriented Analysis
- UML Design

Inheritance is one of the most powerful features of Object-Oriented Programming because it allows software developers to eliminate duplicated code and model real-world relationships more naturally.

---

# Problem Statement

A company employs:

```text
Manager

SalesPerson

Secretary
```

All employees share:

```text
Employee Number

Name

Salary
```

Additional information:

```text
Manager
    → Allowance

SalesPerson
    → Commission

Secretary
    → Department
```

---

# Task 1: Design a UML Hierarchy

## Step 1: Identify Common Attributes

All employee types have:

```text
Employee Number

Name

Salary
```

These attributes should be placed in a superclass.

---

## Step 2: Identify Specialized Attributes

Manager:

```text
Allowance
```

SalesPerson:

```text
Commission
```

Secretary:

```text
Department
```

These should be placed inside their respective subclasses.

---

## UML Class Diagram

```text
                    Employee
          +-------------------------+
          | employee_number         |
          | name                    |
          | salary                  |
          +-------------------------+
          | display_details()       |
          | get_pay()               |
          +-------------------------+
                     /|\
                      |
      ---------------------------------------
      |                  |                 |
      |                  |                 |
      |                  |                 |
  Manager         SalesPerson       Secretary

+------------+    +-------------+   +-------------+
| allowance  |    | commission  |   | department  |
+------------+    +-------------+   +-------------+
| get_pay()  |    | get_pay()   |   | get_pay()   |
+------------+    +-------------+   +-------------+
```

---

# Discussion

The hierarchy reflects:

```text
Manager IS-An Employee

SalesPerson IS-An Employee

Secretary IS-An Employee
```

This is a classic example of inheritance.

---

# Task 2: Implement an Employee Superclass

## Design Analysis

The superclass should contain:

### Attributes

```text
Employee Number

Name

Salary
```

### Behaviours

```text
Display Details

Calculate Salary
```

---

## Employee Class

```python
class Employee:

    def __init__(
        self,
        employee_number,
        name,
        salary
    ):

        self.employee_number = employee_number
        self.name = name
        self.salary = salary

    def display_details(self):

        print("\nEMPLOYEE DETAILS")
        print("--------------------")
        print(
            f"Employee Number: "
            f"{self.employee_number}"
        )
        print(f"Name: {self.name}")
        print(f"Salary: ${self.salary}")

    def get_pay(self):

        return self.salary
```

---

# Discussion

The Employee class captures common functionality shared by all employee types.

This prevents duplication throughout the system.

---

# Task 3: Implement All Subclasses

---

# Manager Class

Managers receive an additional allowance.

---

## UML

```text
Manager

Allowance
```

---

## Implementation

```python
class Manager(Employee):

    def __init__(
        self,
        employee_number,
        name,
        salary,
        allowance
    ):

        super().__init__(
            employee_number,
            name,
            salary
        )

        self.allowance = allowance

    def get_pay(self):

        return (
            self.salary +
            self.allowance
        )
```

---

# SalesPerson Class

Salespersons receive commission.

---

## UML

```text
SalesPerson

Commission
```

---

## Implementation

```python
class SalesPerson(Employee):

    def __init__(
        self,
        employee_number,
        name,
        salary,
        commission
    ):

        super().__init__(
            employee_number,
            name,
            salary
        )

        self.commission = commission

    def get_pay(self):

        return (
            self.salary +
            self.commission
        )
```

---

# Secretary Class

Secretaries belong to departments.

---

## UML

```text
Secretary

Department
```

---

## Implementation

```python
class Secretary(Employee):

    def __init__(
        self,
        employee_number,
        name,
        salary,
        department
    ):

        super().__init__(
            employee_number,
            name,
            salary
        )

        self.department = department
```

In this case:

```python
get_pay()
```

does not require overriding because salary alone represents payment.

---

# Task 4: Demonstrate Inheritance

## Creating Objects

```python
manager = Manager(

    "E001",

    "John Smith",

    90000,

    10000
)

salesperson = SalesPerson(

    "E002",

    "Sarah Lee",

    60000,

    15000
)

secretary = Secretary(

    "E003",

    "Emma Brown",

    50000,

    "Human Resources"
)
```

---

## Display Details

```python
manager.display_details()

salesperson.display_details()

secretary.display_details()
```

Output:

```text
EMPLOYEE DETAILS
--------------------
Employee Number: E001
Name: John Smith
Salary: $90000
```

---

## Discussion

Notice:

```python
display_details()
```

was inherited directly from:

```python
Employee
```

No duplication was required.

This is one of the major benefits of inheritance.

---

# Task 5: Demonstrate Constructor Reuse Using super()

---

## Why super() Is Needed

Suppose we create a Manager:

```python
manager = Manager(
    "E001",
    "John Smith",
    90000,
    10000
)
```

The object must still initialize:

```text
employee_number

name

salary
```

which belong to Employee.

---

## Constructor Chain

```text
Manager Constructor

        |
        v

super().__init__()

        |
        v

Employee Constructor

        |
        v

Initialize Common Attributes
```

---

# Example

```python
class Manager(Employee):

    def __init__(
        self,
        employee_number,
        name,
        salary,
        allowance
    ):

        super().__init__(
            employee_number,
            name,
            salary
        )

        self.allowance = allowance
```

---

# Why This Is Better

Without `super()`:

```python
self.employee_number =
employee_number

self.name = name

self.salary = salary
```

would have to be rewritten inside:

```text
Manager

SalesPerson

Secretary
```

This produces duplication.

With `super()`:

```text
Single Source

Better Maintenance

Cleaner Design
```

---

# Demonstrating Polymorphism

Although this exercise focuses on inheritance, it naturally introduces polymorphism.

Consider:

```python
employees = [

    manager,

    salesperson,

    secretary
]

for employee in employees:

    print(employee.get_pay())
```

Output:

```text
100000

75000

50000
```

Notice:

```python
employee.get_pay()
```

is identical.

However:

```text
Manager

SalesPerson

Secretary
```

produce different results.

This is polymorphism in action.

---

# Challenge Question

## Explain Why This Relationship Is Incorrect

```python
class Customer(Order):
```

---

# Analysis

Inheritance represents:

```text
IS-A Relationship
```

The question becomes:

```text
Is a Customer an Order?
```

The answer is:

```text
No
```

A customer is a person or business entity.

An order is a transaction.

They are entirely different concepts.

Therefore:

```python
class Customer(Order)
```

is incorrect.

---

# Correct Relationship

A customer may create multiple orders.

Therefore:

```text
Customer HAS Orders
```

This is a:

```text
Has-A Relationship
```

not an:

```text
Is-A Relationship
```

---

## UML Relationship

```text
Customer

     1
     |
     |
     |
     *
Order
```

Meaning:

```text
One Customer

Can Have

Many Orders
```

---

## Python Implementation

```python
class Customer:

    def __init__(
        self,
        customer_id,
        name
    ):

        self.customer_id = customer_id

        self.name = name

        self.orders = []
```

This accurately models reality.

---

# Relationship Summary

| Relationship | Example |
|-------------|----------|
| IS-A | Manager IS-An Employee |
| IS-A | SalesPerson IS-An Employee |
| HAS-A | Customer HAS Orders |
| HAS-A | Library HAS Books |
| HAS-A | University HAS Students |

---

# Reflection

This exercise demonstrates several important software engineering concepts.

---

## Generalization

Shared features moved to:

```text
Employee
```

---

## Specialization

Additional features added to:

```text
Manager

SalesPerson

Secretary
```

---

## Constructor Reuse

Achieved through:

```python
super()
```

---

## Code Reuse

Shared methods inherited from:

```text
Employee
```

---

## Maintainability

Common functionality exists in one location only.

---

# Self-Evaluation Checklist

After completing Exercise 06, you should be able to:

✅ Design class hierarchies.

✅ Identify superclass and subclass relationships.

✅ Implement inheritance in Python.

✅ Use `super()` correctly.

✅ Identify IS-A relationships.

✅ Identify HAS-A relationships.

✅ Create UML class hierarchies.

✅ Understand method overriding.

✅ Understand code reuse through inheritance.

✅ Explain why inheritance improves maintainability.

---

# Key Takeaways

Inheritance allows developers to create structured and reusable software systems.

The main lessons from this exercise are:

```text
Generalization

Specialization

Inheritance

Method Reuse

Constructor Reuse

IS-A Relationships

HAS-A Relationships
```

These concepts provide the foundation for the next major topic:

```text
Polymorphism
```

where different subclasses can respond differently to the same method call while sharing a common interface.
