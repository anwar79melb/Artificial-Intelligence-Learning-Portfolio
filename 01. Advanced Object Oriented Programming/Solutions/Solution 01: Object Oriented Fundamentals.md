# Solution 01: Object-Oriented Fundamentals

## Overview

This document provides suggested solutions and discussion points for **Exercise 01: Object-Oriented Fundamentals**.

The purpose of these solutions is not only to present answers but also to demonstrate the analytical thinking expected in software engineering and object-oriented design.

---

# Question 1

## Explain the difference between:

```text
Object
Class
Attribute
Method
```

using a real-world example not discussed in the course.

---

# Solution

Consider a **Car Rental System**.

---

## Class

A class is a blueprint used to create objects.

Example:

```text
Car
```

The class defines what information and behaviours every car should have.

---

## Object

An object is a specific instance created from a class.

Examples:

```text
Toyota Corolla

Honda Civic

Tesla Model 3
```

Each vehicle is an object belonging to the class:

```text
Car
```

---

## Attribute

Attributes represent the characteristics or properties of an object.

For a Car object:

```text
Registration Number

Model

Colour

Daily Rental Price
```

Example:

```text
Registration Number = AB1234

Model = Toyota Corolla

Colour = White

Rental Price = $85/day
```

---

## Method

Methods represent actions that an object can perform.

Examples:

```text
RentVehicle()

ReturnVehicle()

DisplayDetails()

CalculateRentalCost()
```

Methods define the behaviour of an object.

---

## Illustration

```text
+----------------------+
|         Car          |
+----------------------+
| registrationNumber   |
| model                |
| colour               |
| rentalPrice          |
+----------------------+
| rentVehicle()        |
| returnVehicle()      |
| displayDetails()     |
+----------------------+
```

---

## Summary Table

| Concept | Description | Example |
|----------|------------|----------|
| Class | Blueprint | Car |
| Object | Instance of a class | Toyota Corolla |
| Attribute | Data describing an object | Colour = White |
| Method | Behaviour of an object | rentVehicle() |

---

# Question 2

## A university intends to develop a software system for managing courses.

Identify:

- Five possible classes
- Three attributes for each class
- Two methods for each class

Present your answer in tabular form.

---

# Solution

## University Course Management System

| Class | Attributes | Methods |
|---------|------------|------------|
| Student | student_id, name, email | enrol(), view_results() |
| Lecturer | lecturer_id, name, office | teach(), grade_assignment() |
| Course | course_code, title, credits | add_student(), assign_lecturer() |
| Assignment | assignment_id, due_date, marks | submit(), calculate_grade() |
| Enrolment | enrolment_id, semester, status | activate(), withdraw() |

---

## UML Representation

```text
+------------------+
|     Student      |
+------------------+
| student_id       |
| name             |
| email            |
+------------------+
| enrol()          |
| view_results()   |
+------------------+
```

---

```text
+------------------+
|      Course      |
+------------------+
| course_code      |
| title            |
| credits          |
+------------------+
| add_student()    |
| assign_lecturer()|
+------------------+
```

---

## Discussion

A software engineer typically begins by:

1. Identifying nouns within system requirements.
2. Converting nouns into classes.
3. Converting actions into methods.
4. Defining relationships among classes.

This process is a common object-oriented analysis technique.

---

# Question 3

## Discuss the advantages and disadvantages of Object-Oriented Programming compared to procedural programming.

Your answer should include:

```text
Reusability

Modularity

Maintainability

Complexity
```

---

# Solution

Object-Oriented Programming (OOP) organizes software around objects, while procedural programming focuses on functions and procedures.

Both approaches have strengths and weaknesses.

---

## Advantages of OOP

### 1. Reusability

OOP promotes code reuse through:

```text
Inheritance

Composition

Polymorphism
```

For example:

```text
Employee

Manager

SalesPerson

Secretary
```

can share common functionality through inheritance.

As a result:

```text
Less duplicated code
```

is required.

---

### 2. Modularity

Large applications can be divided into smaller components.

Example:

```text
Book Class

Member Class

Loan Class

Library Class
```

Each class manages a specific responsibility.

Benefits:

```text
Easier troubleshooting

Simpler development

Clearer structure
```

