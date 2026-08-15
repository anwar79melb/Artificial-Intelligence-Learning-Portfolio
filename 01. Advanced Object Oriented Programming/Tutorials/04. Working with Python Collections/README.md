# Tutorial 04: Working with Python Collections

## Overview

Most real-world applications work with collections of data rather than individual values.

Consider the following examples:

- A library contains thousands of books.
- A university stores information about thousands of students.
- An online store manages thousands of products.
- A machine learning model may process millions of records.

Managing each value using separate variables would quickly become impossible.

Python provides several powerful collection data structures to solve this problem:

- Lists
- Tuples
- Dictionaries

These collections allow developers to store, organize, access, and manipulate large amounts of data efficiently.

In this tutorial, we will explore the most important collection types available in Python and learn how they are used in practical applications.

---

# Learning Objectives

By the end of this tutorial, you should be able to:

- Understand why collections are important.
- Create and manipulate Python lists.
- Access list elements using indexing.
- Use list slicing to extract subsets of data.
- Apply common list operations and methods.
- Implement a simple sorting algorithm.
- Understand tuples and immutability.
- Create and use dictionaries effectively.
- Choose the appropriate collection type for different scenarios.

---

# Why Collections Matter

Imagine developing a student management system.

Without collections:

```python
student1 = "Alex"
student2 = "John"
student3 = "Emma"
student4 = "Chris"
student5 = "Sarah"
```

As the number of students grows:

```text
10 students
100 students
10,000 students
```

This approach becomes impractical.

Collections solve this problem by allowing multiple values to be stored within a single object.

---

# Introduction to Lists

A list is an ordered collection of values.

Lists are one of the most commonly used data structures in Python.

Examples from everyday life include:

- Shopping lists
- Contact lists
- To-do lists
- Library book collections
- Product catalogs

---

# Creating Lists

Lists are created using square brackets.

Example:

```python
numbers = [1, 2, 3, 4, 5]
```

---

# List of Strings

```python
students = [
    "Alex",
    "John",
    "Emma",
    "Sarah"
]
```

---

# Mixed Data Types

Unlike many programming languages, Python lists can contain different data types.

```python
data = [
    100,
    "Python",
    9.5,
    True
]
```

Although possible, mixing data types should be done carefully to maintain readability.

---

# Empty Lists

Sometimes a list starts with no data.

```python
books = []
```

This is called an empty list.

Items can be added later.

---

# How Lists Work

Think of a list as a sequence of positions.

```text
Index:   0      1      2      3

Value: Alex   John   Emma   Sarah
```

Every element has an index.

---

# Accessing List Elements

List elements are accessed using their index.

Example:

```python
students = [
    "Alex",
    "John",
    "Emma",
    "Sarah"
]

print(students[0])
```

Output:

```text
Alex
```

---

# Important Rule: Indexing Starts at 0

Many beginners expect counting to start at 1.

Python starts at:

```text
0
```

For example:

```python
students[0]
```

refers to:

```text
First element
```

while:

```python
students[3]
```

refers to:

```text
Fourth element
```

---

# Using Elements Like Variables

An element can be assigned a new value.

Example:

```python
students[1] = "Michael"
```

Before:

```text
Alex
John
Emma
Sarah
```

After:

```text
Alex
Michael
Emma
Sarah
```

Lists are mutable, meaning their contents can change.

---

# Negative Indexing

Python supports a very useful feature known as negative indexing.

Instead of counting from the beginning:

```text
0 1 2 3
```

we can count backwards:

```text
-4 -3 -2 -1
```

---

# Accessing the Last Element

```python
students[-1]
```

Returns:

```text
Sarah
```

---

# Accessing the Second Last Element

```python
students[-2]
```

Returns:

```text
Emma
```

---

# Why Negative Indexing Is Useful

Suppose we need the latest entry in a log file.

Instead of calculating:

```python
logs[len(logs)-1]
```

we can simply write:

```python
logs[-1]
```

This is cleaner and easier to read.

---

# Understanding List Slicing

One of Python's most powerful features is slicing.

Slicing allows us to extract portions of a collection.

General syntax:

```python
list[start:stop:step]
```

---

# Visualizing Slicing

Consider:

```python
numbers = [
    0,1,2,3,4,5,6,7,8,9,10
]
```

