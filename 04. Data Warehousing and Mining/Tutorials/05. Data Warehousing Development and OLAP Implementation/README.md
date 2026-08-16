# Tutorial 05: Data Warehouse Development and OLAP Implementation

## Overview

Building a data warehouse is more than simply creating database tables. A successful data warehouse project begins with understanding business requirements, identifying decision-making needs, designing dimensional models, creating fact and dimension tables, and finally enabling analytical processing through OLAP queries.

In this tutorial, we follow a practical case study involving **X-Mart Supermarket**, a retail chain operating multiple stores throughout a city. The organization wants to transform scattered operational data into a centralized analytical system capable of supporting strategic business decisions.

Using this case study, students will learn how to design a data warehouse using dimensional modeling techniques, implement a star schema, define relationships between tables, and perform OLAP analysis.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Understand the data warehouse development lifecycle

✅ Perform requirement analysis

✅ Identify business success factors

✅ Design dimensions and facts

✅ Create a star schema

✅ Implement dimension tables

✅ Implement fact tables

✅ Define primary and foreign keys

✅ Understand star joins

✅ Apply roll-up operations

✅ Apply drill-down operations

✅ Apply slice and dice operations

✅ Perform OLAP-based business analysis

---

# 1. Case Study: X-Mart Supermarket

X-Mart operates multiple supermarket branches across a city.

Every day, thousands of transactions occur involving:

- Customers
- Products
- Stores
- Salespeople

Although large amounts of operational data are collected, management faces an important challenge:

```text
Data Exists

But Insights Do Not
```

Information is scattered across multiple systems and decision-makers cannot easily analyse business performance.

---

## Business Need

Management wants answers to questions such as:

```text
Which stores are most profitable?

Which products sell best?

Which locations generate highest revenue?

How does sales performance change over time?
```

To answer these questions, X-Mart decides to develop a Data Warehouse.

---

# 2. Business Requirements Analysis

The first stage of every warehouse project is:

```text
Requirements Analysis
```

The objective is to understand:

- Business goals
- Decision-making needs
- Key performance indicators (KPIs)
- Reporting requirements

---

## Typical Questions

Management may ask:

```text
What is the daily profit of each store?

Which products have highest demand?

On which days are sales highest?

How do weekend and weekday sales differ?

What are the yearly growth trends?
```

---

# 3. Business Success Factors

The warehouse must support several important business objectives.

---

## Profit Analysis

Understand profitability at multiple levels.

Examples:

```text
Daily Profit

Monthly Profit

Quarterly Profit

Yearly Profit
```

---

## Product Analysis

Identify:

```text
Best Selling Products

Low Performing Products

Popular Categories
```

---

## Location Analysis

Determine:

```text
Best Performing Stores

Highest Revenue Locations

Regional Trends
```

---

## Trend Analysis

Monitor:

```text
Growth

Decline

Seasonal Behaviour

Customer Demand Patterns
```

---

# 4. Data Warehouse Development Lifecycle

Warehouse development follows a structured process.

---

## Phase 1

Requirements Analysis

---

## Phase 2

Dimensional Modeling

---

## Phase 3

Schema Design

---

## Phase 4

Data Loading

---

## Phase 5

OLAP Analysis

---

## Complete Lifecycle

```text
Requirements Analysis
           ↓
Dimensional Modelling
           ↓
Schema Design
           ↓
Table Creation
           ↓
Data Loading
           ↓
OLAP Processing
           ↓
Business Intelligence
```

---

# 5. Dimensional Modeling

Dimensional modeling is the foundation of warehouse design.

It focuses on two major components:

```text
Dimensions

and

Facts
```

---

# 6. Dimensions

Dimensions provide descriptive information.

They answer business questions such as:

```text
Who?

What?

Where?

When?
```

---

## Examples

### Customer

```text
Name

Gender

Location
```

---

### Store

```text
Store Name

City

Country
```

---

### Product

```text
Product Name

Category

Price
```

---

### Salesperson

```text
Name

Department
```

---

# 7. Facts

Facts represent measurable business events.

---

## Examples

```text
Sales Amount

Revenue

Quantity Sold

Profit
```

---

Facts become the basis of analytical processing.

---

# 8. The X-Mart Star Schema

X-Mart adopts a:

```text
Star Schema
```

because it is simple and efficient.

---

## Core Components

### Dimension Tables

```text
dim_customer

dim_store

dim_product

dim_salesperson
```

---

### Fact Table

```text
fact_productsales
```

---

## Structure

```text
         Customer
              |
              |
Store --- Fact --- Product
              |
              |
         Salesperson
```

---

# 9. Customer Dimension

The customer dimension describes customers.

---

## Example Attributes

```text
customer_id

customer_name

gender

city

state

country
```

---

## Business Questions

```text
Which gender purchases most products?

Which cities generate highest revenue?

Which customers buy most frequently?
```

---

# 10. Store Dimension

The store dimension contains information about stores.

---

## Example Attributes

```text
store_id

store_name

store_location

city

state

country
```

---

## Business Questions

```text
Which store performs best?

Which city generates highest profit?
```

---

# 11. Product Dimension

The product dimension stores product information.

---

## Example Attributes

```text
product_id

product_name

category

brand

price
```

---

## Analysis Examples

```text
Top Products

Category Performance

Sales by Product
```

---

# 12. Salesperson Dimension

This dimension describes employees involved in sales transactions.

---

## Example Attributes

```text
salesperson_id

name

department

store_id
```

---

## Analysis Examples

