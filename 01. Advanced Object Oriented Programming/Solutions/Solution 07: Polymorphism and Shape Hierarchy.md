# Solution 07: Polymorphism and Shape Hierarchy

## Overview

This document provides suggested solutions for **Exercise 07: Polymorphism**.

This exercise focuses on one of the most important concepts in Object-Oriented Programming:

```text
Polymorphism
```

Throughout this solution, we will explore how inheritance and method overriding work together to create flexible and maintainable software designs.

---

# Problem Statement

Design the following class hierarchy:

```text
Shape

Rectangle

Circle

Triangle

Square
```

Requirements:

- Every subclass must implement `get_area()`
- Create multiple shape objects
- Store objects in a list
- Use polymorphism to display all areas
- Do not use `if` or `elif` statements for area calculations

---

# Understanding the Design

Before writing code, let's analyze the problem.

All shapes share a common concept:

```text
Every shape has an area.
```

Therefore:

```text
Shape
```

should become the superclass.

Each specific shape:

```text
Rectangle

Circle

Triangle

Square
```

will become a subclass.

---

# UML Diagram

```text
                    Shape
                  +---------+
                  |get_area()|
                  +---------+
                       |
      -------------------------------------
      |          |           |           |
      |          |           |           |
 Rectangle    Circle     Triangle     Square
```

Each subclass provides its own implementation of:

```python
get_area()
```

---

# Step 1: Create the Shape Superclass

The purpose of the Shape class is to define a common interface.

---

## Implementation

```python
class Shape:

    def get_area(self):

        pass
```

---

## Discussion

This method acts as a contract.

Every subclass promises to provide:

```python
get_area()
```

---

# Step 2: Implement Rectangle

## Area Formula

```text
Area = Length × Width
```

---

## Implementation

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

# Step 3: Implement Circle

## Area Formula

```text
Area = πr²
```

---

## Implementation

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

# Step 4: Implement Triangle

## Area Formula

```text
Area =
½ × Base × Height
```

---

## Implementation

```python
class Triangle(Shape):

    def __init__(
        self,
        base,
        height
    ):

        self.base = base
        self.height = height

    def get_area(self):

        return (
            0.5 *
            self.base *
            self.height
        )
```

---

# Step 5: Implement Square

## Area Formula

```text
Area = Side²
```

---

## Implementation

```python
class Square(Shape):

    def __init__(
        self,
        side
    ):

        self.side = side

    def get_area(self):

        return self.side ** 2
```

---

# Complete Inheritance Hierarchy

```text
Shape
│
├── Rectangle
├── Circle
├── Triangle
└── Square
```

Each subclass inherits from:

```text
Shape
```

while providing its own area calculation.

---

# Creating Shape Objects

Now create multiple objects.

```python
rectangle = Rectangle(
    10,
    5
)

circle = Circle(
    3
)

triangle = Triangle(
    8,
    4
)

square = Square(
    6
)
```

---

# Storing Objects in a List

One of the biggest advantages of polymorphism is that different object types can be treated uniformly.

```python
shapes = [

    rectangle,

    circle,

    triangle,

    square
]
```

Notice:

```text
Different Classes

Stored In One Collection
```

---

# Displaying Areas Using Polymorphism

## Implementation

```python
for shape in shapes:

    print(
        shape.get_area()
    )
```

---

# Sample Output

```text
50

28.274333882308138

16.0

36
```

---

# Why This Is Polymorphism

Consider:

```python
shape.get_area()
```

The same statement executes for:

```text
Rectangle

Circle

Triangle

Square
```

However, each object responds differently.

---

## What Happens Internally

First iteration:

```python
Rectangle.get_area()
```

Second iteration:

```python
Circle.get_area()
```

Third iteration:

```python
Triangle.get_area()
```

Fourth iteration:

```python
Square.get_area()
```

Same method name.

Different implementations.

This is polymorphism.

---

# Improved Output

We may want more descriptive output.

---

## Solution

```python
for shape in shapes:

    print(
        type(shape).__name__,
        "Area =",
        shape.get_area()
    )
```

---

## Example Output

```text
Rectangle Area = 50

Circle Area = 28.27

Triangle Area = 16.0

Square Area = 36
```

---

# Why We Avoid if Statements

The exercise specifically states:

```text
Do not use if or elif.
```

Let's see why.

---

## Poor Design

```python
if shape_type == "Rectangle":

    area = length * width

elif shape_type == "Circle":

    area = math.pi * radius ** 2

elif shape_type == "Triangle":

    area = 0.5 * base * height
```

Problems:

```text
Large Code Blocks

Difficult Maintenance

Poor Scalability
```

Every time a new shape is added:

```text
Modify Existing Code
```

This violates good object-oriented design principles.

---

# Polymorphic Solution

Instead:

```python
shape.get_area()
```

The object decides how to compute the result.

Benefits:

```text
Cleaner

More Flexible

More Maintainable
```

---

# Practical Benefits of Polymorphism

Suppose a future requirement introduces:

```text
Pentagon

Hexagon

Ellipse
```

Without polymorphism:

```text
More if statements
```

must be added.

---

With polymorphism:

Simply create:

```python
class Pentagon(
    Shape
)
```

and implement:

```python
get_area()
```

The rest of the program remains unchanged.

This is one of the greatest strengths of object-oriented software design.

---

# Reflection Question

## Why Is Polymorphism More Maintainable?

### Without Polymorphism

```text
New Shape

↓

Modify Existing Code
```

Every enhancement risks introducing bugs.

---

### With Polymorphism

```text
New Shape

↓

Create New Class
```

Existing code remains untouched.

This supports:

```text
Reusability

Extensibility

Maintainability
```

---

# Advanced Extension

## Add a Total Area Calculator

Suppose we want the total area of all shapes.

---

### Solution

```python
total_area = 0

for shape in shapes:

    total_area += (
        shape.get_area()
    )

print(
    "Total Area:",
    total_area
)
```

---

## Sample Output

```text
Total Area: 130.27433388230813
```

Notice:

```python
get_area()
```

is still called polymorphically.

The loop neither knows nor cares which type of shape it is processing.

---

# Complete Program

```python
import math

class Shape:

    def get_area(self):

        pass


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


class Triangle(Shape):

    def __init__(
        self,
        base,
        height
    ):

        self.base = base
        self.height = height

    def get_area(self):

        return (
            0.5 *
            self.base *
            self.height
        )


class Square(Shape):

    def __init__(
        self,
        side
    ):

        self.side = side

    def get_area(self):

        return self.side ** 2


shapes = [

    Rectangle(10, 5),

    Circle(3),

    Triangle(8, 4),

    Square(6)
]

for shape in shapes:

    print(
        type(shape).__name__,
        "Area =",
        round(
            shape.get_area(),
            2
        )
    )
```

---

# Expected Output

```text
Rectangle Area = 50

Circle Area = 28.27

Triangle Area = 16.0

Square Area = 36
```

---

# Key Learning Outcomes

After completing this exercise, students should be able to:

✅ Design superclass-subclass hierarchies.

✅ Apply inheritance.

✅ Override methods.

✅ Understand polymorphism.

✅ Store different object types in a single collection.

✅ Eliminate unnecessary conditional statements.

✅ Design extensible object-oriented systems.

---

# Key Takeaway

A simple rule to remember:

```text
Inheritance provides the structure.

Method overriding provides the variation.

Polymorphism provides the flexibility.
```

Together, these three concepts form the core of advanced object-oriented design and are heavily used in professional software development.
