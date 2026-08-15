# Advanced Object-Oriented Programming
# Exercises and Assessment Activities

## Overview

The purpose of these exercises is to assess both theoretical understanding and practical programming skills developed throughout the course.

The activities are designed using a progressive structure:

```text
Level 1 → Knowledge Recall

Level 2 → Practical Application

Level 3 → Problem Solving

Level 4 → Object-Oriented Design

Level 5 → Software Engineering Challenge
```

These exercises are intentionally more challenging than simple classroom examples and are designed to demonstrate academic understanding and practical programming competency.

---

# Part A: Conceptual Questions

## Exercise 1: Object-Oriented Fundamentals

### Question 1

Explain the difference between:

```text
Object
Class
Attribute
Method
```

using a real-world example not discussed in this course.

---

### Question 2

A university intends to develop a software system for managing courses.

Identify:

- Five possible classes
- Three attributes for each class
- Two methods for each class

Present your answer in tabular form.

---

### Question 3

Discuss the advantages and disadvantages of Object-Oriented Programming compared to procedural programming.

Your answer should include:

```text
Reusability

Modularity

Maintainability

Complexity
```

---

### Question 4

Using your own example, explain the concepts of:

```text
Encapsulation

Inheritance

Polymorphism
```

---

# Part B: Python Fundamentals

## Exercise 2: Variables and Control Structures

### Question 1

Write a Python program that accepts:

```text
Student Name
Assignment Mark
Exam Mark
```

The program should:

1. Calculate the final score.
2. Determine the grade according to:

```text
80 – 100 → HD

70 – 79  → D

60 – 69  → C

50 – 59  → P

0 – 49   → F
```

3. Display the result in a formatted report.

---

### Question 2

Write a Python program that prints the following pattern:

```text
*
**
***
****
*****
```

using a loop.

---

### Question 3

A university wants to identify prime numbers between 1 and 100.

Develop a program that displays all prime numbers within this range.

---

# Part C: Functions

## Exercise 3: Functional Programming

### Question 1

Write a function named:

```python
calculate_tax()
```

that accepts:

```text
Salary
Tax Rate
```

and returns the tax amount.

---

### Question 2

Create a function named:

```python
is_palindrome()
```

which determines whether a word reads the same forward and backward.

Examples:

```text
madam

level

racecar
```

---

### Question 3

Implement a recursive function that calculates:

```text
Fibonacci Numbers
```

Example:

```text
0 1 1 2 3 5 8 ...
```

---

# Part D: Collections

## Exercise 4: Lists, Tuples and Dictionaries

### Question 1

Create a list containing:

```text
20 random integers
```

Then:

1. Display the list.
2. Display the largest value.
3. Display the smallest value.
4. Display the average value.
5. Sort the list.

---

### Question 2

Create a tuple containing:

```text
Days of the Week
```

Attempt to modify one of the elements.

Explain the result.

---

### Question 3

Create a dictionary representing a student record.

Required information:

```text
Student ID

Name

Course

Email

GPA
```

Implement functionality to:

```text
Add Data

Update Data

Display Data

Delete Data
```

---

# Part E: Classes and Objects

## Exercise 5: Object Modelling

### Question 1

Design a class called:

```text
Book
```

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

Develop the complete Python implementation.

---

### Question 2

Design a UML Class Diagram for:

```text
Student
```

Include:

```text
Attributes

Methods

Constructor
```

---

### Question 3

Explain the role of the constructor:

```python
__init__()
```

Why is it useful in object-oriented software design?

---

# Part F: Inheritance and Relationships

## Exercise 6: Inheritance Design

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

Additional details:

```text
Manager → Allowance

SalesPerson → Commission

Secretary → Department
```

---

### Tasks

1. Design a UML hierarchy.
2. Implement an Employee superclass.
3. Implement all subclasses.
4. Demonstrate inheritance.
5. Demonstrate constructor reuse using:

```python
super()
```

---

### Challenge Question

Explain why the following relationship is incorrect:

```python
class Customer(Order):
```

Identify the correct relationship.

---

# Part G: Polymorphism

## Exercise 7: Shape Hierarchy

Design the following hierarchy:

```text
Shape

Rectangle

Circle

Triangle

Square
```

---

### Requirements

Every subclass must implement:

```python
get_area()
```

---

### Tasks

1. Create multiple shape objects.
2. Store them in a list.
3. Use polymorphism to display all areas.
4. Do not use:

```python
if

elif
```

statements for area calculations.

---

### Reflection

Explain why polymorphism is a more maintainable solution than using multiple conditional statements.

---

# Part H: String Processing

## Exercise 8: Text Analytics

Create a program that accepts a paragraph from the user and reports:

```text
Total Characters

Total Words

Total Sentences

Longest Word

Shortest Word
```

---

### Extension Activity

Display the frequency of every word.

Example:

```text
Python → 4

Programming → 2

AI → 3
```

