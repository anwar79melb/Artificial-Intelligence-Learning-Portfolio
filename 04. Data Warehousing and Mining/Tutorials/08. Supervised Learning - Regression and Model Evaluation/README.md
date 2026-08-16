# Tutorial 08: Supervised Learning - Regression and Model Evaluation

## Overview

Supervised Learning is one of the most important branches of Machine Learning. In supervised learning, a model learns from labelled data, meaning that both the inputs and the correct outputs are known during the learning process.

One of the most widely used supervised learning techniques is:

```text
Regression
```

Regression allows us to predict continuous numerical values such as:

- House prices
- Salary
- Revenue
- Temperature
- Sales volume
- Stock prices

This tutorial focuses on regression analysis, including simple linear regression, multiple regression, gradient descent, model diagnostics, residual analysis, least squares estimation, and prediction techniques.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain regression in machine learning

✅ Differentiate simple and multiple regression

✅ Understand regression equations

✅ Explain slope and intercept

✅ Apply linear regression concepts

✅ Explain gradient descent

✅ Understand bias-variance trade-off

✅ Interpret model diagnostics

✅ Explain residuals

✅ Interpret R²

✅ Understand Residual Standard Error (RSE)

✅ Explain F-statistics

✅ Understand least squares estimation

✅ Explain likelihood estimation

✅ Make predictive inferences using regression models

---

# 1. Supervised Learning Recap

Supervised Learning uses labelled datasets to learn relationships between inputs and outputs.

---

## Components

### Input Variables

Also called:

```text
Predictors

Features

Independent Variables
```

Represented by:

```text
X
```

---

### Output Variable

Also called:

```text
Target

Label

Dependent Variable
```

Represented by:

```text
Y
```

---

## Goal

Learn a function:

```text
Y = f(X)
```

that can accurately predict future values.

---

# 2. What is Regression?

Regression is a predictive modelling technique that analyzes relationships between:

```text
Independent Variables (X)

and

Dependent Variable (Y)
```

---

## Purpose

Regression can be used to:

### Predict Future Values

Example:

```text
Predict House Prices
```

---

### Understand Relationships

Example:

```text
How does income affect happiness?
```

---

### Analyze Trends

Example:

```text
Sales Growth Over Time
```

---

### Identify Cause-and-Effect Relationships

Example:

```text
Advertising Spend
→
Sales Revenue
```

---

# 3. Best Fit Line

The core objective of regression is to identify the:

```text
Best Fit Line
```

A line that minimizes prediction errors across all observations.

---

## Example

```text
          •
        •
      •
    •
  •
─────────────────►
```

The regression line attempts to pass through the overall trend of the data.

---

# 4. Linear Regression

Linear Regression is the simplest form of regression.

It assumes a linear relationship between variables.

---

## Equation

```text
Y = b + kX + e
```

Where:

```text
Y = Dependent Variable

X = Independent Variable

b = Intercept

k = Slope

e = Error
```

---

# 5. Simple Linear Regression

Simple Linear Regression uses:

```text
One Predictor

One Response Variable
```

---

## Example

Predict:

```text
Height
```

from:

```text
Age
```

---

Equation:

```text
Height = b₀ + b₁ × Age + Error
```

---

# 6. Assumptions of Simple Linear Regression

Several assumptions must hold for reliable results.

---

## Linearity

Relationship between X and Y is linear.

---

## Homoscedasticity

Error variance remains constant.

---

## Independence

Observations are independent.

---

## Normality

Errors follow a normal distribution.

---

# 7. Understanding the Regression Equation

The simple regression equation is:

```text
Y = b₀ + b₁X + e
```

---

## b₀ (Intercept)

Predicted value of Y when:

```text
X = 0
```

---

## b₁ (Slope)

Amount that Y changes when X increases by one unit.

---

## e (Error)

Difference between:

```text
Observed Value

and

Predicted Value
```

---

# 8. Example: Income and Happiness

Suppose:

```text
X = Income

Y = Happiness Score
```

---

A positive slope implies:

```text
Higher Income
→
Higher Happiness
```

---

The regression model estimates the strength of this relationship.

---

# 9. Example: Age and Height

Suppose:

```text
X = Age

Y = Height
```

---

Regression model:

```text
Height = b₀ + b₁(Age)
```

---

Interpretation:

As age increases, height is expected to increase.

