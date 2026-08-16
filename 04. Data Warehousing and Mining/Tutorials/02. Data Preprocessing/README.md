# Tutorial 02: Data Preprocessing

## Overview

Data preprocessing is one of the most important stages in the data warehousing and data mining process. In practice, real-world datasets are rarely clean, complete, or consistent. They often contain missing values, duplicate records, data entry errors, outliers, conflicting information, and redundant attributes.

Even the most advanced data mining or machine learning algorithms cannot produce reliable results when applied to poor-quality data.

A common principle in analytics is:

```text
Garbage In
     ↓
Garbage Out
```

If poor-quality data is used as input, the resulting analysis, predictions, and business decisions will also be poor.

Data preprocessing addresses these challenges by cleaning, integrating, transforming, reducing, and preparing data before analytical techniques are applied.

This tutorial introduces the concepts, methods, and techniques used in data preprocessing and explains why preprocessing is a critical component of successful data mining projects.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain why data preprocessing is necessary

✅ Identify different types of dirty data

✅ Evaluate data quality

✅ Handle missing values

✅ Handle noisy data

✅ Understand data filtering techniques

✅ Explain regression-based smoothing

✅ Understand data integration

✅ Detect data redundancy

✅ Perform correlation analysis

✅ Perform covariance analysis

✅ Explain data reduction

✅ Understand Principal Component Analysis (PCA)

✅ Apply normalization techniques

✅ Explain discretization

✅ Understand concept hierarchies

---

# 1. Why Data Preprocessing?

Real-world data is rarely perfect.

Common problems include:

### Incomplete Data

Missing values or attributes.

Example:

```text
Occupation = NULL
```

---

### Noisy Data

Incorrect or unusual values.

Example:

```text
Salary = -10
```

---

### Inconsistent Data

Conflicting information.

Example:

```text
Age = 42

Birthday = 03/07/1997
```

The age and date of birth cannot both be correct.

---

### Duplicate Records

The same customer may appear multiple times in a database.

---

These issues must be addressed before meaningful analysis can occur.

---

## Importance of Quality Data

```text
Quality Data
      ↓
Quality Analysis
      ↓
Quality Decisions
```

Poor-quality data leads to:

- Incorrect statistics
- Misleading reports
- Weak predictive models
- Poor business decisions

---

# 2. Why Is Data Dirty?

Data quality problems occur for many reasons.

---

## Causes of Missing Data

### Data Not Collected

Some information may not have been recorded.

---

### Not Applicable Values

Certain fields may not apply to all records.

---

### Human Error

Users may forget to enter information.

---

### Hardware or Software Failure

Data may be lost due to system problems.

---

## Causes of Noisy Data

### Faulty Measurement Instruments

Sensors may produce incorrect readings.

---

### Data Entry Errors

Typing mistakes are common.

Example:

```text
Age = 222
```

---

### Data Transmission Errors

Data may become corrupted during transfer.

---

## Causes of Inconsistent Data

### Multiple Data Sources

Different systems may use different formats.

---

### Data Updates

Some records may be updated while others are not.

---

### Duplicate Databases

Different versions of the same record may exist.

---

# 3. Data Quality Dimensions

Data quality can be evaluated from several perspectives.

---

## Accuracy

Is the data correct?

Example:

```text
Salary = $50,000
```

versus

```text
Salary = -$50,000
```

---

## Completeness

Are all required values present?

---

## Consistency

Do all records agree with each other?

---

## Timeliness

Is the data up to date?

---

## Believability

Can the data be trusted?

---

## Interpretability

Can users easily understand the data?

---

# 4. Major Tasks in Data Preprocessing

Data preprocessing consists of four major activities.

---

## Data Cleaning

Correct poor-quality data.

---

## Data Integration

Combine data from multiple sources.

---

## Data Reduction

Reduce the size of data while preserving important information.

---

## Data Transformation

Convert data into suitable formats for analysis.

---

## Pipeline

```text
Raw Data
      ↓
Cleaning
      ↓
Integration
      ↓
Reduction
      ↓
Transformation
      ↓
Data Mining
```

---

# 5. Data Cleaning

Data cleaning aims to improve data quality.

---

## Main Tasks

### Missing Value Handling

Fill or estimate missing values.

---

### Noise Removal

Reduce random errors.

---

### Outlier Detection

Identify unusual observations.

---

### Inconsistency Correction

Resolve conflicting records.

---

# 6. Missing Data

One of the most common preprocessing problems is missing information.

---

## Examples

```text
Income = NULL

Age = ?

Phone Number Missing
```

---

## Causes

- Data entry mistakes
- Equipment malfunction
- Deleted records
- Unrecorded information
- Historical information unavailable

---

# 7. Methods for Handling Missing Data

Several strategies can be used.

---

## Method 1: Ignore the Record

Most commonly used when:

```text
Class Label Is Missing
```

in classification tasks.

---

## Method 2: Manual Completion

A human manually fills in missing values.