```text
Employee Performance

Sales by Employee

Productivity Reports
```

---

# 13. Fact Product Sales Table

The fact table stores transactional business events.

---

## Example Columns

```text
transaction_id

invoice_number

transaction_time

store_id

customer_id

product_id

salesperson_id

quantity
```

---

## Measures

Examples include:

```text
Quantity

Revenue

Profit

Sales Amount
```

---

# 14. Primary Keys and Foreign Keys

Warehouse tables must be related through keys.

---

## Primary Keys

Uniquely identify records.

Examples:

```text
customer_id

store_id

product_id
```

---

## Foreign Keys

Connect fact tables to dimensions.

Examples:

```text
customer_id

store_id

product_id

salesperson_id
```

---

# 15. Warehouse Relationship Structure

The fact table acts as the center of the schema.

```text
fact_productsales
         |
         ├── dim_customer
         |
         ├── dim_product
         |
         ├── dim_store
         |
         └── dim_salesperson
```

---

This structure supports multidimensional analysis.

---

# 16. Building the Warehouse

After schema design, implementation begins.

---

## Step 1

Create all dimension tables.

---

## Step 2

Create the fact table.

---

## Step 3

Define primary keys.

---

## Step 4

Define foreign key relationships.

---

## Step 5

Generate DDL statements.

---

## Step 6

Execute the schema.

---

## Step 7

Load warehouse data.

---

# 17. DDL Generation

DDL stands for:

```text
Data Definition Language
```

---

DDL contains SQL statements such as:

```sql
CREATE TABLE
```

```sql
ALTER TABLE
```

```sql
ADD CONSTRAINT
```

---

The generated DDL automatically creates warehouse structures.

---

# 18. Loading Warehouse Data

After schema creation:

```text
Warehouse Tables
      ↓
Insert Data
      ↓
Validate Data
      ↓
Begin Analysis
```

---

Typical sources include:

- Transaction systems
- Operational databases
- CSV files
- ETL processes

---

# 19. Star Joins

Most warehouse queries require joining dimensions to facts.

---

## Example

```text
fact_productsales
         ↓
Join Customer
         ↓
Join Product
         ↓
Join Store
         ↓
Analytical Result
```

---

This type of query is called a:

```text
Star Join
```

---

# 20. OLAP Analysis on the Warehouse

Once data is loaded, management can start analyzing information.

Examples include:

```text
Sales Performance

Store Performance

Product Performance

Customer Behaviour
```

---

# 21. Roll-Up Analysis

Roll-up summarises detailed records.

---

## Example

Sales by Product:

```text
Laptop = 500

Phone = 600

TV = 300
```

---

Roll-Up Result:

```text
Total Sales = 1400
```

---

## Business Question

```text
What are total sales by product?
```

---

# 22. Drill-Down Analysis

Drill-down moves towards greater detail.

---

## Example

```text
Store Sales
```

↓

```text
Store + Product Sales
```

↓

```text
Store + Product + Customer Sales
```

---

Business users can investigate specific causes behind performance.

---

# 23. Slice Operation

A slice selects one dimension value.

---

## Example

```text
City = Ahmedabad
```

---

Result:

```text
Only Ahmedabad Data
```

---

This creates a smaller analytical view.

---

# 24. Dice Operation

Dice selects multiple values across dimensions.

---

## Example

```text
City = Ahmedabad

Gender = Male
```

---

Result:

```text
Male Customers
Within Ahmedabad Stores
```

---

This produces a focused subset of business information.

---

# 25. Practical OLAP Queries

Typical warehouse queries include:

---

## Product Analysis

```text
Total Sales by Product
```

---

## Store Analysis

```text
Total Sales by Store
```

---

## Customer Analysis

```text
Total Sales by Customer
```

---

## Combined Analysis

```text
Store

Product

Customer
```

analyzed together through drill-down operations.

---

# 26. Business Questions Supported

The warehouse enables management to answer:

```text
Which products sell most?

Which stores perform best?

Which customers buy most?

Which regions generate highest revenue?

How is performance changing over time?
```

---

# Complete Warehouse Architecture

```text
Operational Systems
          ↓
Data Cleaning
          ↓
Data Integration
          ↓
Dimension Tables
          ↓
Fact Tables
          ↓
Star Schema
          ↓
Data Warehouse
          ↓
OLAP Queries
          ↓
Business Intelligence
          ↓
Decision Making
```

---

# Summary

In this tutorial we explored:

- Data Warehouse Development
- Requirements Analysis
- Business Success Factors
- Dimensional Modeling
- Dimension Tables
- Fact Tables
- Star Schema Design
- Primary Keys
- Foreign Keys
- DDL Generation
- Data Loading
- Star Joins
- Roll-Up
- Drill-Down
- Slice
- Dice
- OLAP Querying

A successful data warehouse begins with understanding business requirements and ends with delivering actionable insights. By transforming operational data into a structured analytical environment, organizations can make better decisions, identify trends, improve profitability, and gain a competitive advantage.

---

# Self-Assessment Checklist

✅ Explain the warehouse development lifecycle.

✅ Conduct requirements analysis.

✅ Identify business success factors.

✅ Design dimension tables.

✅ Design fact tables.

✅ Explain star schema architecture.

✅ Distinguish facts and dimensions.

✅ Define primary keys.

✅ Define foreign keys.

✅ Explain star joins.

✅ Apply roll-up analysis.

✅ Apply drill-down analysis.

✅ Apply slice analysis.

✅ Apply dice analysis.

✅ Understand how OLAP supports business intelligence.