---

# 10. Slope of the Regression Line

The slope determines the direction of the relationship.

---

## Positive Slope

```text
X ↑
Y ↑
```

Example:

```text
Experience
→
Salary
```

---

## Negative Slope

```text
X ↑
Y ↓
```

Example:

```text
Product Price
→
Customer Demand
```

---

## Zero Slope

No relationship.

Example:

```text
X Changes
Y Remains Constant
```

---

## Undefined Slope

Occurs in a vertical line.

---

# 11. Multiple Regression

Most real-world problems involve more than one predictor.

---

Examples:

```text
House Price
```

depends on:

```text
Bedrooms

Bathrooms

Land Size

Location

Age of Property
```

---

# 12. Multiple Regression Equation

General form:

```text
Y = β₀ + β₁X₁ + β₂X₂ + ... + βₚXₚ
```

---

Where:

```text
Y = Target Variable

X₁...Xₚ = Predictors

β = Coefficients
```

---

# 13. Simple vs Multiple Regression

| Feature | Simple Regression | Multiple Regression |
|----------|----------|----------|
| Predictors | One | Multiple |
| Response Variable | One | One |
| Complexity | Low | Higher |
| Realism | Limited | More Realistic |
| Applications | Basic Problems | Real Business Problems |

---

# 14. Example: House Price Prediction

Predict:

```text
House Price
```

using:

```text
Bedrooms

Bathrooms

Location

Land Area
```

---

Model:

```text
Price

=

β₀

+

β₁(Bedrooms)

+

β₂(Bathrooms)

+

β₃(Location)

+

β₄(Land Size)
```

---

# 15. Regression Geometry

The regression model can be viewed as:

---

## One Predictor

```text
Line
```

---

## Two Predictors

```text
Plane
```

---

## Many Predictors

```text
Hyperplane
```

---

# 16. Gradient Descent

Many machine learning models use:

```text
Gradient Descent
```

for optimization.

---

## Definition

Gradient Descent is an optimization algorithm used to minimize a loss function.

---

## Core Idea

Repeatedly move in the direction of:

```text
Steepest Descent
```

until the minimum error is reached.

---

## Process

```text
Random Starting Point
          ↓
Compute Gradient
          ↓
Update Parameters
          ↓
Reduce Error
          ↓
Repeat
```

---

# 17. Why Gradient Descent Matters

Gradient Descent is widely used in:

- Linear Regression
- Logistic Regression
- Neural Networks
- Deep Learning

---

It is not a model itself.

It is simply:

```text
A Training Method
```

---

# 18. Regression in Scikit-Learn

Popular regression implementations include:

---

## LinearRegression

Uses:

```text
Ordinary Least Squares (OLS)
```

---

## SGD Regressor

Uses:

```text
Stochastic Gradient Descent
```

---

Commonly used for large datasets.

---

# 19. Bias-Variance Trade-Off

A key machine learning concept.

---

## High Bias

Model is too simple.

Result:

```text
Underfitting
```

---

## High Variance

Model is too complex.

Result:

```text
Overfitting
```

---

Goal:

```text
Balance Bias and Variance
```

---

# 20. What is Model Diagnostics?

After building a regression model:

```text
Never Assume It Works Perfectly
```

---

We must evaluate:

- Model fit
- Assumptions
- Prediction quality
- Reliability

---

This process is known as:

```text
Model Diagnostics
```

---

# 21. Why Diagnostics Matter

Potential problems include:

---

## Non-Linearity

Actual relationship isn't linear.

---

## Outliers

Extreme values influence results.

---

## Heteroscedasticity

Error variance is inconsistent.

---

## Missing Predictors

Important variables are omitted.

---

# 22. R² (Coefficient of Determination)

One of the most widely used diagnostic metrics.

---

## Definition

Measures how much variation in Y is explained by the model.

---

## Range

```text
0 ≤ R² ≤ 1
```

---

# 23. Interpreting R²

### R² = 0

Model explains none of the variation.

---

### R² = 1

Model explains all variation.

---

### Example

```text
R² = 0.80
```

means:

```text
80% of variation
is explained
by the model.
```

---

# 24. Residual Sum of Squares (RSS)

Measures the remaining prediction error.

---

Formula Conceptually:

```text
RSS

=

Sum of

(Prediction Errors)²
```

---

Lower values indicate better fit.

