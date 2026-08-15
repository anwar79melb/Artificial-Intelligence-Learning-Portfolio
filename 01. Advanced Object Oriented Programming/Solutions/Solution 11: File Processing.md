# Solution 11: File Processing

## Overview

This document provides suggested solutions for **Exercise 11: File Processing**.

This exercise focuses on:

- File Reading
- File Writing
- Data Processing
- Error Handling
- Lists
- Loops
- Statistical Calculations

File processing is an essential software engineering skill because most real-world applications need to:

```text
Store Data

Retrieve Data

Generate Reports

Maintain Records
```

Examples include:

```text
Library Systems

Banking Applications

Student Information Systems

Machine Learning Pipelines
```

---

# Question

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

Write a Python program that:

1. Reads the file.
2. Calculates:
   - Average Mark
   - Highest Mark
   - Lowest Mark
3. Writes results to:

```text
report.txt
```

---

# Step 1: Understanding the Input File

File:

```text
marks.txt
```

Contents:

```text
78
90
82
66
59
72
85
```

Each line represents one student's mark.

---

# Step 2: Read Marks from File

## Algorithm

```text
Open File

Read Lines

Convert Strings to Integers

Store Marks in a List
```

---

## Implementation

```python
marks = []

with open(
    "marks.txt",
    "r"
) as file:

    for line in file:

        marks.append(
            int(line.strip())
        )

print(marks)
```

---

## Expected Output

```text
[78, 90, 82, 66, 59, 72, 85]
```

---

# Step 3: Calculate Statistics

Once data is stored in a list, Python provides useful built-in functions.

---

## Highest Mark

```python
highest_mark = max(marks)
```

Result:

```text
90
```

---

## Lowest Mark

```python
lowest_mark = min(marks)
```

Result:

```text
59
```

---

## Average Mark

```python
average_mark = (

    sum(marks)

    /

    len(marks)
)
```

Calculation:

```text
(78+90+82+66+59+72+85)

÷

7

=

76.0
```

---

# Step 4: Write Report to File

## Implementation

```python
with open(
    "report.txt",
    "w"
) as report:

    report.write(
        f"Average Mark: "
        f"{average_mark}\n"
    )

    report.write(
        f"Highest Mark: "
        f"{highest_mark}\n"
    )

    report.write(
        f"Lowest Mark: "
        f"{lowest_mark}\n"
    )
```

---

# Contents of report.txt

```text
Average Mark: 76.0

Highest Mark: 90

Lowest Mark: 59
```

---

# Complete Solution

```python
marks = []

with open(
    "marks.txt",
    "r"
) as file:

    for line in file:

        marks.append(
            int(line.strip())
        )

average_mark = (
    sum(marks) /
    len(marks)
)

highest_mark = max(marks)

lowest_mark = min(marks)

with open(
    "report.txt",
    "w"
) as report:

    report.write(
        f"Average Mark: "
        f"{average_mark}\n"
    )

    report.write(
        f"Highest Mark: "
        f"{highest_mark}\n"
    )

    report.write(
        f"Lowest Mark: "
        f"{lowest_mark}\n"
    )

print(
    "Report Generated Successfully."
)
```

---

# Sample Output

```text
Report Generated Successfully.
```

Generated file:

```text
Average Mark: 76.0
Highest Mark: 90
Lowest Mark: 59
```

---

# Extension Activity

## Display Grade Distribution

Determine:

```text
HD

D

C

P

F
```

grades within the file.

---

# Grading Scheme

```text
80+  → HD

70-79 → D

60-69 → C

50-59 → P

Below 50 → F
```

---

# Analysis

Marks:

```text
78 → D

90 → HD

82 → HD

66 → C

59 → P

72 → D

85 → HD
```

---

# Expected Result

```text
HD = 3

D = 2

C = 1

P = 1

F = 0
```

---

# Algorithm

For each mark:

```text
Check Range

Increment Counter
```

---

# Implementation

```python
hd = 0
d = 0
c = 0
p = 0
f = 0

for mark in marks:

    if mark >= 80:

        hd += 1

    elif mark >= 70:

        d += 1

    elif mark >= 60:

        c += 1

    elif mark >= 50:

        p += 1

    else:

        f += 1
```

---

# Displaying Grade Counts

```python
print("HD:", hd)

print("D:", d)

print("C:", c)

print("P:", p)

print("F:", f)
```

---

# Output

```text
HD: 3

D: 2

C: 1

P: 1

F: 0
```

---

# Enhanced Report Generator

The report can include both statistics and grade distribution.

---

## Implementation

```python
with open(
    "report.txt",
    "w"
) as report:

    report.write(
        "MARK ANALYSIS REPORT\n"
    )

    report.write(
        "--------------------\n"
    )

    report.write(
        f"Average Mark: "
        f"{average_mark}\n"
    )

    report.write(
        f"Highest Mark: "
        f"{highest_mark}\n"
    )

    report.write(
        f"Lowest Mark: "
        f"{lowest_mark}\n\n"
    )

    report.write(
        "GRADE DISTRIBUTION\n"
    )

    report.write(
        f"HD: {hd}\n"
    )

    report.write(
        f"D: {d}\n"
    )

    report.write(
        f"C: {c}\n"
    )

    report.write(
        f"P: {p}\n"
    )

    report.write(
        f"F: {f}\n"
    )
```

---

# Example Final Report

```text
MARK ANALYSIS REPORT
--------------------

Average Mark: 76.0

Highest Mark: 90

Lowest Mark: 59

GRADE DISTRIBUTION

HD: 3

D: 2

C: 1

P: 1

F: 0
```

---

# Error Handling Improvement

A file may not exist.

Example:

```text
marks.txt
```

might be missing.

---

## Safer Solution

```python
try:

    with open(
        "marks.txt",
        "r"
    ) as file:

        marks = [

            int(line.strip())

            for line in file
        ]

except FileNotFoundError:

    print(
        "File not found."
    )
```

---

# Why Error Handling Is Important

Without error handling:

```text
Program Crashes
```

With error handling:

```text
Program Responds Gracefully
```

This is expected in professional software.

---

# Complexity Analysis

Let:

```text
n = number of marks
```

---

## Reading File

```text
O(n)
```

---

## Calculating Statistics

```text
O(n)
```

---

## Grade Distribution

```text
O(n)
```

---

## Overall Complexity

```text
O(n)
```

which is efficient and scalable.

---

# Reflection

This exercise combines concepts from several tutorials:

### Tutorial 03

```text
Functions

Input / Output
```

---

### Tutorial 04

```text
Lists
```

---

### Tutorial 09

```text
File Handling

Context Managers
```

---

### Tutorial 02

```text
Loops

Conditional Statements
```

---

# Self-Evaluation Checklist

After completing Exercise 11, you should be able to:

✅ Open files for reading.

✅ Open files for writing.

✅ Read numeric data from files.

✅ Convert strings to integers.

✅ Process data using lists.

✅ Calculate averages.

✅ Find maximum values.

✅ Find minimum values.

✅ Generate reports.

✅ Handle file-related errors.

---

# Key Takeaways

This exercise demonstrates a complete data-processing workflow:

```text
Read Data
      ↓

Process Data
      ↓

Generate Statistics
      ↓

Write Report
```

This workflow is the foundation of many real-world systems including:

```text
Student Result Processing

Sales Reporting

Business Analytics

Data Science Pipelines

Machine Learning Preprocessing
```
