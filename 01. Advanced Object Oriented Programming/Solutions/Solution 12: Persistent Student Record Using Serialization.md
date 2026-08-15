# Solution 12: Persistent Student Records Using Serialization

## Overview

This document provides suggested solutions for **Exercise 12: Persistent Student Records**.

This exercise combines several concepts from throughout the course:

- Classes and Objects
- Constructors
- Lists
- File Handling
- Serialization
- Deserialization
- Object Persistence
- Object-Oriented Design

The goal is to create student objects, save them permanently to a file, restore them later, and generate simple reports.

---

# Problem Statement

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

Requirements:

1. Create student objects.
2. Store students in a list.
3. Serialize the list into:

```text
students.dat
```

4. Deserialize the file.
5. Display all student information.

---

# Challenge Requirement

After deserialization calculate:

```text
Highest GPA

Lowest GPA

Average GPA
```

---

# Understanding the Problem

Suppose we create:

```python
student1 = Student(...)
student2 = Student(...)
student3 = Student(...)
```

These objects exist only while the program is running.

Once the application exits:

```text
Objects are lost.
```

Serialization allows us to save the objects permanently and restore them later.

---

# Step 1: Design the Student Class

## UML Diagram

```text
+---------------------------+
|          Student          |
+---------------------------+
| student_id               |
| name                     |
| course                   |
| gpa                      |
+---------------------------+
| display_details()        |
+---------------------------+
```

---

# Python Implementation

```python
class Student:

    def __init__(
        self,
        student_id,
        name,
        course,
        gpa
    ):

        self.student_id = student_id
        self.name = name
        self.course = course
        self.gpa = gpa

    def display_details(self):

        print(
            f"ID: {self.student_id}"
        )

        print(
            f"Name: {self.name}"
        )

        print(
            f"Course: {self.course}"
        )

        print(
            f"GPA: {self.gpa}"
        )

        print("-" * 30)
```

---

# Step 2: Create Student Objects

## Example Data

```python
student1 = Student(
    "S1001",
    "Alex",
    "Artificial Intelligence",
    3.8
)

student2 = Student(
    "S1002",
    "Emma",
    "Data Science",
    3.5
)

student3 = Student(
    "S1003",
    "John",
    "Cyber Security",
    3.9
)
```

---

# Step 3: Store Objects in a List

A list allows us to manage multiple student records.

---

## Implementation

```python
students = [

    student1,

    student2,

    student3
]
```

---

## Memory Representation

```text
Students List

│

├── Student 1

├── Student 2

└── Student 3
```

---

# Step 4: Serialize the Student List

## Import Pickle

```python
import pickle
```

---

## Save Students to File

```python
with open(
    "students.dat",
    "wb"
) as file:

    pickle.dump(
        students,
        file
    )
```

---

# Understanding What Happens

Before:

```text
Memory
    ↓
Student Objects
```

After:

```text
students.dat
    ↓
Serialized Objects
```

The student list is now permanently stored.

---

# Step 5: Deserialize the Student List

To restore the data:

---

## Load File

```python
with open(
    "students.dat",
    "rb"
) as file:

    loaded_students = (
        pickle.load(file)
    )
```

---

## Memory After Loading

```text
students.dat
     ↓

Loaded Student Objects
```

The objects are reconstructed automatically.

---

# Step 6: Display Student Records

## Implementation

```python
for student in loaded_students:

    student.display_details()
```

---

# Sample Output

```text
ID: S1001
Name: Alex
Course: Artificial Intelligence
GPA: 3.8
------------------------------

ID: S1002
Name: Emma
Course: Data Science
GPA: 3.5
------------------------------

ID: S1003
Name: John
Course: Cyber Security
GPA: 3.9
------------------------------
```

---

# Complete Program

