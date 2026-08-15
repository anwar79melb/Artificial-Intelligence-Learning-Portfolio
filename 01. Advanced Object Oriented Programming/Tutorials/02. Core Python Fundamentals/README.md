# Tutorial 02: Core Python Fundamentals

## Overview

Before building object-oriented applications, machine learning models, or artificial intelligence systems, it is essential to develop a solid understanding of the programming fundamentals that form the foundation of Python development.

In this tutorial, we will explore:

- Variables
- Data Types
- Assignment Statements
- Operators
- Conditional Statements
- Loops
- Program Flow Control

These concepts are the building blocks used in every Python program, regardless of its complexity.

---

# Learning Objectives

After completing this tutorial, you should be able to:

- Declare and use variables effectively.
- Understand Python's built-in data types.
- Use assignment statements and operators.
- Make decisions using conditional statements.
- Create repetitive processes using loops.
- Develop small interactive Python programs.
- Apply problem-solving techniques using program flow control.

---

# Why Learn the Fundamentals?

Imagine building a Library Management System.

Before implementing classes such as:

```text
Book
Member
Librarian
Loan
```

you first need the ability to store and manipulate data.

Consider the following questions:

- How do we store a book title?
- How do we record the number of available copies?
- How do we determine whether a book can be borrowed?
- How do we repeatedly process multiple records?

The answers begin with variables, data types, and control structures.

---

# Understanding Variables

## What is a Variable?

A variable is a named location used to store data during program execution.

Think of a variable as a labelled container.

```text
+------------------+
|      Age         |
+------------------+
|       25         |
+------------------+
```

The label is the variable name.

The value stored inside may change during the program's execution.

---

## Creating Variables in Python

Unlike languages such as Java or C++, Python does not require explicit variable declarations.

Simply assign a value:

```python
age = 25
```

Python automatically determines the data type.

Another example:

```python
name = "Alex"
```

---

## Dynamic Typing in Python

Python is dynamically typed.

This means the same variable can hold different types of data.

```python
value = 100

value = "Artificial Intelligence"
```

Although this flexibility is powerful, it should be used carefully to maintain code readability.

---

# Variable Naming Rules

Python has several naming rules.

A variable name:

✅ Can start with a letter

```python
student
```

✅ Can start with an underscore

```python
_student
```

✅ Can contain numbers

```python
student1
```

❌ Cannot begin with a number

```python
1student
```

❌ Cannot contain spaces

```python
student name
```

❌ Cannot contain most special characters

```python
student-name
```

---

# Naming Conventions

Technically valid names are not always good names.

Poor examples:

```python
x
a
abc
```

Better examples:

```python
student_name
customer_balance
total_sales
average_score
```

Good variable names improve readability and maintainability.

---

# Data Types in Python

Programs work with different categories of data.

Python provides several built-in data types.

---

# Integer (int)

Integers represent whole numbers.

Examples:

```python
age = 25

employees = 100

temperature = -5
```

---

# Floating-Point Numbers (float)

Floats represent decimal numbers.

Examples:

```python
price = 19.99

gpa = 3.75

pi = 3.14159
```

---

# Boolean (bool)

Booleans represent logical values.

Two possible values:

```python
True
False
```

Examples:

```python
is_student = True

is_logged_in = False
```

Booleans are heavily used in decision-making.

---

# Strings (str)

Strings represent text.

Examples:

```python
name = "Alice"

course = "Artificial Intelligence"
```

Strings may contain:

- Letters
- Numbers
- Symbols
- Spaces

---

# Checking Data Types

Python provides the `type()` function.

Example:

```python
age = 25

print(type(age))
```

Output:

```text
<class 'int'>
```

---

# Assignment Statements

An assignment statement stores a value into a variable.

General syntax:

```python
variable = value
```

Example:

```python
score = 95
```

Python evaluates the right-hand side before assignment.

```python
result = 5 + 10
```

Result:

```text
15
```

stored inside the variable.

---

# Variables Can Change

Variables are designed to hold changing values.

```python
score = 70

score = score + 10
```

The new value becomes:

```text
80
```

---

# Arithmetic Operators

Python supports standard mathematical operators.

## Addition

```python
5 + 3
```

Result:

```text
8
```

---

## Subtraction

```python
10 - 4
```

Result:

```text
6
```

---

## Multiplication

```python
6 * 3
```

Result:

```text
18
```

---

