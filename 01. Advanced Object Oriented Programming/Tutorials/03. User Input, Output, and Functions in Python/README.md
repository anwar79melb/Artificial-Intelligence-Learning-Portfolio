# Tutorial 03: User Input, Output, and Functions in Python

## Overview

Programming becomes truly useful when applications can interact with users and perform reusable tasks efficiently.

So far, we have learned how to:

- Store information using variables.
- Manipulate data with operators.
- Make decisions using conditions.
- Repeat operations with loops.

However, most real-world programs also need to:

- Receive information from users.
- Display meaningful results.
- Organize logic into reusable components.

This tutorial introduces three fundamental concepts:

- Standard Input
- Standard Output
- Functions

These concepts form the foundation of interactive applications and are heavily used in object-oriented programming, machine learning, web development, and software engineering.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Receive input from users.
- Convert user input into appropriate data types.
- Display formatted output.
- Create reusable functions.
- Pass information to functions using parameters.
- Return values from functions.
- Understand recursive functions.
- Apply modular programming principles.

---

# Why Input and Output Matter

Imagine building a Library Management System.

Without user input:

```text
The program cannot accept book loans.
The program cannot register new members.
The program cannot search for books.
```

Without output:

```text
Users cannot see search results.
Users cannot view available books.
Users cannot receive confirmations.
```

Input and output allow communication between a user and a program.

---

# Understanding Standard Input and Output

A program and a user communicate through two channels:

```text
User  -------->  Program
       Input

User  <--------  Program
       Output
```

The user provides data.

The program processes the data.

The program returns useful information.

---

# Standard Input

Python uses the built-in `input()` function to receive data from users.

General syntax:

```python
input("Prompt Message")
```

Example:

```python
name = input("Enter your name: ")
```

Output:

```text
Enter your name:
```

Suppose the user enters:

```text
Alex
```

The value is stored inside the variable:

```python
name
```

---

# First Interactive Program

```python
name = input("Enter your name: ")

print("Hello", name)
```

Example execution:

```text
Enter your name: Alex

Hello Alex
```

---

# Important: Input Always Returns a String

Many beginners assume Python automatically knows what data type the user enters.

It does not.

Consider:

```python
age = input("Enter your age: ")
```

If the user enters:

```text
25
```

Python stores:

```python
"25"
```

not

```python
25
```

The value is stored as a string.

---

# Checking the Data Type

```python
age = input("Enter age: ")

print(type(age))
```

Output:

```text
<class 'str'>
```

Regardless of what the user types, `input()` returns text.

---

# Why Type Conversion Is Necessary

Suppose we wish to calculate the user's age next year.

Incorrect:

```python
age = input("Enter age: ")

next_year = age + 1
```

Result:

```text
TypeError
```

Why?

Because Python is trying to add:

```text
String + Integer
```

which is invalid.

---

# Type Casting

Type casting converts one data type into another.

Python provides several conversion functions.

| Function | Purpose |
|-----------|----------|
| int() | Convert to integer |
| float() | Convert to decimal |
| str() | Convert to string |
| bool() | Convert to Boolean |

---

# Converting to Integer

```python
age = int(input("Enter age: "))

next_year = age + 1

print(next_year)
```

Example:

```text
Enter age: 25

26
```

---

# Converting to Float

```python
price = float(
    input("Enter price: ")
)

tax = price * 0.1

print(tax)
```

Example:

```text
Enter price: 100

10.0
```

---

# Invalid Conversions

Not every conversion works.

Example:

```python
age = int(
    input("Enter age: ")
)
```

User enters:

```text
twenty
```

Result:

```text
ValueError
```

Python cannot convert non-numeric text into an integer.

---

# Understanding Boolean Conversion

```python
print(bool(1))
```

Output:

```text
True
```

```python
print(bool(0))
```

Output:

```text
False
```

Boolean conversion is commonly used when evaluating conditions.

---

# Receiving Multiple Inputs

Sometimes we need more than one value.

A simple approach:

```python
name = input("Enter name: ")

age = input("Enter age: ")
```

This works but requires multiple lines.

---

# Multiple Inputs on One Line

Python's `split()` method makes this easier.

```python
first_name, last_name = input(
    "Enter first and last name: "
).split()
```

Example:

```text
Enter first and last name:

John Smith
```

Result:

```python
first_name = "John"

last_name = "Smith"
```

---

# Working with Numeric Inputs

Remember:

```python
split()
```

still returns strings.

Example:

```python
a, b = input(
    "Enter two numbers: "
).split()

a = int(a)
b = int(b)
```

---

# A Better Approach

```python
a, b = map(
    int,
    input(
        "Enter two numbers: "
    ).split()
)
```

Example:

```text
10 20
```

Result:

```python
a = 10

b = 20
```

---

# Custom Separators

By default, `split()` uses spaces.

Example:

```python
data = input().split(",")
```

Input:

```text
10,20,30
```

Output:

```python
['10', '20', '30']
```

Other separators are possible:

```python
:
;
#
@
|
```

---

# Standard Output

Output allows programs to display information.

Python uses:

```python
print()
```

---

# Basic Output

```python
print("Hello World")
```

Output:

```text
Hello World
```

---

# Printing Variables

```python
name = "Alex"

print(name)
```

Output:

```text
Alex
```

---

# Printing Multiple Values

```python
name = "Alex"

age = 25

print(name, age)
```

Output:

```text
Alex 25
```

---

# String Formatting

Formatting creates cleaner output.

Consider:

```python
name = "Alex"
age = 25
```

---

## Using f-Strings

Recommended modern approach:

```python
print(
    f"{name} is {age} years old."
)
```

Output:

```text
Alex is 25 years old.
```