```python
import pickle

class Student:

    def __init__(
        self,
        student_id,
        name,
        course,
        gpa
    ):

        self.student_id = student_id
        self.name = name
        self.course = course
        self.gpa = gpa

    def display_details(self):

        print(
            f"ID: {self.student_id}"
        )

        print(
            f"Name: {self.name}"
        )

        print(
            f"Course: {self.course}"
        )

        print(
            f"GPA: {self.gpa}"
        )

        print("-" * 30)


student1 = Student(
    "S1001",
    "Alex",
    "Artificial Intelligence",
    3.8
)

student2 = Student(
    "S1002",
    "Emma",
    "Data Science",
    3.5
)

student3 = Student(
    "S1003",
    "John",
    "Cyber Security",
    3.9
)

students = [

    student1,

    student2,

    student3
]

with open(
    "students.dat",
    "wb"
) as file:

    pickle.dump(
        students,
        file
    )

with open(
    "students.dat",
    "rb"
) as file:

    loaded_students = (
        pickle.load(file)
    )

for student in loaded_students:

    student.display_details()
```

---

# Challenge Solution

## Highest GPA

```python
highest_gpa = max(

    student.gpa

    for student in loaded_students
)
```

Result:

```text
3.9
```

---

# Lowest GPA

```python
lowest_gpa = min(

    student.gpa

    for student in loaded_students
)
```

Result:

```text
3.5
```

---

# Average GPA

```python
average_gpa = (

    sum(
        student.gpa

        for student in loaded_students
    )

    /

    len(loaded_students)
)
```

Calculation:

```text
(3.8 + 3.5 + 3.9)

÷

3

=

3.73
```

---

# Display Statistics

```python
print(
    "Highest GPA:",
    highest_gpa
)

print(
    "Lowest GPA:",
    lowest_gpa
)

print(
    "Average GPA:",
    round(
        average_gpa,
        2
    )
)
```

---

# Sample Output

```text
Highest GPA: 3.9

Lowest GPA: 3.5

Average GPA: 3.73
```

---

# Complete Challenge Solution

```python
highest_gpa = max(

    student.gpa

    for student in loaded_students
)

lowest_gpa = min(

    student.gpa

    for student in loaded_students
)

average_gpa = (

    sum(
        student.gpa

        for student in loaded_students
    )

    /

    len(loaded_students)
)

print("\nGPA REPORT")
print("----------------")

print(
    "Highest GPA:",
    highest_gpa
)

print(
    "Lowest GPA:",
    lowest_gpa
)

print(
    "Average GPA:",
    round(
        average_gpa,
        2
    )
)
```

---

# Improved Professional Solution

In a real application:

```text
Program Starts
      ↓
Check if students.dat exists
      ↓
Load Existing Students
      ↓
Allow Updates
      ↓
Save Before Exit
```

This creates a true persistent information system.

---

## Checking File Existence

```python
import os

if os.path.exists(
    "students.dat"
):

    with open(
        "students.dat",
        "rb"
    ) as file:

        students = pickle.load(
            file
        )

else:

    students = []
```

This prevents:

```text
FileNotFoundError
```

when the application is started for the first time.

---

# Reflection

This exercise integrates concepts from multiple tutorials.

---

## Classes and Objects

```python
Student
```

was implemented as a class.

---

## Collections

```python
students = []
```

stores multiple objects.

---

## File Handling

```python
open()
```

is used for file operations.

---

## Serialization

```python
pickle.dump()
```

stores objects permanently.

---

## Deserialization

```python
pickle.load()
```

restores objects.

---

## Reporting

Statistics were generated using:

```python
max()

min()

sum()
```

---

# Self-Evaluation Checklist

After completing Exercise 12, you should be able to:

✅ Create custom classes.

✅ Instantiate objects.

✅ Store objects in lists.

✅ Serialize objects using pickle.

✅ Deserialize objects from files.

✅ Implement object persistence.

✅ Generate reports from object collections.

✅ Handle missing files safely.

✅ Build small persistent information systems.

---

# Key Takeaways

This exercise demonstrates a complete persistence workflow:

```text
Create Objects
      ↓

Store in Collection
      ↓

Serialize
      ↓

Save to File
      ↓

Load From File
      ↓

Deserialize
      ↓

Generate Reports
```

These same concepts are used in:

```text
Library Management Systems

Student Information Systems

Inventory Management Systems

Hospital Systems

Machine Learning Model Storage
```

and serve as an important bridge between object-oriented programming and real-world software engineering.
