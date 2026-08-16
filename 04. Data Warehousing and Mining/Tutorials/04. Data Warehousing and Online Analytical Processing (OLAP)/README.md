# Tutorial 04: Data Warehousing and Online Analytical Processing (OLAP)

## Overview

After understanding the concepts and characteristics of Data Warehouses, the next step is learning how analytical data is organized and explored.

Traditional databases organize information into tables consisting of rows and columns. While this structure works well for transaction processing, it is not ideal for multidimensional business analysis.

To support business intelligence, data warehouses use multidimensional models that allow analysts to examine data from different perspectives such as:

- Time
- Product
- Customer
- Region
- Store

This multidimensional view enables powerful analytical processing known as:

```text
Online Analytical Processing (OLAP)
```

This tutorial introduces multidimensional data models, data cubes, fact tables, dimension tables, warehouse schemas, OLAP operations, and business analytics techniques used in modern data warehouses.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain multidimensional data models

✅ Define fact tables and dimension tables

✅ Understand data cubes

✅ Explain star schemas

✅ Explain snowflake schemas

✅ Explain fact constellation schemas

✅ Classify OLAP measures

✅ Explain roll-up operations

✅ Explain drill-down operations

✅ Explain slice operations

✅ Explain dice operations

✅ Explain pivot operations

✅ Understand multidimensional business analysis

✅ Apply OLAP concepts to real business scenarios

---

# 1. From Data Warehouse to Analysis

A data warehouse stores historical business data.

However, storing data alone is not enough.

Organizations want answers to questions such as:

```text
What were total sales last year?

Which products generate the highest revenue?

Which regions perform best?

How has profit changed over time?
```

To answer these questions efficiently, data warehouses use:

```text
Multidimensional Data Models
```

---

# 2. Multidimensional Data Model

A multidimensional data model organizes information into:

```text
Facts

and

Dimensions
```

rather than traditional transactional tables.

---

## Main Idea

Business events are analyzed from different perspectives.

Example:

```text
Sales
```

can be analyzed by:

```text
Time

Store

Product

Customer
```

---

## Multidimensional View

```text
            Time
               |
               |
Product -------+------- Store
               |
               |
           Customer

               ↓

             Sales
```

---

This representation forms a:

```text
Data Cube
```

---

# 3. What is a Data Cube?

A Data Cube is a multidimensional representation of warehouse data.

Each dimension represents a business perspective, while the cube contains measurable business information.

---

## Example Dimensions

```text
Time

Product

Store
```

---

## Example Measure

```text
Sales Revenue
```

---

Business users can explore data across all combinations of dimensions.

---

# 4. Fact Tables

A Fact Table is the core table in a multidimensional model.

It stores measurable business events.

---

## Example Fact Table

| Product ID | Customer ID | Units Sold | Unit Price |
|------------|------------|------------|------------|
| 112233 | 12345 | 3 | 100 |
| 112234 | 12346 | 1 | 75 |
| 112235 | 12347 | 2 | 100 |

---

## Characteristics

Fact tables contain:

### Measures

Examples:

```text
Sales

Profit

Revenue

Quantity Sold

Cost
```

---

### Foreign Keys

Used to connect dimensions.

Examples:

```text
Customer_ID

Product_ID

Store_ID

Time_ID
```

---

# 5. Dimension Tables

Dimension tables provide context for facts.

---

## Example Product Dimension

| Product ID | Product Name | Category | Price |
|------------|------------|------------|------------|
| 101 | Laptop | Electronics | 1500 |
| 102 | Phone | Electronics | 900 |

---

## Examples of Dimensions

### Product Dimension

Contains:

```text
Product Name

Category

Brand

Price
```

---

### Customer Dimension

Contains:

```text
Customer Name

Address

Age

Gender
```

---

### Time Dimension

Contains:

```text
Day

Month

Quarter

Year
```

---

### Store Dimension

Contains:

```text
Store Name

Region

Location
```

---

# 6. Facts vs Dimensions

A simple rule:

---

## Facts

Answer:

```text
How Much?
```

Examples:

```text
Revenue

Sales

Profit

Quantity
```

---

## Dimensions

Answer:

```text
Who?

What?

Where?

When?
```

Examples:

```text
Customer

Product

Store

Time
```

---

# 7. Warehouse Schemas

A schema defines how warehouse tables are organized.

There are three major schema types.

---

# 8. Star Schema

