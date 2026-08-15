# Solution 03: Functional Programming

## Overview

This document provides suggested solutions for **Exercise 03: Functions**.

The purpose of these exercises is to reinforce:

- Function Design
- Parameters
- Return Values
- Modular Programming
- Recursion
- Problem Solving

Functions are one of the most important programming concepts because they allow developers to break large problems into smaller reusable components.

---

# Question 1

## Tax Calculation Function

### Problem Statement

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

# Solution

## Analysis

The tax amount can be calculated using:

```text
Tax Amount = Salary × Tax Rate
```

For example:

```text
Salary = $80,000

Tax Rate = 30%

Tax Amount = $24,000
```

---

## Algorithm

1. Accept salary.
2. Accept tax rate.
3. Convert tax rate to decimal form.
4. Calculate tax amount.
5. Return tax amount.

---

## Implementation

```python
def calculate_tax(
    salary,
    tax_rate
):

    tax_amount = (
        salary * tax_rate
    )

    return tax_amount
```

---

## Using the Function

```python
salary = 80000

tax = calculate_tax(
    salary,
    0.30
)

print(
    f"Tax Amount: ${tax:.2f}"
)
```

---

## Sample Output

```text
Tax Amount: $24000.00
```

---

## Alternative Version

Users enter percentages.

```python
def calculate_tax(
    salary,
    tax_rate
):

    return (
        salary *
        (tax_rate / 100)
    )
```

Usage:

```python
tax = calculate_tax(
    80000,
    30
)
```

Output:

```text
24000
```

---

## Discussion

This solution demonstrates:

```text
Parameters

Arithmetic Operations

Return Values
```

The function can easily be reused throughout an application.

---

# Question 2

## Palindrome Function

### Problem Statement

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

# Understanding Palindromes

A palindrome reads identically in both directions.

Example:

```text
madam
```

Forward:

```text
madam
```

Backward:

```text
madam
```

They are identical.

Therefore:

```text
Palindrome
```

---

## Non-Palindrome Example

```text
python
```

Forward:

```text
python
```

Backward:

```text
nohtyp
```

Different.

Therefore:

```text
Not a palindrome
```

---

# Algorithm

1. Accept a word.
2. Reverse the word.
3. Compare original and reversed versions.
4. Return the result.

---

# Implementation

```python
def is_palindrome(word):

    reversed_word = word[::-1]

    return (
        word == reversed_word
    )
```

---

# Using the Function

```python
result = is_palindrome(
    "madam"
)

print(result)
```

Output:

```text
True
```

---

# Multiple Test Cases

```python
print(
    is_palindrome(
        "madam"
    )
)

print(
    is_palindrome(
        "level"
    )
)

print(
    is_palindrome(
        "python"
    )
)
```

Output:

```text
True

True

False
```

---

# Improved Version

Often we want:

```text
Madam

MADAM

madam
```

to all be treated equally.

---

## Improved Implementation

```python
def is_palindrome(word):

    word = word.lower()

    return (
        word ==
        word[::-1]
    )
```

---

# Discussion

This solution demonstrates:

```text
Functions

String Manipulation

Slicing

Boolean Logic
```

---

# Question 3

## Recursive Fibonacci Function

### Problem Statement

Implement a recursive function that calculates Fibonacci numbers.

Example:

```text
0 1 1 2 3 5 8 ...
```

---

# Understanding Fibonacci Numbers

The Fibonacci sequence begins with:

```text
0
1
```

Every subsequent number is the sum of the previous two.

Example:

```text
0

1

0 + 1 = 1

1 + 1 = 2

1 + 2 = 3

2 + 3 = 5

3 + 5 = 8
```

Result:

```text
0 1 1 2 3 5 8
```

---

# Mathematical Definition

```text
F(0) = 0

F(1) = 1

F(n) = F(n−1) + F(n−2)
```

This definition naturally leads to recursion.

---

# Recursive Algorithm

To calculate:

```text
F(5)
```

we need:

```text
F(4)

F(3)
```

Each of those requires additional Fibonacci values.

The process continues until:

```text
F(0)

F(1)
```

which are known directly.

---

# Recursive Implementation

```python
def fibonacci(n):

    if n == 0:

        return 0

    elif n == 1:

        return 1

    else:

        return (
            fibonacci(n - 1)
            +
            fibonacci(n - 2)
        )
```

---

# Using the Function

```python
print(
    fibonacci(6)
)
```

Output:

```text
8
```

---

# Generating a Sequence

```python
for i in range(10):

    print(
        fibonacci(i),
        end=" "
    )
```

Output:

```text
0 1 1 2 3 5 8 13 21 34
```

---

# Visualizing Recursion

Suppose:

```python
fibonacci(4)
```

Python performs:

```text
fibonacci(4)

=
fibonacci(3)

+
fibonacci(2)
```

Further expansion:

```text
fibonacci(3)

=
fibonacci(2)

+
fibonacci(1)
```

Eventually:

```text
fibonacci(1)

=
1

fibonacci(0)

=
0
```

The recursive calls begin returning values until the final answer is produced.

---

# Importance of Base Cases

Every recursive function requires stopping conditions.

For Fibonacci:

```python
if n == 0:

    return 0

elif n == 1:

    return 1
```

These are known as:

```text
Base Cases
```

Without them:

```python
fibonacci()
```

would continue calling itself indefinitely.

---

# Iterative Alternative

Although recursion is elegant, Fibonacci can also be implemented using loops.

```python
def fibonacci_iterative(n):

    a = 0

    b = 1

    for _ in range(n):

        a, b = b, a + b

    return a
```

---

# Comparison

| Approach | Advantages | Disadvantages |
|-----------|------------|------------|
| Recursive | Elegant, mirrors mathematical definition | Less efficient |
| Iterative | Faster, uses less memory | Slightly less intuitive |

---

# Reflection

These exercises demonstrate several important software engineering concepts.

---

## Exercise 1

```python
calculate_tax()
```

demonstrates:

```text
Function Parameters

Return Values

Code Reuse
```

---

## Exercise 2

```python
is_palindrome()
```

demonstrates:

```text
String Processing

Boolean Logic

Function Design
```

---

## Exercise 3

```python
fibonacci()
```

demonstrates:

```text
Recursion

Problem Decomposition

Mathematical Modelling
```

---

# Self-Evaluation Checklist

After completing Exercise 03, you should be able to:

✅ Create custom functions.

✅ Use parameters effectively.

✅ Return values from functions.

✅ Develop reusable program components.

✅ Manipulate strings inside functions.

✅ Understand recursion.

✅ Identify base cases.

✅ Compare recursive and iterative solutions.

---

# Key Takeaways

Functions are fundamental building blocks of software development.

By mastering functions, programmers can:

```text
Reduce Duplication

Improve Readability

Simplify Maintenance

Create Modular Systems
```

These skills become increasingly important as we move toward larger object-oriented applications and software engineering projects.