---

# 25. Residual Standard Error (RSE)

Measures the average size of residuals.

---

Interpretation:

```text
Smaller RSE
=
More Accurate Predictions
```

---

## Example

If:

```text
RSE = 2
```

predictions are typically off by about two units.

---

# 26. F-Statistic

Used to determine whether predictors are useful.

---

Tests:

```text
Does At Least One Predictor
Help Explain Y?
```

---

If significant:

```text
At Least One Predictor
Contributes Meaningfully
```

---

# 27. Residuals

Residuals represent prediction errors.

---

Formula:

```text
Residual

=

Actual Value

-

Predicted Value
```

---

# 28. Residual Analysis

Residual plots help identify model problems.

---

## Random Scatter

Good indication.

---

## Visible Pattern

Suggests model issues.

---

Possible causes:

- Non-linearity
- Missing variables
- Heteroscedasticity

---

# 29. Residual Plot Interpretation

---

## Residual vs Predictor Plot

Pattern implies:

```text
Relationship Is Not Linear
```

---

## Residual vs Fitted Plot

Pattern implies:

```text
Unequal Error Variance
```

(Heteroscedasticity)

---

# 30. Ordinary Least Squares (OLS)

OLS is the most common estimation method in regression.

---

## Goal

Find coefficients that minimize:

```text
Residual Sum of Squares
```

---

OLS determines the:

```text
Best Fit Line
```

through the data.

---

# 31. Least Squares Principle

OLS minimizes:

```text
Σ(Actual − Predicted)²
```

---

This produces model coefficients.

---

# 32. Likelihood and Regression

Under the assumption:

```text
Errors are normally distributed
```

Maximum Likelihood Estimation (MLE) and OLS produce identical solutions.

---

Therefore:

```text
MLE ≡ OLS
```

for standard linear regression.

---

# 33. Predictions Using Regression

After fitting a model, we can predict outcomes.

---

Example:

```text
Input:

Age = 12
```

---

Model predicts:

```text
Height = 145 cm
```

---

# 34. Prediction Variance

Predictions contain uncertainty.

---

A model provides:

```text
Predicted Value
```

and

```text
Prediction Uncertainty
```

---

# 35. Prediction Intervals

Instead of predicting:

```text
145 cm
```

we may predict:

```text
145 cm ± 5 cm
```

---

Example:

```text
95% Prediction Interval

=
140 cm to 150 cm
```

---

Prediction intervals are more realistic.

---

# 36. Key Questions for Model Evaluation

When evaluating regression models, we should always ask:

---

## Is the model useful?

---

## Are predictors significant?

---

## Does the model fit well?

---

## Are assumptions satisfied?

---

## How accurate are predictions?

---

# Complete Regression Workflow

```text
Collect Data
       ↓
Prepare Dataset
       ↓
Select Predictors
       ↓
Build Regression Model
       ↓
Estimate Coefficients
       ↓
Evaluate R²
       ↓
Analyze Residuals
       ↓
Check Diagnostics
       ↓
Make Predictions
       ↓
Business Decisions
```

---

# Summary

In this tutorial we explored:

- Supervised Learning
- Regression Analysis
- Linear Regression
- Multiple Regression
- Regression Equations
- Slopes and Intercepts
- Gradient Descent
- Bias-Variance Trade-Off
- Model Diagnostics
- Residual Analysis
- R²
- Residual Sum of Squares
- Residual Standard Error
- F-Statistics
- Ordinary Least Squares
- Maximum Likelihood Estimation
- Predictions
- Prediction Intervals

Regression is one of the most important supervised learning techniques and serves as the foundation for many predictive analytics applications. By understanding regression modelling, parameter estimation, model diagnostics, and prediction uncertainty, analysts can build reliable models that support accurate forecasting and informed decision-making.

---

# Self-Assessment Checklist

✅ Define regression.

✅ Explain simple linear regression.

✅ Explain multiple regression.

✅ Interpret slope and intercept.

✅ Describe regression assumptions.

✅ Explain gradient descent.

✅ Describe bias-variance trade-off.

✅ Interpret R².

✅ Understand RSS and RSE.

✅ Explain F-statistics.

✅ Interpret residual plots.

✅ Explain OLS estimation.

✅ Explain likelihood estimation.

✅ Make regression predictions.

✅ Interpret prediction intervals.