Indexes:

```text
0 1 2 3 4 5 6 7 8 9 10
```

---

# The Start Index

The element at the start position is included.

Example:

```python
numbers[2:6]
```

Result:

```text
[2, 3, 4, 5]
```

---

# The Stop Index

The stop position is not included.

Many beginners find this confusing.

Example:

```python
numbers[2:6]
```

Includes:

```text
2
3
4
5
```

Does NOT include:

```text
6
```

---

# The Step Value

The third value controls the interval.

Example:

```python
numbers[0:11:2]
```

Result:

```text
[0, 2, 4, 6, 8, 10]
```

Python selects every second element.

---

# Omitting Values

Python provides sensible defaults.

---

## Everything From Index 3 Onward

```python
numbers[3:]
```

Result:

```text
[3,4,5,6,7,8,9,10]
```

---

## Everything Before Index 3

```python
numbers[:3]
```

Result:

```text
[0,1,2]
```

---

## Entire List

```python
numbers[:]
```

Returns a copy of the list.

---

## Every Second Element

```python
numbers[::2]
```

Result:

```text
[0,2,4,6,8,10]
```

---

# Practical Examples

Suppose a machine learning dataset contains:

```python
dataset = [
    1,2,3,4,5,6,7,8,9,10
]
```

Training subset:

```python
dataset[:8]
```

Testing subset:

```python
dataset[8:]
```

Slicing is heavily used in:

- Data Science
- Machine Learning
- Artificial Intelligence
- Data Analytics

---

# Useful Built-In List Functions

Python provides several functions that work with lists.

---

# len()

Returns the number of elements.

```python
numbers = [1,2,3,4]

print(len(numbers))
```

Output:

```text
4
```

---

# max()

Returns the largest value.

```python
max(numbers)
```

Output:

```text
4
```

---

# min()

Returns the smallest value.

```python
min(numbers)
```

Output:

```text
1
```

---

# sum()

Returns the total sum.

```python
sum(numbers)
```

Output:

```text
10
```

---

# Combining Lists

The `+` operator joins lists.

```python
list1 = [1,2]
list2 = [3,4]

result = list1 + list2
```

Result:

```text
[1,2,3,4]
```

---

# Repeating Lists

The `*` operator repeats a list.

```python
[1,2] * 3
```

Result:

```text
[1,2,1,2,1,2]
```

---

# Common List Methods

Methods belong directly to list objects.

---

# append()

Adds an element to the end.

```python
students = ["Alex"]

students.append("John")
```

Result:

```text
['Alex', 'John']
```

---

# insert()

Adds an element at a specific position.

```python
students.insert(
    1,
    "Emma"
)
```

Result:

```text
['Alex', 'Emma', 'John']
```

---

# remove()

Removes an element.

```python
students.remove(
    "Emma"
)
```

---

# pop()

Removes an element by index.

```python
students.pop(0)
```

---

# reverse()

Reverses list order.

```python
students.reverse()
```

---

# sort()

Sorts the list.

```python
numbers.sort()
```

---

# Important Note About List Methods

Many list methods modify the original list directly.

Example:

```python
numbers = [3,2,1]

result = numbers.sort()
```

Many beginners expect:

```python
result
```

to contain the sorted list.

However:

```python
result
```

contains:

```python
None
```

because `sort()` modifies the original list rather than returning a new one.

---

# Problem Solving with Lists

Suppose we wish to sort values manually.

Consider:

```python
numbers = [
    19, 3, 54, 37,
    62, 8, 93
]
```

How can we sort them without using `sort()`?

This leads us to sorting algorithms.

---

# Bubble Sort

Bubble Sort repeatedly compares neighboring elements and swaps them if they are in the wrong order.

---

# Visual Example

Initial list:

```text
19, 3, 54, 37
```

Compare:

```text
19 and 3
```

Swap:

```text
3, 19, 54, 37
```

Continue until the list becomes sorted.

---

# Bubble Sort Implementation

```python
def bubble_sort(data):

    n = len(data)

    for i in range(n):

        for j in range(
            0,
            n - i - 1
        ):

            if data[j] > data[j + 1]:

                temp = data[j]

                data[j] = data[j + 1]

                data[j + 1] = temp
```

---

# Introduction to Tuples