## Division

```python
10 / 2
```

Result:

```text
5.0
```

---

## Integer Division

```python
10 // 3
```

Result:

```text
3
```

---

## Modulus

Returns remainder.

```python
10 % 3
```

Result:

```text
1
```

---

## Exponentiation

```python
2 ** 3
```

Result:

```text
8
```

---

# Example: Area of a Rectangle

```python
length = 10
width = 5

area = length * width

print(area)
```

Output:

```text
50
```

---

# Program Flow and Decision Making

Programs do not always execute every statement.

Sometimes decisions must be made.

For example:

```text
Can a student graduate?
Can a customer borrow a book?
Can a user log in?
```

Decision-making is based on conditions.

---

# Comparison Operators

Comparison operators evaluate conditions.

| Operator | Meaning |
|-----------|----------|
| == | Equal to |
| != | Not equal to |
| > | Greater than |
| < | Less than |
| >= | Greater than or equal |
| <= | Less than or equal |

Example:

```python
age = 20

print(age >= 18)
```

Output:

```text
True
```

---

# Boolean Expressions

A Boolean expression always evaluates to:

```text
True
```

or

```text
False
```

Example:

```python
50 > 10
```

Result:

```text
True
```

---

# The if Statement

The simplest decision structure is the `if` statement.

```python
age = 20

if age >= 18:
    print("Adult")
```

Output:

```text
Adult
```

---

# Understanding Indentation

Python uses indentation to define code blocks.

Example:

```python
if age >= 18:
    print("Adult")
```

The indented line belongs to the condition.

Without correct indentation:

```python
if age >= 18:
print("Adult")
```

Python produces an error.

---

# The if-else Statement

When there are two possible outcomes:

```python
age = 15

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Minor
```

### If-elif-else flowchart

```
if
 ↓
elif
 ↓
elif
 ↓
else (optional)
```


---

# Multiple Conditions

Use `if-elif-else`.

Example:

```python
score = 72

if score >= 80:
    print("HD")

elif score >= 70:
    print("D")

elif score >= 60:
    print("C")

elif score >= 50:
    print("P")

else:
    print("F")
```

Output:

```text
D
```

---

# Multiple Decision Paths

When a program needs to evaluate multiple conditions, Python provides the `if-elif-else` structure.

General syntax:

```python
if condition_1:

    statements

elif condition_2:

    statements

elif condition_3:

    statements

...
    
elif condition_n:

    statements

else:

    statements
```

Important notes:

- Every structure must begin with an `if`.
- You may have **multiple `elif` statements**.
- The `else` statement is **optional**.
- Conditions are evaluated from top to bottom.
- Once a condition evaluates to `True`, the remaining conditions are skipped.

---

## Example: Student Grades

```python
score = 72

if score >= 80:

    print("HD")

elif score >= 70:

    print("D")

elif score >= 60:

    print("C")

elif score >= 50:

    print("P")

else:

    print("F")
```

Output:

```text
D
```

---

## How the Evaluation Works

Suppose:

```python
score = 72
```

Python evaluates conditions in order:

```text
score >= 80    → False
score >= 70    → True
```

Since the second condition is true:

```python
print("D")
```

is executed and the remaining conditions are ignored.

---

## Multiple elif Statements

There is no practical limit to the number of `elif` statements.

Example:

```python
temperature = 35

if temperature < 0:

    print("Freezing")

elif temperature < 15:

    print("Cold")

elif temperature < 25:

    print("Mild")

elif temperature < 35:

    print("Warm")

elif temperature < 40:

    print("Hot")
```

Output:

```text
Hot
```

---

## Else Is Optional

Many beginners assume an `else` block is required.

It is not.

This is perfectly valid Python:

```python
age = 20

if age >= 18:

    print("Adult")
```

Output:

```text
Adult
```

If the condition is false, nothing happens.

---

## Example Without Else

```python
balance = 500

if balance > 1000:

    print("Premium Customer")
```

Output:

```text
(No output)
```

because the condition is false and there is no `else` block.

---

## Common Mistake

Consider:

```python
score = 85

if score >= 50:

    print("Pass")

elif score >= 70:

    print("Credit")

elif score >= 80:

    print("Distinction")
```

Output:

```text
Pass
```

This happens because conditions are checked from top to bottom.

Once:

```python
score >= 50
```

becomes true, Python stops checking the remaining conditions.

The correct order should be:

