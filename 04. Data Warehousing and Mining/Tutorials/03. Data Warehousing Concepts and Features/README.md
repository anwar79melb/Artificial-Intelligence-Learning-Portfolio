# Tutorial 03: Data Warehousing Concepts and Features

## Overview

Organizations generate data from numerous operational systems including sales systems, customer relationship management platforms, banking systems, e-commerce applications, inventory systems, and financial applications.

While operational databases are excellent for processing daily transactions, they are not designed for long-term analysis, reporting, trend discovery, or strategic decision-making.

To support business intelligence and decision support, organizations create **Data Warehouses** that consolidate, integrate, and store historical data from multiple sources.

This tutorial introduces the fundamental concepts of Data Warehousing, the characteristics of a data warehouse, the differences between operational databases and data warehouses, and the role of Online Analytical Processing (OLAP) in business intelligence.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define a Data Warehouse

✅ Explain why organizations need data warehouses

✅ Describe the four characteristics of a Data Warehouse

✅ Distinguish between OLTP and OLAP systems

✅ Explain operational databases

✅ Understand Business Intelligence (BI)

✅ Describe historical data analysis

✅ Understand OLAP queries

✅ Explain decision support systems

✅ Describe the role of data warehouses in modern organizations

---

# 1. What is a Data Warehouse?

A Data Warehouse is a centralized repository that stores integrated, historical, and consolidated data for analytical and decision-support purposes.

A widely accepted definition is provided by Bill Inmon:

```text
A Data Warehouse is a
Subject-Oriented,
Integrated,
Time-Variant,
and Non-Volatile
collection of data
used to support management
decision-making.
```

---

## Purpose of a Data Warehouse

Unlike operational systems that support daily activities, data warehouses support:

- Business Intelligence
- Reporting
- Strategic Planning
- Trend Analysis
- Forecasting
- Decision Making

---

## Simplified View

```text
Operational Systems
         ↓
Data Integration
         ↓
Data Warehouse
         ↓
Analysis
         ↓
Business Intelligence
         ↓
Decision Making
```

---

# 2. Why Do We Need a Data Warehouse?

Organizations often maintain multiple databases.

Examples include:

```text
Sales System

Customer Database

Inventory System

Finance System

Marketing System
```

Each system serves a different operational purpose.

However, management often needs answers to questions such as:

```text
Which products generate highest profit?

Which regions are growing fastest?

How have sales changed over the last 5 years?

Which customers are most valuable?
```

Operational databases are not designed to answer these analytical questions efficiently.

A Data Warehouse provides a solution.

---

# 3. Real-World Examples

## Amazon

Amazon stores and analyzes vast volumes of customer and transaction data.

Applications include:

- Product recommendations
- Personalized marketing
- Inventory optimization
- Demand forecasting

---

## Walmart

Walmart uses warehousing technology to analyze sales information from thousands of stores.

Applications include:

- Demand forecasting
- Dynamic pricing
- Inventory management
- Supply chain optimization

---

## Netflix

Netflix stores viewing behavior and user preferences.

Applications include:

- Recommendation systems
- User behavior analysis
- Content strategy planning

---

# 4. Evolution from Data to Decisions

The purpose of a data warehouse is to convert operational information into business intelligence.

```text
Raw Data
      ↓
Data Cleaning
      ↓
Data Integration
      ↓
Data Warehouse
      ↓
Analytics
      ↓
Knowledge
      ↓
Business Decisions
```

---

# 5. Operational Databases

An operational database is designed to support day-to-day business activities.

Another common term is:

```text
Transactional Database
```

---

## Examples

- Banking systems
- E-commerce websites
- Customer service platforms
- Airline reservation systems
- Student administration systems

---

## Characteristics

### Real-Time Data

Stores current information.

---

### Fast Processing

Supports rapid transactions.

---

### Frequent Updates

Data changes constantly.

---

### High Availability

Must remain available during business operations.

---

### Normalized Design

Reduces redundancy.

---

# 6. Examples of Operational Systems

## Customer Relationship Management (CRM)

Stores:

- Customer details
- Customer interactions
- Service requests

---

## Enterprise Resource Planning (ERP)

Stores:

- Inventory
- Finance
- Accounting
- Human Resources

---

# 7. Operational Processing Example

Consider an airline ticket booking system.

The system must answer questions such as:

```text
Available flights?

Available seats?

Passenger details?

Booking confirmation?
```