A tuple is similar to a list, but it cannot be changed after creation.

For this reason, tuples are said to be:

```text
Immutable
```

---

# Creating Tuples

```python
days = (
    "Mon",
    "Tue",
    "Wed"
)
```

---

# Accessing Tuple Elements

Indexing works exactly like lists.

```python
days[0]
```

Result:

```text
Mon
```

---

# Slicing Tuples

```python
days[1:]
```

Result:

```text
('Tue', 'Wed')
```

---

# Why Use Tuples?

Tuples are generally:

- Faster
- Safer
- Memory efficient

Use tuples when data should never change.

Examples:

```text
Coordinates
RGB Colors
Days of the Week
Country Codes
```

---

# Lists vs Tuples

| Feature | List | Tuple |
|----------|--------|--------|
| Ordered | Yes | Yes |
| Mutable | Yes | No |
| Indexed | Yes | Yes |
| Sliceable | Yes | Yes |

Rule of thumb:

```text
Data changes → List

Data stays fixed → Tuple
```

---

# Introduction to Dictionaries

Lists use numbers as indexes.

Dictionaries use keys.

This makes data more meaningful.

---

# List Example

```python
days = [
    31,
    28,
    31,
    30
]
```

To find January days:

```python
days[0]
```

Not very descriptive.

---

# Dictionary Example

```python
days = {

    "January": 31,

    "February": 28,

    "March": 31
}
```

Access:

```python
days["January"]
```

Result:

```text
31
```

The code is much easier to understand.

---

# Creating Dictionaries

Syntax:

```python
dictionary = {

    key: value,

    key: value
}
```

Example:

```python
student = {

    "id": 1001,

    "name": "Alex",

    "course": "AI"
}
```

---

# Accessing Values

```python
student["name"]
```

Result:

```text
Alex
```

---

# Adding New Entries

```python
student["email"] =

"alex@email.com"
```

---

# Updating Values

```python
student["course"] =

"Artificial Intelligence"
```

---

# Dictionary Keys

Keys must be immutable.

Common examples:

```python
String
Integer
Float
Tuple
```

Most developers use strings.

---

# Dictionaries in Real Applications

Dictionaries are commonly used for:

- Student records
- JSON data
- Configuration files
- Web APIs
- Machine learning metadata

Example:

```python
book = {

    "isbn": "1234",

    "title": "Python",

    "copies": 5
}
```

---

# Choosing the Right Collection

| Collection | Best Used For |
|-------------|---------------|
| List | Dynamic sequence of items |
| Tuple | Fixed data |
| Dictionary | Key-value lookup |

---

# Mini Project: Student Database

Create a program that stores:

```text
Student ID
Name
Course
Email
```

Using dictionaries.

Store multiple students in a list.

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
    }
]
```

This combines lists and dictionaries, which is extremely common in real-world applications.

---

# Common Beginner Mistakes

## Forgetting That Indexes Start at 0

```python
students[1]
```

returns the second element.

---

## Confusing Lists and Tuples

Lists:

```python
[]
```

Tuples:

```python
()
```

---

## Accessing Missing Dictionary Keys

```python
student["phone"]
```

Produces:

```text
KeyError
```

if the key does not exist.

---

## Forgetting That Tuples Are Immutable

```python
days[0] = "Sunday"
```

Produces an error.

---

# Summary

In this tutorial, you learned:

✅ How lists store ordered collections of data.

✅ How indexing and negative indexing work.

✅ How slicing extracts subsets of data.

✅ Common list functions and methods.

✅ How sorting algorithms work conceptually.

✅ Why tuples are useful.

✅ How dictionaries store key-value pairs.

✅ How to choose the right collection for a given problem.

These collection types form the foundation of many advanced topics including object-oriented design, data science, machine learning, and artificial intelligence.

---

# Knowledge Check

1. What is the difference between a list and a tuple?
2. Why does Python use zero-based indexing?
3. What is slicing?
4. What does `numbers[::2]` return?
5. When should a dictionary be used instead of a list?
6. Why are tuples considered safer than lists?
7. What happens if you access a dictionary key that does not exist?

---

# Next Tutorial

In **Tutorial 05: Object-Oriented Design with Classes**, we will begin creating our own classes and objects, transforming Python from a simple programming language into a powerful tool for modelling real-world systems.