---

### Limitations

❌ Time-consuming

❌ Expensive

❌ Impractical for large datasets

---

## Method 3: Use a Global Constant

Example:

```text
Unknown
```

---

## Method 4: Replace with Mean

Example:

```text
Average Income
```

for the dataset.

---

## Method 5: Class Mean

Use the average value for the same category.

Example:

```text
Average Salary
for Engineers
```

rather than all employees.

---

## Method 6: Predict the Value

Use:

- Bayesian methods
- Decision trees
- Machine learning models

to infer missing values.

---

# 8. Noisy Data

Noise refers to random variation or errors in data.

---

## Examples

```text
Temperature = 400°C

Age = -5

Height = 12 metres
```

---

These values are usually unrealistic.

---

## Sources of Noise

- Measurement errors
- Sensor failures
- Data entry mistakes
- Communication failures
- System limitations

---

# 9. Methods for Handling Noisy Data

Several techniques are available.

---

## Filtering

Smooth fluctuating values.

---

## Regression

Approximate data using mathematical models.

---

## Clustering

Detect unusual observations.

---

## Human Inspection

Review suspicious values manually.

---

# 10. Moving Average Filtering

A frequently used smoothing technique.

---

## Example

Original Data

```text
100
108
102
120
95
110
```

---

Moving Average

```text
Average nearby values
```

to reduce fluctuations.

---

## Applications

- Financial analysis
- Stock prices
- Sensor data
- Time-series analysis

---

# 11. Regression Analysis

Regression is another approach to reducing noise.

---

## Definition

Regression models relationships between variables.

---

Example:

```text
Height
     =
Function(Age)
```

---

## Goal

Find a model that best fits observed data.

---

# 12. Linear Regression

The simplest regression model.

---

Equation:

```text
Y = wX + b
```

Where:

```text
w = slope

b = intercept
```

---

Applications:

- Forecasting
- Trend analysis
- Prediction

---

# 13. Multiple Regression

Real-world problems often involve multiple variables.

---

Example:

```text
House Price

=
Bedrooms
+
Bathrooms
+
Floor Area
```

---

General form:

```text
Y = b0 + b1X1 + b2X2 + ...
```

---

# 14. Data Integration

Organizations frequently store information across multiple systems.

---

Examples:

```text
Sales Database

Customer Database

Marketing Database
```

---

Data integration combines these sources into a single coherent dataset.

---

# 15. Challenges in Data Integration

Several problems arise during integration.

---

## Schema Matching

Example:

```text
Customer_ID

Client_ID
```

may refer to the same attribute.

---

## Entity Identification

Example:

```text
Bill Clinton

William Clinton
```

may refer to the same individual.

---

## Data Value Conflicts

Example:

```text
Weight = kilograms

Weight = pounds
```

Different units require transformation.

---

# 16. Data Redundancy

Redundant data frequently appears after integration.

---

## Example

The same customer stored in:

```text
Database A

Database B
```

---

Problems created:

- Increased storage
- Reduced consistency
- Slower analysis

---

# 17. Correlation Analysis

Correlation measures relationships between variables.

---

## Positive Correlation

Both variables increase together.

Example:

```text
Study Hours

Exam Score
```

---

## Negative Correlation

One variable increases while the other decreases.

Example:

```text
Product Price

Demand
```

---

## Zero Correlation

No meaningful relationship.

---

# 18. Pearson Correlation Coefficient

Most commonly used correlation measure.

---

Range:

```text
-1 ≤ r ≤ +1
```

---

Interpretation:

```text
r = +1
Perfect Positive Correlation

r = 0
No Correlation

r = -1
Perfect Negative Correlation
```

---

# 19. Covariance Analysis

Covariance measures whether variables move together.

---

## Positive Covariance

Variables tend to rise together.

---

## Negative Covariance

One tends to rise when the other falls.

---

## Zero Covariance

No linear relationship detected.

---

# 20. Example of Covariance

Suppose two stocks often increase together.

Then:

```text
Cov(A, B) > 0
```

---

Interpretation:

```text
Positive Market Relationship
```

---

Useful in:

- Finance
- Portfolio analysis
- Risk management

---

# 21. Data Reduction

Large datasets can make analysis expensive.

Data reduction creates a smaller dataset while preserving useful information.

---

## Benefits

✅ Faster processing

✅ Lower storage requirements

✅ Improved efficiency

✅ Reduced computational cost

---

# 22. Data Reduction Strategies

Common approaches include:

### Dimensionality Reduction

Remove unnecessary variables.

---

### PCA

Principal Component Analysis.

---

### Feature Selection

Retain only useful attributes.

---

### Sampling

Use representative subsets.

---

### Compression

Reduce storage requirements.

---

### Aggregation

Summarize data.

---

# 23. Principal Component Analysis (PCA)

One of the most important dimensionality reduction techniques.

---

## Goal

Find a smaller set of variables that captures most of the variation in data.

---

## Process