Characteristics:

- Real-time responses
- Immediate updates
- Small transactions
- High reliability

---

This type of processing is known as:

```text
Online Transaction Processing
(OLTP)
```

---

# 8. Business Intelligence and Decision Support

Managers often require different information.

Examples:

```text
Most popular routes

Yearly passenger trends

Fuel cost trends

Seasonal performance
```

These questions require:

- Historical data
- Aggregated data
- Complex calculations

---

This is known as:

```text
Decision Support
```

or

```text
Business Intelligence (BI)
```

---

# 9. Benefits of Data Warehousing

A Data Warehouse provides several business advantages.

---

## Integrated Data

Combines information from multiple systems.

---

## Improved Data Quality

Provides consistent and cleaned data.

---

## Historical Intelligence

Supports long-term analysis.

---

## Faster Decision Making

Enables rapid access to business insights.

---

## Higher ROI

Improves strategic planning and efficiency.

---

# 10. Four Core Characteristics of a Data Warehouse

The most important examination topic in Data Warehousing is understanding these four characteristics:

```text
Subject-Oriented

Integrated

Time-Variant

Non-Volatile
```

---

# 11. Subject-Oriented

Data is organized around important business subjects rather than operational processes.

---

## Examples of Subjects

```text
Customer

Sales

Products

Regions

Branches
```

---

## Operational View

An operational system stores data according to applications.

Example:

```text
Order Processing

Inventory

Billing
```

---

## Warehouse View

A warehouse stores data according to business entities.

Example:

```text
Customer

Product

Region

Sales
```

---

## Example

A supermarket warehouse may focus on:

```text
Sales

Products

Stores

Regions
```

rather than transaction-processing functions.

---

# 12. Integrated

A Data Warehouse combines data from multiple heterogeneous sources.

Examples:

```text
Relational Databases

Flat Files

Spreadsheets

ERP Systems

Online Transactions
```

---

## Integration Activities

### Standardization

Example:

```text
USD
AUD
EUR
```

may be converted into one currency.

---

### Naming Consistency

Example:

```text
Cust_ID

Customer_ID

Client_ID
```

must be standardized.

---

### Unit Conversion

Example:

```text
Kilograms

Pounds
```

must be converted consistently.

---

## Goal

Provide a single and consistent version of truth.

---

# 13. Time-Variant

Data warehouses maintain historical information.

---

## Operational Databases

Typically contain:

```text
Current Data
```

---

## Data Warehouses

Typically contain:

```text
Several Years
of Historical Data
```

---

## Example

A manager may analyze:

```text
Sales This Month

Sales Last Year

Sales During Previous Decade
```

---

Time becomes a very important dimension.

Common dimensions include:

```text
Day

Week

Month

Quarter

Year
```

---

# 14. Time Perspective Example

Operational systems answer:

```text
What happened today?
```

---

Data warehouses answer:

```text
What has happened over
the last 5 years?
```

---

This distinction is fundamental to business intelligence.

---

# 15. Non-Volatile

Once data enters a warehouse, it is rarely modified or deleted.

Data is primarily:

```text
Inserted
```

rather than:

```text
Updated

Deleted
```

---

## Operational Systems

Constant modifications occur.

Example:

```text
Customer updates

Inventory updates

Order updates
```

---

## Data Warehouses

Mainly support:

```text
Querying

Reporting

Analysis
```

---

Therefore data remains stable.

---

# 16. Operational Databases vs Data Warehouses

This comparison is one of the most important concepts in the course.

---

| Operational Database (OLTP) | Data Warehouse (OLAP) |
|------------|------------|
| Run the Business | Improve the Business |
| Current Data | Historical Data |
| Frequent Updates | Mostly Read-Only |
| Normalized Structure | Analytical Structure |
| Small Queries | Complex Queries |
| Detailed Data | Summarized Data |
| Transaction Processing | Decision Support |
| Operational Staff | Managers and Analysts |

---

# 17. OLTP (Online Transaction Processing)

OLTP systems support daily operations.

---

## Characteristics

✅ Fast transactions

✅ Current information

✅ Simple queries

✅ Continuous updates

---

## Examples

- Banking
- Shopping carts
- Hotel bookings
- Student enrolment
- Airline reservations

---

# 18. OLAP (Online Analytical Processing)

OLAP systems support business analysis.

---

## Characteristics

✅ Historical data

✅ Aggregated data

✅ Complex queries