The Star Schema is the simplest and most commonly used warehouse design.

---

## Structure

```text
        Time
          |
          |
Customer -- Fact -- Product
          |
          |
        Store
```

---

Fact table is located in the center.

Dimensions surround the fact table.

The structure resembles a star.

---

## Advantages

✅ Simple design

✅ Easy to understand

✅ Fast query performance

✅ Widely adopted

---

## Example

Fact Table:

```text
Sales Fact
```

Dimensions:

```text
Time

Product

Customer

Store
```

---

# 9. Snowflake Schema

A Snowflake Schema is an extension of a Star Schema.

Dimension tables are normalized into multiple related tables.

---

## Example

Instead of:

```text
Customer
```

holding all information,

we separate information into:

```text
Customer
      ↓
Address
      ↓
City
      ↓
Country
```

---

## Structure

```text
          Country
              |
            City
              |
          Address
              |
Customer --- Fact --- Product
              |
            Time
```

---

## Advantages

✅ Less redundancy

✅ Better consistency

✅ Easier maintenance

---

## Disadvantages

❌ More joins

❌ More complex queries

---

# 10. Fact Constellation Schema

Also known as:

```text
Galaxy Schema
```

---

Multiple fact tables share dimensions.

---

## Example

```text
            Product
               |
               |
Sales Fact ----+---- Shipping Fact
               |
               |
             Time
```

---

Shared dimensions reduce redundancy.

---

## Applications

Large enterprises often use fact constellation schemas.

Examples:

- Retail chains
- Banking systems
- Logistics companies

---

# 11. Comparing Schema Designs

| Feature | Star | Snowflake | Fact Constellation |
|----------|----------|----------|----------|
| Complexity | Low | Medium | High |
| Query Speed | Fast | Moderate | Variable |
| Redundancy | Higher | Lower | Moderate |
| Flexibility | Moderate | High | Very High |
| Typical Usage | Most Common | Large Systems | Enterprise Systems |

---

# 12. Measures in Data Cubes

Measures represent numerical values stored within fact tables.

Different measures behave differently during aggregation.

---

Three important categories exist.

---

# 13. Distributive Measures

Can be aggregated directly.

Examples:

```text
SUM()

COUNT()

MIN()

MAX()
```

---

## Example

Sales from multiple stores can be summed directly.

```text
Store A Sales

+

Store B Sales

=

Total Sales
```

---

# 14. Algebraic Measures

Require calculations based on distributive measures.

Examples:

```text
Average

Variance

Standard Deviation
```

---

## Example

Average Sales

```text
Total Sales
     ÷
Total Records
```

---

# 15. Holistic Measures

Require access to the complete dataset.

Examples:

```text
Median

Mode

Rank
```

---

These are more expensive to compute.

---

# 16. What is OLAP?

OLAP stands for:

```text
Online Analytical Processing
```

---

OLAP provides tools for exploring multidimensional warehouse data.

---

## Purpose

```text
Analyze Data

Rather Than

Process Transactions
```

---

OLAP supports:

- Summarization
- Trend Analysis
- Comparisons
- Business Intelligence

---

# 17. OLAP Operations

Five core OLAP operations are used extensively.

---

## Roll-Up

## Drill-Down

## Slice

## Dice

## Pivot

---

# 18. Roll-Up

Roll-Up summarizes detailed information into higher levels.

Also known as:

```text
Drill-Up
```

---

## Example

```text
City
   ↓
State
   ↓
Country
```

---

Business Question:

```text
What are total sales
for Australia?
```

instead of:

```text
What are sales
for Melbourne?
```

---

## Benefits

✅ Higher-level summaries

✅ Executive reporting

✅ Strategic analysis

---

# 19. Real-World Roll-Up Example

Detailed Sales:

```text
Melbourne

Sydney

Perth
```

---

Roll-Up:

```text
Australia Total
```

---

Decision makers frequently use roll-up reports.

---

# 20. Drill-Down

Drill-Down is the reverse of Roll-Up.

---

Move from summary information to detailed information.

---

## Example

```text
Country
   ↓
State
   ↓
City
```

---

Business Question:

```text
Which city
generated highest sales?
```

---

## Benefits

✅ Detailed investigation

✅ Root cause analysis

✅ Operational insights

---

# 21. Real-World Drill-Down Example

Summary:

```text
Australia Sales
```

↓

Detailed:

```text
Victoria
```

↓

More Detailed:

```text
Melbourne
```

---

# 22. Slice Operation

A Slice selects one value from a dimension.

---

## Example

Dimension:

```text
Year
```

Select:

```text
2024
```

---

Result:

```text
Sales Data
for 2024 Only
```

---

A slice reduces the cube into a smaller view.

---

# 23. Real-World Slice Example

Full Cube:

```text
All Products
All Years
All Stores
```

---

Slice:

```text
Year = 2024
```

---

New Cube:

```text
All Products
All Stores
Only Year 2024
```

---

# 24. Dice Operation

Dice selects multiple values from multiple dimensions.

---

## Example

```text
Year = 2024

Region = Victoria

Category = Electronics
```

---

The resulting cube contains only matching records.

---

## Benefits

✅ Focused analysis

✅ Subset exploration

✅ Market segmentation

---

# 25. Slice vs Dice

### Slice

One dimension value.

Example:

```text
Year = 2024
```

---

### Dice

Multiple dimension values.

Example:

```text
Year = 2024

Category = Electronics

Region = Victoria
```

---

# 26. Pivot (Rotate)

Pivot changes the orientation of data.

---

## Before

```text
Rows = Product

Columns = Years
```

---

## After

```text
Rows = Years

Columns = Product
```

---

No data changes.

Only the perspective changes.

---

## Benefits

✅ Alternative viewpoints

✅ Better reporting

✅ Easier interpretation

---

# 27. Common Types of OLAP Queries

Managers regularly perform three categories of analysis.

---

# Comparison Queries

Example:

```text
2024 Sales
vs
2023 Sales
```

---

Purpose:

```text
Measure Growth
```

---

# Ranking Queries

Example:

```text
Top 10 Products

Top 5 Customers

Top Salespeople
```

---

Purpose:

```text
Identify Best Performance
```

---

# Statistical Queries

Examples:

```text
Total Profit

Average Revenue

Maximum Sales

Minimum Cost
```

---

Purpose:

```text
Performance Measurement
```

---

# 28. Custom Consolidation

Custom groups can be created for analysis.

---

Example:

Customer Ages:

```text
Young

Middle-Aged

Senior
```

---

Sales can then be aggregated by customer group.

---

## Applications

- Marketing
- Customer Segmentation
- Sales Analysis

---

# 29. Multidimensional Expressions (MDX)

Many OLAP systems use:

```text
MDX
```

(MultiDimensional eXpressions)

for querying data cubes.

---

MDX works with:

```text
Dimensions

Measures

Hierarchies

Cubes
```

rather than traditional tables.

---

# 30. Analytical Thinking with OLAP

OLAP enables decision makers to answer questions such as:

```text
What is selling well?

Where is growth occurring?

Who are our best customers?

Which products are declining?

Which stores require attention?
```

---

This transforms raw warehouse data into actionable intelligence.

---

# End-to-End Data Warehouse Analytics Pipeline

```text
Operational Systems
          ↓
Data Cleaning
          ↓
Data Integration
          ↓
Data Warehouse
          ↓
Data Cube
          ↓
OLAP Analysis
          ↓
Business Intelligence
          ↓
Strategic Decisions
```

---

# Summary

In this tutorial we explored:

- Multidimensional Data Models
- Data Cubes
- Fact Tables
- Dimension Tables
- Star Schemas
- Snowflake Schemas
- Fact Constellation Schemas
- Cube Measures
- Distributive Measures
- Algebraic Measures
- Holistic Measures
- OLAP
- Roll-Up
- Drill-Down
- Slice
- Dice
- Pivot
- MDX

Data Warehousing provides the foundation for business analytics, while OLAP provides the tools necessary to explore multidimensional data efficiently. Through data cubes, schemas, and OLAP operations, organizations can transform historical data into meaningful insights that support strategic decision-making and business intelligence.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Define a Data Cube.

✅ Distinguish fact tables and dimension tables.

✅ Explain Star Schema architecture.

✅ Explain Snowflake Schema architecture.

✅ Explain Fact Constellation architecture.

✅ Classify distributive, algebraic, and holistic measures.

✅ Explain Roll-Up operations.

✅ Explain Drill-Down operations.

✅ Explain Slice operations.

✅ Explain Dice operations.

✅ Explain Pivot operations.

✅ Understand OLAP systems.

✅ Distinguish OLTP from OLAP.

✅ Explain how OLAP supports Business Intelligence.
