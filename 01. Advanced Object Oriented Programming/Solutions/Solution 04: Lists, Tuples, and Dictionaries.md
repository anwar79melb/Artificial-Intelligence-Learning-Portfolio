# Solution 04: Lists, Tuples and Dictionaries

## Overview

This document provides suggested solutions for **Exercise 04: Lists, Tuples and Dictionaries**.

The purpose of these exercises is to strengthen your understanding of:

- Collection Data Structures
- List Operations
- Tuple Immutability
- Dictionary Manipulation
- Data Processing
- Problem Solving

Collections are among the most frequently used structures in Python and form the foundation of many real-world software systems.

---

# Question 1

## List Processing

### Problem Statement

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

# Solution

## Analysis

We need to:

1. Generate 20 random integers.
2. Store them in a list.
3. Apply built-in list functions.
4. Display useful statistics.

---

## Python Implementation

```python
import random

numbers = []

for i in range(20):

    numbers.append(
        random.randint(1, 100)
    )

print("Original List:")
print(numbers)

print("\nLargest Value:")
print(max(numbers))

print("\nSmallest Value:")
print(min(numbers))

average = sum(numbers) / len(numbers)

print("\nAverage:")
print(average)

numbers.sort()

print("\nSorted List:")
print(numbers)
```

---

## Sample Output

```text
Original List:
[55, 12, 89, 41, 67, 23, 91, 37, 10, 75,
 18, 42, 65, 51, 79, 30, 88, 24, 13, 60]

Largest Value:
91

Smallest Value:
10

Average:
48.0

Sorted List:
[10, 12, 13, 18, 23, 24, 30, 37, 41,
 42, 51, 55, 60, 65, 67, 75, 79, 88,
 89, 91]
```

---

## Discussion

This solution demonstrates:

```text
Lists

Loops

Random Number Generation

Built-in List Functions

Sorting
```

---

# Alternative Solution

Using list comprehension:

```python
import random

numbers = [

    random.randint(1, 100)

    for i in range(20)
]
```

This produces the same result with fewer lines of code.

---

# Question 2

## Tuple Immutability

### Problem Statement

Create a tuple containing:

```text
Days of the Week
```

Attempt to modify one of the elements.

Explain the result.

---

# Solution

## Creating the Tuple

```python
days = (

    "Monday",

    "Tuesday",

    "Wednesday",

    "Thursday",

    "Friday",

    "Saturday",

    "Sunday"
)
```

---

## Accessing Elements

```python
print(days[0])
```

Output:

```text
Monday
```

---

## Attempting Modification

```python
days[0] = "Mon"
```

---

## Result

Python produces:

```text
TypeError:
'tuple' object does not support item assignment
```

---

# Why Does This Happen?

Tuples are:

```text
Immutable
```

meaning their contents cannot be changed after creation.

Unlike lists:

```python
students[0] = "Alex"
```

Tuples do not allow assignment operations.

---

# Benefits of Immutability

Tuple immutability provides:

### Reliability

Data cannot be modified accidentally.

---

### Security

Important information remains unchanged.

---

### Performance

Tuples generally require less memory than lists.

---

# Practical Example

GPS coordinates:

```python
location = (

    -37.8136,

    144.9631
)
```

The coordinates should remain fixed.

A tuple is therefore more appropriate than a list.

---

## Discussion

Use tuples when:

```text
Data Should Never Change
```

Examples:

```text
Coordinates

Days of Week

Months

Country Codes

RGB Values
```

---

# Question 3

## Student Dictionary

### Problem Statement

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

# Solution

## Creating the Dictionary

```python
student = {

    "student_id": 1001,

    "name": "Alex",

    "course": "Artificial Intelligence",

    "email": "alex@email.com",

    "gpa": 3.8
}
```

---

# Displaying Data

```python
print(student)
```

Output:

```python
{
    'student_id': 1001,
    'name': 'Alex',
    'course': 'Artificial Intelligence',
    'email': 'alex@email.com',
    'gpa': 3.8
}
```

---

# Adding Data

Suppose we wish to add:

```text
Phone Number
```

---

## Implementation

```python
student["phone"] =

"0400123456"
```

---

## Result

```python
{
    ...
    'phone': '0400123456'
}
```

---

# Updating Data

Suppose GPA changes.

---

## Implementation

```python
student["gpa"] = 4.0
```

---

## Result

```python
{
    ...
    'gpa': 4.0
}
```

---

# Deleting Data

Suppose we remove:

```text
Phone Number
```

---

## Implementation

```python
del student["phone"]
```

---

## Result

```python
{
    'student_id': 1001,
    'name': 'Alex',
    'course': 'Artificial Intelligence',
    'email': 'alex@email.com',
    'gpa': 4.0
}
```

---

# Complete Program

```python
student = {

    "student_id": 1001,

    "name": "Alex",

    "course":
    "Artificial Intelligence",

    "email":
    "alex@email.com",

    "gpa": 3.8
}

print(
    "\nOriginal Record:"
)

print(student)

student["phone"] =

"0400123456"

student["gpa"] = 4.0

del student["phone"]

print(
    "\nUpdated Record:"
)

print(student)
```

---

# Sample Output

```text
Original Record:

{
 'student_id': 1001,
 'name': 'Alex',
 'course': 'Artificial Intelligence',
 'email': 'alex@email.com',
 'gpa': 3.8
}

Updated Record:

{
 'student_id': 1001,
 'name': 'Alex',
 'course': 'Artificial Intelligence',
 'email': 'alex@email.com',
 'gpa': 4.0
}
```

---

# Extension Activity

## Managing Multiple Students

A common real-world solution combines:

```text
Lists

+

Dictionaries
```

Example:

```python
students = [

    {
        "id": 1001,
        "name": "Alex"
    },

    {
        "id": 1002,
        "name": "Emma"
    },

    {
        "id": 1003,
        "name": "John"
    }
]
```

---

# Why This Design Is Useful

This structure resembles:

```text
Database Records

JSON Documents

Web API Responses

Machine Learning Metadata
```

and appears frequently in professional software applications.

---

# Reflection

Each collection type solves different problems.

---

## List

Best for:

```text
Ordered

Changeable

Growing Collections
```

Example:

```python
books = []

students = []
```

---

## Tuple

Best for:

```text
Fixed Information

Read-Only Data
```

Example:

```python
week_days = (
    ...
)
```

---

## Dictionary

Best for:

```text
Descriptive Data

Fast Lookups

Key-Value Storage
```

Example:

```python
student = {

    ...
}
```

---

# Comparison Table

| Feature | List | Tuple | Dictionary |
|----------|--------|--------|------------|
| Ordered | Yes | Yes | Yes |
| Mutable | Yes | No | Yes |
| Indexed | Yes | Yes | Keys |
| Fast Lookup | No | No | Yes |
| Use Case | Collections | Fixed Data | Records |

---

# Self-Evaluation Checklist

After completing Exercise 04, you should be able to:

✅ Create lists.

✅ Access list elements.

✅ Sort lists.

✅ Use list functions.

✅ Create tuples.

✅ Explain immutability.

✅ Create dictionaries.

✅ Add dictionary entries.

✅ Update dictionary values.

✅ Delete dictionary entries.

✅ Combine lists and dictionaries.

---

# Key Takeaways

This exercise introduced three fundamental Python collection types:

```text
Lists

Tuples

Dictionaries
```

Mastering these structures is essential because they are widely used in:

```text
Object-Oriented Programming

Data Science

Machine Learning

Artificial Intelligence

Web Development

Software Engineering
```

Many advanced applications are built on these simple but extremely powerful collection structures.