```text
High-Dimensional Data
          ↓
Projection
          ↓
New Components
          ↓
Reduced Data
```

---

## Benefits

✅ Fewer dimensions

✅ Faster analysis

✅ Reduced noise

✅ Better visualization

---

# 24. Attribute Subset Selection

Some attributes provide little value.

---

## Redundant Attributes

Duplicate information.

Example:

```text
Tax Paid

Purchase Price
```

Often strongly related.

---

## Irrelevant Attributes

Provide no useful information.

Example:

```text
Student ID
```

when predicting GPA.

---

Removing such attributes improves efficiency.

---

# 25. Parametric Data Reduction

Statistical models can summarize datasets.

---

Examples:

### Linear Regression

Represent data using a line.

---

### Multiple Regression

Represent data using multiple predictors.

---

### Log-Linear Models

Represent multidimensional probability distributions.

---

# 26. Data Transformation

Data transformation converts data into formats suitable for mining.

---

Examples:

- Scaling
- Normalization
- Aggregation
- Generalization

---

# 27. Normalization

Normalization rescales values into comparable ranges.

---

## Why Normalize?

Example:

```text
Income = 100,000

Age = 25
```

Income dominates analysis because of its scale.

Normalization fixes this issue.

---

# 28. Min-Max Normalization

Transforms values into a fixed range.

Commonly:

```text
0
to
1
```

---

Example:

```text
73,000
```

may become:

```text
0.71
```

---

# 29. Z-Score Normalization

Uses:

```text
Mean

Standard Deviation
```

---

Formula:

```text
Value - Mean
-------------------
Standard Deviation
```

---

Advantages:

✅ Works well when outliers exist.

---

# 30. Decimal Scaling

Moves the decimal point.

---

Example:

```text
65000
```

becomes:

```text
0.65000
```

---

# 31. Discretization

Discretization converts continuous values into categories.

---

Example:

```text
Age
```

↓

```text
Child

Teen

Adult

Senior
```

---

Benefits:

✅ Simpler analysis

✅ Reduced storage

✅ Improved classification

---

# 32. Types of Attributes

---

## Nominal

Unordered categories.

Example:

```text
Colour

Religion
```

---

## Ordinal

Ordered categories.

Example:

```text
Low

Medium

High
```

---

## Numeric

Numerical values.

Example:

```text
Income

Temperature
```

---

# 33. Discretization Methods

---

## Histogram Analysis

Divide values into intervals.

---

## Clustering

Group similar values.

---

## Decision Trees

Create meaningful intervals based on labels.

---

# 34. Histogram Analysis

Histograms divide values into buckets.

---

## Equal Width

All buckets have identical size.

---

## Equal Frequency

All buckets contain similar numbers of observations.

---

Applications:

- Data summarization
- Visualization
- Compression

---

# 35. Concept Hierarchies

Concept hierarchies organize data into multiple abstraction levels.

---

Example:

```text
Street
   ↓
City
   ↓
State
   ↓
Country
```

---

These hierarchies support:

- Data summarization
- Roll-up operations
- OLAP analysis

---

# 36. Automatic Concept Hierarchy Generation

Hierarchies can be generated automatically by examining:

```text
Number of Distinct Values
```

---

Example:

```text
Street
→ Many values

City
→ Fewer values

Country
→ Very few values
```

---

# Complete Data Preprocessing Pipeline

```text
Raw Data
     ↓
Cleaning
     ↓
Missing Value Handling
     ↓
Noise Removal
     ↓
Data Integration
     ↓
Correlation Analysis
     ↓
Data Reduction
     ↓
Transformation
     ↓
Normalization
     ↓
Discretization
     ↓
Prepared Data
```

---

# Summary

In this tutorial we explored:

- Data Preprocessing
- Data Quality
- Missing Values
- Noisy Data
- Data Cleaning
- Data Integration
- Data Redundancy
- Correlation Analysis
- Covariance Analysis
- Data Reduction
- Principal Component Analysis (PCA)
- Attribute Selection
- Normalization
- Discretization
- Histogram Analysis
- Concept Hierarchies

Data preprocessing is one of the most critical stages of the entire data mining process. By cleaning, integrating, reducing, and transforming data before analysis, organizations can significantly improve the quality, accuracy, efficiency, and reliability of their data mining and business intelligence systems.

---

# Self-Assessment Checklist

After completing this tutorial, you should be able to:

✅ Explain why preprocessing is necessary.

✅ Identify incomplete, noisy, and inconsistent data.

✅ Evaluate data quality dimensions.

✅ Apply methods for handling missing values.

✅ Explain noise reduction techniques.

✅ Understand regression smoothing.

✅ Explain data integration challenges.

✅ Detect redundancy in datasets.

✅ Interpret correlation coefficients.

✅ Interpret covariance values.

✅ Explain data reduction strategies.

✅ Describe PCA.

✅ Apply normalization techniques.

✅ Explain discretization.

✅ Understand concept hierarchies.