```python
if score >= 80:

    print("Distinction")

elif score >= 70:

    print("Credit")

elif score >= 50:

    print("Pass")
```

Always place more restrictive conditions before broader conditions.


# Logical Operators

Sometimes multiple conditions must be combined.

## and

Both conditions must be true.

```python
age = 20
citizen = True

if age >= 18 and citizen:
    print("Eligible")
```

---

## or

At least one condition must be true.

```python
if age >= 18 or permission:
    print("Allowed")
```

---

## not

Reverses a condition.

```python
if not logged_in:
    print("Login Required")
```

---

# Repetition in Programming

Many tasks must be repeated.

Examples:

- Processing library books
- Displaying customer records
- Training machine learning models
- Reading datasets

Instead of repeating code manually, loops automate repetition.

---

# The for Loop

A `for` loop repeats a task a fixed number of times.

Example:

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

---

# Understanding range()

```python
range(5)
```

Produces:

```text
0, 1, 2, 3, 4
```

---

# Custom Range

```python
for number in range(1, 6):
    print(number)
```

Output:

```text
1
2
3
4
5
```

---

# Controlling the Step Size

```python
for number in range(0, 11, 2):
    print(number)
```

Output:

```text
0
2
4
6
8
10
```

---

# Example: Multiplication Table

```python
for number in range(1, 11):

    print("5 x", number, "=",
          5 * number)
```

---

# The while Loop

A `while` loop continues until a condition becomes false.

Example:

```python
count = 1

while count <= 5:

    print(count)

    count += 1
```

Output:

```text
1
2
3
4
5
```

---

# How While Loops Work

Flow:

```text
Check Condition
      |
      v
 True -----> Execute Loop
      |
      v
 Check Again
      |
      v
 False -----> Exit Loop
```

---

# Avoiding Infinite Loops

Dangerous example:

```python
while True:
    print("Hello")
```

The loop never stops.

Always ensure the condition eventually becomes false.

---

# The break Statement

Sometimes we want to stop a loop immediately.

```python
while True:

    user_input = input()

    if user_input == "quit":
        break
```

The loop terminates when the user enters:

```text
quit
```

---

# Example: Simple Login System

```python
password = "python123"

attempt = ""

while attempt != password:

    attempt = input(
        "Enter password: "
    )

print("Access Granted")
```

This is a practical example of loops and conditions working together.

---

# Mini Project: Grade Calculator

Create a program that:

1. Accepts two scores.
2. Calculates the average.
3. Determines a grade.

Example grading scheme:

```text
80+  = HD
70+  = D
60+  = C
50+  = P
Below 50 = F
```

---

# Real-World Scenario

Imagine a Library Management System.

A program might:

```python
available_copies = 3

if available_copies > 0:

    print("Book Available")

else:

    print("Out of Stock")
```

And perhaps process multiple books:

```python
for book in range(1000):

    process_book()
```

These same concepts later become the foundation of object-oriented applications.

---

# Common Beginner Mistakes

## Confusing = and ==

Assignment:

```python
score = 90
```

Comparison:

```python
score == 90
```

---

## Incorrect Indentation

Bad:

```python
if score > 50:
print("Pass")
```

Good:

```python
if score > 50:
    print("Pass")
```

---

## Infinite Loops

Always ensure loop conditions eventually change.

---

## Poor Variable Naming

Avoid:

```python
a
b
x
```

Prefer:

```python
total_sales
average_marks
student_name
```

---

# Summary

In this tutorial, you learned:

✅ What variables are and how they store data.

✅ How Python uses dynamic typing.

✅ Common built-in data types.

✅ Arithmetic and comparison operators.

✅ The role of Boolean expressions.

✅ How to make decisions using `if`, `if-else`, and `if-elif-else`.

✅ How repetition works using `for` and `while` loops.

✅ How loops and conditions work together to solve problems.

These concepts form the foundation for everything that follows in Python programming.

---

# Knowledge Check

1. What is the difference between a variable and a value?
2. What is dynamic typing?
3. When would you use `if-elif-else` instead of `if-else`?
4. What is the difference between a `for` loop and a `while` loop?
5. What causes an infinite loop?
6. Why is indentation important in Python?

---

# Next Tutorial

In **Tutorial 03: User Input, Output, and Functions**, we will learn how Python programs interact with users, organize reusable code using functions, and solve larger problems through modular programming.