✅ Decision support

---

## Examples

- Sales analysis
- Profitability analysis
- Trend analysis
- Forecasting

---

# 19. OLTP vs OLAP Example

Consider a flight company.

---

## OLTP Question

```text
Show available flights
from Melbourne
to Sydney
today.
```

---

## OLAP Question

```text
What are the
top 10 seasonal routes
over the past five years?
```

---

The second question requires a Data Warehouse.

---

# 20. Types of OLAP Queries

Analysts use warehouses to answer various kinds of questions.

---

# Comparison Queries

Compare business performance across periods.

Example:

```text
Sales This Year

vs

Sales Last Year
```

---

# Ranking Queries

Identify:

```text
Top 10 Products

Top 5 Customers

Most Profitable Stores
```

---

# Statistical Queries

Compute:

```text
Total Sales

Average Revenue

Maximum Profit

Minimum Cost
```

---

# Custom Consolidation Queries

Group information into meaningful segments.

Example:

```text
Young Customers

Middle-Aged Customers

Senior Customers
```

and compare purchasing behavior.

---

# 21. Typical Business Questions

Examples include:

```text
Which products perform best?

Which regions generate highest revenue?

Which stores are most profitable?

How are sales changing over time?

Who are our most valuable customers?
```

These questions are difficult to answer using operational databases alone.

---

# 22. Multidimensional Analysis

OLAP systems support analysis across multiple perspectives.

---

Example Dimensions:

```text
Time

Product

Store

Customer
```

---

Example Measure:

```text
Sales Revenue
```

---

Analysts can examine:

```text
Sales by Product

Sales by Store

Sales by Time

Sales by Customer
```

using the same warehouse.

---

# 23. Business Intelligence Ecosystem

A typical BI environment consists of:

```text
Operational Systems
          ↓
Data Cleaning
          ↓
Data Integration
          ↓
Data Warehouse
          ↓
OLAP Analysis
          ↓
Reports
          ↓
Dashboards
          ↓
Decision Making
```

---

# 24. Modern Data Warehouse Workflow

A modern analytics architecture follows:

```text
Data Sources
       ↓
Extraction
       ↓
Transformation
       ↓
Loading (ETL)
       ↓
Data Warehouse
       ↓
BI Tools
       ↓
Reports & Dashboards
       ↓
Business Decisions
```

---

Examples of BI tools include:

- Power BI
- Tableau
- Looker

---

# 25. Data Warehouse Architecture Example

```text
CRM Database
         │
ERP Database
         │
Sales Database
         │
Inventory System
         │
         ▼
Data Integration
         ▼
Data Warehouse
         ▼
Analytics
         ▼
Management Reports
```

---

# 26. Why Data Warehouses Matter

Without data warehouses:

❌ Data remains scattered

❌ Historical analysis becomes difficult

❌ Business reporting becomes slow

❌ Decision making becomes less reliable

---

With data warehouses:

✅ Centralized information

✅ Consistent data

✅ Historical insights

✅ Faster business intelligence

✅ Better strategic planning

---

# Complete Comparison: Run Business vs Improve Business

```text
OLTP
─────
Run Business

Record Transactions

Current Information

Daily Operations
```

```text
OLAP
─────
Improve Business

Analyze Information

Historical Trends

Strategic Decisions
```

---

# Summary

In this tutorial we explored:

- Data Warehouses
- Business Intelligence
- Decision Support Systems
- Operational Databases
- Transaction Processing
- Subject Orientation
- Data Integration
- Time Variance
- Non-Volatility
- OLTP
- OLAP
- Historical Data
- Analytical Processing
- Multidimensional Analysis
- Business Reporting

A Data Warehouse is a centralized repository that supports business intelligence and strategic decision-making. By integrating data from multiple operational systems and preserving historical information, organizations gain the ability to analyze trends, monitor performance, discover opportunities, and make evidence-based decisions that improve business outcomes.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define a Data Warehouse.

✅ Explain why organizations need data warehouses.

✅ Describe Subject-Oriented data.

✅ Explain Integration in data warehouses.

✅ Describe Time-Variant data.

✅ Explain Non-Volatile data.

✅ Differentiate OLTP and OLAP systems.

✅ Explain Business Intelligence.

✅ Understand Decision Support Systems.

✅ Identify common OLAP query types.

✅ Explain the role of historical data.

✅ Describe how data warehouses support strategic decision-making.