---

### 3. Maintainability

Changes can often be made within a single class without affecting the entire application.

Example:

```text
Updating Book
```

normally affects only book-related functionality.

This reduces the likelihood of introducing errors elsewhere.

---

### 4. Scalability

Object-oriented systems generally grow more effectively as requirements increase.

Additional classes can be introduced with minimal impact on existing software.

---

## Disadvantages of OOP

### 1. Increased Complexity

Small programs often become more complicated when OOP is introduced.

For example:

```text
Simple Calculator
```

may be easier to implement procedurally.

---

### 2. Additional Design Effort

Developers must spend time designing:

```text
Classes

Relationships

Inheritance Hierarchies
```

before implementation.

---

### 3. Higher Memory Usage

Objects often require more memory than simple procedural data structures.

This is usually insignificant for modern systems but may matter in embedded environments.

---

### 4. Learning Curve

Concepts such as:

```text
Inheritance

Polymorphism

Encapsulation

Design Patterns
```

require time and practice to master.

---

## Comparison Table

| Aspect | Procedural Programming | Object-Oriented Programming |
|----------|----------------------|---------------------------|
| Focus | Functions | Objects |
| Reusability | Limited | High |
| Modularity | Moderate | Strong |
| Maintainability | Moderate | High |
| Scalability | Moderate | High |
| Learning Difficulty | Easier | Harder |
| Design Effort | Lower | Higher |

---

## Conclusion

For small scripts, procedural programming may be sufficient.

For medium and large applications, object-oriented programming offers significant advantages through:

```text
Reusability

Modularity

Maintainability

Scalability
```

which is why it remains one of the most widely used software development paradigms.

---

# Question 4

## Using your own example, explain:

```text
Encapsulation

Inheritance

Polymorphism
```

---

# Solution

Consider a **Hospital Management System**.

---

# Encapsulation

Encapsulation is the process of hiding implementation details and exposing only the necessary functionality.

---

## Example

Class:

```text
Patient
```

Attributes:

```text
patientID

name

medicalHistory
```

Methods:

```text
getMedicalHistory()

updateMedicalHistory()
```

Patients should not access internal database details directly.

Instead, they interact through controlled methods.

---

## Illustration

```text
          User

            |

            V

+----------------------+
|       Patient        |
+----------------------+

Hidden Data

medicalHistory

insuranceDetails

internalNotes

+----------------------+

Public Methods

getHistory()

updateHistory()
```

---

# Inheritance

Inheritance allows one class to acquire attributes and methods from another class.

---

## Example

Superclass:

```text
Employee
```

Subclasses:

```text
Doctor

Nurse

Receptionist
```

---

## UML Diagram

```text
            Employee
                |
      -------------------
      |        |        |
      |        |        |
    Doctor   Nurse  Receptionist
```

Shared properties:

```text
employeeID

name

salary
```

Need only be implemented once.

---

# Polymorphism

Polymorphism allows different subclasses to respond differently to the same method call.

---

## Example

Every hospital employee may have:

```python
perform_duty()
```

---

Doctor:

```python
perform_duty()

→ Diagnose Patient
```

---

Nurse:

```python
perform_duty()

→ Assist Treatment
```

---

Receptionist:

```python
perform_duty()

→ Register Patient
```

---

## Illustration

```text
perform_duty()

        |
        |

 -------------------------
 |           |           |

Doctor      Nurse    Receptionist

   |           |           |

Diagnose    Assist     Register
```

---

## Benefits

Encapsulation provides:

```text
Security

Controlled Access
```

Inheritance provides:

```text
Code Reuse

Consistency
```

Polymorphism provides:

```text
Flexibility

Extensibility

Maintainability
```

Together, these three principles form the foundation of Object-Oriented Programming.

---

# Self-Evaluation Checklist

After completing Exercise 01, you should be able to:

✅ Distinguish between classes and objects.

✅ Identify attributes and methods.

✅ Analyze a real-world problem and identify classes.

✅ Explain the benefits of object-oriented programming.

✅ Describe encapsulation, inheritance, and polymorphism.

✅ Construct basic UML class diagrams.

✅ Apply object-oriented thinking to software design problems.
