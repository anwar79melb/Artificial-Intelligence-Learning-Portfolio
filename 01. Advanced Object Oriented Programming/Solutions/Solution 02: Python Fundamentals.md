# Solution 02: Python Fundamentals

## Overview

This document provides suggested solutions for **Exercise 02: Variables and Control Structures**.

The purpose of these activities is to demonstrate the use of:

- Variables
- Data Types
- Input and Output
- Arithmetic Operations
- Conditional Statements
- Loops
- Problem Solving

---

# Question 1

## Student Grade Calculator

### Problem Statement

Write a Python program that:

1. Accepts:
   - Student Name
   - Assignment Mark
   - Exam Mark

2. Calculates the final mark.

3. Determines the grade according to:

```text
80 – 100 → HD
70 – 79  → D
60 – 69  → C
50 – 59  → P
0 – 49   → F
```

4. Displays the result in a formatted report.

---

# Solution

## Algorithm

1. Read student's name.
2. Read assignment mark.
3. Read exam mark.
4. Calculate final mark.
5. Determine grade using an if-elif-else structure.
6. Display results.

---

## Python Implementation

```python
student_name = input(
    "Enter student name: "
)

assignment_mark = float(
    input(
        "Enter assignment mark: "
    )
)

exam_mark = float(
    input(
        "Enter exam mark: "
    )
)

final_mark = (
    assignment_mark +
    exam_mark
)

if final_mark >= 80:

    grade = "HD"

elif final_mark >= 70:

    grade = "D"

elif final_mark >= 60:

    grade = "C"

elif final_mark >= 50:

    grade = "P"

else:

    grade = "F"

print("\nRESULT REPORT")
print("---------------------")
print(
    f"Student Name : {student_name}"
)
print(
    f"Final Mark   : {final_mark}"
)
print(
    f"Grade        : {grade}"
)
```

---

## Sample Output

```text
Enter student name: Alex
Enter assignment mark: 40
Enter exam mark: 45

RESULT REPORT
---------------------
Student Name : Alex
Final Mark   : 85.0
Grade        : HD
```

---

## Discussion

This solution demonstrates:

```text
Variables

Input

Type Conversion

Arithmetic Operations

Selection Structures

Output Formatting
```

---

# Alternative Solution

Instead of storing the grade in a variable:

```python
if final_mark >= 80:

    print("HD")

elif final_mark >= 70:

    print("D")

...
```

However, storing the result first is often more flexible and maintainable.

---

# Question 2

## Print the Following Pattern

```text
*
**
***
****
*****
```

using a loop.

---

# Solution

## Understanding the Problem

Notice:

```text
Row 1 → 1 star
Row 2 → 2 stars
Row 3 → 3 stars
Row 4 → 4 stars
Row 5 → 5 stars
```

Each row contains one additional star.

---

## Python Implementation

```python
for row in range(1, 6):

    print("*" * row)
```

---

## Sample Output

```text
*
**
***
****
*****
```

---

# Explanation

First iteration:

```python
row = 1
```

Output:

```python
"*"
```

Second iteration:

```python
row = 2
```

Output:

```python
"**"
```

This continues until:

```python
row = 5
```

---

# Alternative Solution

Using nested loops:

```python
for row in range(1, 6):

    for col in range(row):

        print(
            "*",
            end=""
        )

    print()
```

Output is identical.

---

# Discussion

The first solution is preferred because:

```text
Shorter

Cleaner

Easier to Read
```

---

# Question 3

## Display All Prime Numbers Between 1 and 100

---

# Understanding Prime Numbers

A prime number:

```text
Has exactly two factors:

1

Itself
```

Examples:

```text
2
3
5
7
11
13
17
```

Not Prime:

```text
4  -> 1,2,4

6  -> 1,2,3,6

8  -> 1,2,4,8
```

---

# Algorithm

For each number:

1. Assume it is prime.
2. Test divisibility by smaller numbers.
3. If divisible:
   - Not prime.
4. Otherwise:
   - Prime.

---

# Python Implementation

```python
for number in range(2, 101):

    is_prime = True

    for divisor in**ange(
        2,
        number
 ** ):

        if number % divisor ** 0:

            is_prime = False**            break

    if is_prim**

        print(number)
```

---
** Sample Output

```text
2
3
5
7
1**13
17
19
23
29
31
...
97
```

---**# Step-by-Step Example

Consider:**```python
number = 7
```

Check:
**``python
7 % 2
```

Result:

```t**t
1
```

Check:

```python
7 % 3
**`

Result:

```text
1
```

Check:**```python
7 % 4
```

Result:

```**xt
3
```

No divisor found.

Ther**ore:

```text
Prime
```

---

# M**e Efficient Solution

We only nee**to test up to:

```text
√number
`**

because larger factors must pai**with smaller factors.

---

## Op**mized Version

```python
import m**h

for number in range(2, 101):

    is_prime = True

    for divisor in range(
        2,
        int(
            math.sqrt(number)
        ) + 1
    ):

        if number % divisor == 0:

            is_prime = False

            break

    if is_prime:

        print(number)
```

---

# Complexity Discussion

Basic Solution:

```text
O(n²)
```

Optimized Solution:

```text
O(n√n)
```

The optimized version becomes significantly faster for large values.

---

# Reflection

This exercise combines several important programming concepts:

### Variables

```python
number

divisor

is_prime
```

---

### Loops

```python
for
```

used repeatedly.

---

### Conditions

```python
if

else
```

used to determine primality.

---

### Arithmetic Operators

```python
%
```

used to calculate remainders.

---

# Self-Evaluation Checklist

After completing Exercise 02, you should be able to:

✅ Accept user input.

✅ Convert input into numeric values.

✅ Use arithmetic operations.

✅ Build selection structures using if-elif-else.

✅ Use loops to perform repetitive tasks.

✅ Generate output using formatted print statements.

✅ Solve mathematical problems using program logic.

✅ Understand how loops and conditions work together.

---

# Key Takeaways

The solutions in this exercise reinforce some of the most fundamental programming concepts:

```text
Variables

Data Types

Input

Output

Conditions

Loops

Problem Solving
```

Mastering these concepts is essential before progressing to functions, collections, classes, and object-oriented software design.