---

## Formatting Floating Point Values

```python
price = 19.99999

print(f"{price:.2f}")
```

Output:

```text
20.00
```

---

# Practical Example

```python
name = input("Name: ")

salary = float(
    input("Salary: ")
)

print(
    f"{name} earns ${salary:.2f}"
)
```

Example output:

```text
Alex earns $3500.00
```

---

# What Are Functions?

As programs grow larger, repeating code becomes a problem.

Consider:

```python
Calculate student's grade
Calculate employee's bonus
Calculate product discount
```

Each task may require complex logic.

Rather than rewriting code repeatedly, we place the logic inside functions.

A function is simply a reusable block of code designed to perform a specific task.

---

# Why Use Functions?

Functions provide several advantages:

## Reusability

Write once.

Use many times.

---

## Maintainability

Updates only need to be made in one location.

---

## Readability

Programs become easier to understand.

---

## Modularity

Large problems become smaller manageable tasks.

---

# Function Anatomy

General syntax:

```python
def function_name():

    statements
```

Example:

```python
def greet():

    print("Hello")
```

---

# Calling a Function

Defining a function does not execute it.

We must call it.

```python
greet()
```

Output:

```text
Hello
```

---

# Functions with Parameters

Parameters allow functions to receive data.

Example:

```python
def greet(name):

    print(
        f"Hello {name}"
    )
```

Call:

```python
greet("Alex")
```

Output:

```text
Hello Alex
```

---

# Multiple Parameters

```python
def add(a, b):

    print(a + b)
```

Call:

```python
add(10, 20)
```

Output:

```text
30
```

---

# Returning Values

Many functions produce results.

Example:

```python
def square(number):

    return number * number
```

Usage:

```python
result = square(5)

print(result)
```

Output:

```text
25
```

---

# Functions Without Return

Some functions simply perform actions.

```python
def display_menu():

    print("1. View Books")
    print("2. Borrow Book")
```

No return value is necessary.

---

# Functions as Problem-Solving Tools

Suppose we want to calculate the area of rectangles repeatedly.

Bad approach:

```python
area = 5 * 10

area = 8 * 4

area = 9 * 7
```

Better approach:

```python
def rectangle_area(
    length,
    width
):

    return length * width
```

---

# Example: Student Grade Function

```python
def calculate_grade(mark):

    if mark >= 80:

        return "HD"

    elif mark >= 70:

        return "D"

    elif mark >= 60:

        return "C"

    elif mark >= 50:

        return "P"

    return "F"
```

Usage:

```python
grade = calculate_grade(78)

print(grade)
```

Output:

```text
D
```

---

# Recursive Functions

A recursive function is a function that calls itself.

This is an advanced but powerful concept.

---

# Understanding Recursion Through Factorials

Mathematically:

```text
5!

=
5 × 4 × 3 × 2 × 1
```

Another way to express this is:

```text
5!

=
5 × 4!
```

Similarly:

```text
4!

=
4 × 3!
```

Eventually:

```text
1!

=
1
```

This definition naturally suggests recursion.

---

# Recursive Factorial Function

```python
def factorial(n):

    if n == 1:

        return 1

    return n * factorial(
        n - 1
    )
```

---

# Visualizing the Calls

Suppose:

```python
factorial(4)
```

Python performs:

```text
4 × factorial(3)

4 × (
    3 × factorial(2)
)

4 × (
    3 × (
        2 × factorial(1)
    )
)

4 × 3 × 2 × 1
```

Result:

```text
24
```

---

# The Importance of a Base Case

Every recursive function must have a stopping condition.

This is called the **base case**.

Example:

```python
if n == 1:

    return 1
```

Without it:

```python
factorial()
```

would continue forever until Python runs out of memory.

---

# Recursion vs Iteration

Factorial using recursion:

```python
factorial(n)
```

Factorial using a loop:

```python
for
while
```

Recursion is often:

✅ Elegant

✅ Compact

However loops may sometimes be:

✅ Faster

✅ Easier to debug

Professional developers choose the approach most appropriate for the situation.

---

# Mini Project: Simple Calculator

Create functions for:

```text
Addition
Subtraction
Multiplication
Division
```

Requirements:

```python
add()
subtract()
multiply()
divide()
```

Read numbers from the user and display the result.

This project combines:

- Input
- Output
- Functions
- Type Conversion

---

# Common Beginner Mistakes

## Forgetting Type Conversion

```python
age = input()

age + 1
```

Produces an error.

---

## Defining but Never Calling a Function

```python
def greet():

    print("Hello")
```

No output occurs until:

```python
greet()
```

is executed.

---

## Missing Return Statements

```python
def square(n):

    n * n
```

No value is returned.

Correct:

```python
def square(n):

    return n * n
```

---

## Recursive Functions Without a Base Case

Always ensure recursion has a stopping condition.

---

# Summary

In this tutorial, you learned:

✅ How Python receives user input.

✅ Why type conversion is necessary.

✅ How to accept multiple inputs.

✅ How to display formatted output.

✅ What functions are and why they matter.

✅ How to build reusable code using parameters.

✅ How return values work.

✅ How recursive functions operate.

These concepts provide the foundation for building larger and more structured applications.

---

# Knowledge Check

1. Why does `input()` always return a string?
2. When should you use `int()` and `float()`?
3. What is the purpose of `split()`?
4. What problem do functions solve?
5. What is the difference between a parameter and an argument?
6. What is recursion?
7. Why is a base case required in recursive functions?

---

# Next Tutorial

In **Tutorial 04: Working with Python Collections**, we will explore lists, tuples, and dictionaries, which are essential data structures for storing and managing groups of data efficiently.