---

### Advanced Challenge

Determine:

```text
Most Frequently Used Word
```

without using external libraries.

---

# Part I: Data Structures

## Exercise 9: Stacks and Queues

### Question 1

Implement a Stack class.

Required methods:

```python
push()

pop()

top()

is_empty()
```

---

### Question 2

Create a browser history simulator.

Functions:

```text
Visit Page

Back

Display Current Page
```

Use a Stack.

---

### Question 3

Implement a Queue class.

Required methods:

```python
enqueue()

dequeue()

first()

is_empty()
```

---

### Question 4

Design a Customer Service Queue System.

Functions:

```text
Add Customer

Serve Customer

Display Waiting Customers
```

---

### Reflection

Compare:

```text
Stack

Queue
```

and explain when each should be used.

---

# Part J: Design Patterns

## Exercise 10: Software Design Patterns

### Question 1

Research and explain:

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

### Question 2

Develop a Singleton class named:

```text
ConfigurationManager
```

Only one configuration object should exist.

---

### Question 3

Provide a real-world example where the Adapter Pattern would improve software design.

---

# Part K: File Operations

## Exercise 11: File Processing

Create a file named:

```text
marks.txt
```

containing:

```text
78
90
82
66
59
72
85
```

---

### Tasks

Write a Python program that:

1. Reads the file.
2. Calculates:
   - Average
   - Highest Mark
   - Lowest Mark
3. Writes the results to:

```text
report.txt
```

---

### Extension

Display the number of:

```text
HD

D

C

P

F
```

grades found in the file.

---

# Part L: Serialization

## Exercise 12: Persistent Student Records

Design a class:

```text
Student
```

Attributes:

```text
Student ID

Name

Course

GPA
```

---

### Program Requirements

1. Create student objects.
2. Store students in a list.
3. Serialize the list into:

```text
students.dat
```

4. Deserialize the file.
5. Display all student information.

---

### Challenge

Calculate:

```text
Highest GPA

Lowest GPA

Average GPA
```

after deserialization.

---

# Part M: Concurrency

## Exercise 13: Multi-Threaded Applications

### Task 1

Create three threads.

Each thread should:

```text
Display Numbers 1-10
```

along with the thread name.

---

### Task 2

Measure the execution time using:

```python
time.time()
```

---

### Task 3

Explain the purpose of:

```python
join()
```

in your implementation.

---

# Advanced Challenge

Develop a program that:

1. Accepts a list of URLs.
2. Creates one thread per URL.
3. Simulates downloading data.
4. Records execution time.

Compare:

```text
Sequential Execution

Threaded Execution
```

Discuss the results.

---

# Major Capstone Assessment

## Integrated Library Management System

### Scenario

A local council wishes to automate its library operations.

Develop a complete object-oriented system capable of managing:

```text
Books

Members

Loans

Reservations
```

---

## Functional Requirements

### User Management

```text
Add Member

Update Member

Search Member
```

---

### Book Management

```text
Add Book

Update Book

Search Book

Delete Book
```

---

### Borrowing System

```text
Borrow Book

Return Book

Calculate Late Returns
```

---

### Reservation Queue

Implement reservation waiting lists using:

```text
Queue
```

---

### Persistence

Use:

```text
Serialization
```

to save all records.

---

### Reporting

Produce:

```text
Most Borrowed Books

Active Members

Overdue Loans
```

---

## Assessment Criteria

| Component | Weight |
|------------|---------|
| Program Design | 15% |
| OOP Principles | 20% |
| Inheritance & Polymorphism | 15% |
| Data Structures | 10% |
| Serialization | 10% |
| File Operations | 10% |
| Concurrency | 10% |
| Code Quality & Documentation | 10% |

---

# Final Reflection Questions

1. What was the most challenging concept in this course and why?
2. How does Object-Oriented Programming improve software maintainability?
3. When would you choose a Queue over a Stack?
4. What advantages does serialization provide compared to plain text storage?
5. When should multiprocessing be preferred over multithreading?
6. Which concepts from this course are most relevant to Artificial Intelligence applications?
7. How would you improve your capstone project if given additional development time?

---

# Recommended Submission Structure

```text
Advanced-OOP-Exercises/
│
├── Exercise01_OOP_Fundamentals/
├── Exercise02_Python_Basics/
├── Exercise03_Functions/
├── Exercise04_Collections/
├── Exercise05_Classes/
├── Exercise06_Inheritance/
├── Exercise07_Polymorphism/
├── Exercise08_Strings/
├── Exercise09_DataStructures/
├── Exercise10_DesignPatterns/
├── Exercise11_FileOperations/
├── Exercise12_Serialization/
├── Exercise13_Concurrency/
└── Capstone_Project/
```

These exercises move beyond syntax memorization and assess understanding, design ability, problem-solving skills, and software engineering competency, making them suitable for an academic course, portfolio repository, or self-assessment framework.
