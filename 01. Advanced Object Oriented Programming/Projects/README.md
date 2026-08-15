# Library Management System

## Project Overview

The Library Management System is a console-based software application developed using Object-Oriented Programming principles in Python.

The system was designed to support the day-to-day operations of a community library, including book management, member administration, borrowing transactions, reservations, and record persistence.

The project demonstrates the practical application of advanced object-oriented design techniques, file-based persistence, modular architecture, and defensive programming practices.

---

# Project Objectives

The primary objectives of this project were to:

- Model a real-world library environment using object-oriented design.
- Support both library staff and library members.
- Maintain persistent records between application sessions.
- Implement borrowing and reservation workflows.
- Enforce borrowing policies and business rules.
- Produce a maintainable and extensible software architecture.

---

# Key Features

## Staff Features

Library staff can:

- Search books, members, borrow records, and reservations.
- Create new member accounts.
- Update member information.
- Remove member records.
- Add new book titles.
- Edit book information.
- Remove book records.
- Process borrowing transactions.
- Process returns.
- View overdue items.
- Monitor reservation queues.
- Generate library summary information.

---

## Member Features

Library members can:

- Search books by title.
- Search books by author.
- Search books by category.
- Search books by availability.
- View current borrowed items.
- View reservation history.
- Reserve unavailable books.
- Cancel reservations.
- View important account messages and notifications.

---

# Core System Functionality

The system supports:

- Multiple copies of a single title.
- Real-time availability tracking.
- Reservation management.
- Borrowing limits.
- Input validation.
- Exception handling.
- Persistent data storage.
- User privacy considerations.

Availability is automatically updated whenever:

- A book is borrowed.
- A book is returned.
- A reservation is created.
- A reservation is cancelled.

---

# Software Design

The project follows Object-Oriented Programming principles and emphasizes:

## Encapsulation

Data and behaviour are grouped together inside appropriate classes.

Examples:

```text
Book
Member
Reservation
BorrowRecord
```

---

## Inheritance

Common functionality can be shared through inheritance hierarchies where applicable.

Example:

```text
User
├── Member
└── Staff
```

---

## Polymorphism

Polymorphic behaviour can be used to reduce duplication and improve extensibility.

---

## Composition and Association

The system models real-world relationships through object composition and association.

Examples:

```text
Member HAS BorrowRecords

Book HAS Reservations

Library MANAGES Books
```

---

# System Architecture

The system is organized into several logical components.

```text
Library Management System
│
├── Book Management
├── Member Management
├── Borrow Management
├── Reservation Management
├── Data Persistence
└── Application Services
```

---

# Main Entities

## Book

Stores:

- ISBN
- Title
- Author
- Category
- Number of Copies
- Availability Status

Responsibilities:

- Availability management
- Reservation eligibility
- Inventory tracking

---

## Member

Stores:

- Member ID
- Name
- Contact Information
- Borrowing Status

Responsibilities:

- Borrow books
- Return books
- Manage reservations

---

## Borrow Record

Stores:

- Member Information
- Book Information
- Borrow Date
- Due Date
- Return Date

Responsibilities:

- Loan tracking
- Overdue detection

---

## Reservation

Stores:

- Reservation Details
- Queue Position
- Reservation Status

Responsibilities:

- Reservation tracking
- Queue management

---

# Data Persistence

All data is stored using persistent files so that application information is retained between sessions.

Potential data files include:

```text
Books.dat
Members.dat
Borrows.dat
Reservations.dat
```

Stored information includes:

- Book records
- Member records
- Borrowing history
- Reservation queues

---

# Object-Oriented Concepts Demonstrated

| Concept | Demonstrated |
|----------|-------------|
| Classes and Objects | ✅ |
| Encapsulation | ✅ |
| Inheritance | ✅ |
| Polymorphism | ✅ |
| Composition | ✅ |
| Association | ✅ |
| Collections | ✅ |
| File Handling | ✅ |
| Serialization | ✅ |
| Exception Handling | ✅ |
| Modular Design | ✅ |

---

# Software Engineering Practices

The project incorporates:

- Modular architecture
- Clear class responsibilities
- Low code duplication
- Defensive programming
- Input validation
- Exception handling
- Maintainable naming conventions

---

# Technologies Used

```text
Python 3

Object-Oriented Programming

File Handling

Serialization

Command-Line Interface
```

---

# Learning Outcomes

This project provided practical experience in:

- Object-Oriented Analysis
- Software Design
- Class Modelling
- File Persistence
- Data Management
- Exception Handling
- System Testing
- Requirements Analysis

---

# Future Enhancements

Potential future enhancements include:

- Graphical User Interface (GUI)
- Database integration (SQLite/PostgreSQL)
- User authentication
- Fine and penalty calculations
- Recommendation engine
- Audit logging
- Automated backups
- REST API integration
- Web-based deployment

---

# Academic Context

This project was originally developed as part of an Advanced Object-Oriented Programming course.

The focus of the project was to demonstrate the application of object-oriented software engineering principles in the design and implementation of a realistic information management system.
