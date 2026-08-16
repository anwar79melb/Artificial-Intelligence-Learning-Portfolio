# Tutorial 07: Fundamentals of Machine Learning

## Overview

Machine Learning (ML) is one of the most important branches of Artificial Intelligence (AI). It focuses on developing algorithms that can learn patterns from data and make predictions or decisions without being explicitly programmed for every scenario.

Instead of manually defining every rule, machine learning systems discover relationships directly from historical data.

Examples include:

- Email spam detection
- Credit card fraud detection
- Disease diagnosis
- Product recommendations
- House price prediction
- Customer churn prediction
- Image recognition

Machine Learning is now used extensively in business, healthcare, finance, e-commerce, manufacturing, social media, and scientific research.

This tutorial introduces the fundamental concepts of machine learning, including supervised and unsupervised learning, regression, classification, training and test datasets, model accuracy, confusion matrices, precision, recall, ROC curves, and AUC.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define Machine Learning

✅ Explain different types of Machine Learning

✅ Distinguish supervised and unsupervised learning

✅ Explain regression problems

✅ Explain classification problems

✅ Understand prediction and inference

✅ Calculate Mean Squared Error (MSE)

✅ Differentiate training and test error

✅ Explain model flexibility

✅ Explain interpretability

✅ Understand classification accuracy

✅ Explain confusion matrices

✅ Calculate precision and recall

✅ Interpret ROC curves

✅ Explain AUC

---

# 1. What is Machine Learning?

Machine Learning provides a framework for constructing predictive models directly from data.

Rather than relying entirely on manually written rules, algorithms learn patterns automatically.

---

## Traditional Programming

```text
Rules
     +
Data
     ↓
Answers
```

---

## Machine Learning

```text
Data
     +
Answers
     ↓
Model
```

Later:

```text
New Data
      ↓
Model
      ↓
Prediction
```

---

## Goal of Machine Learning

The ultimate objective is:

```text
Learn Patterns
      ↓
Make Predictions
      ↓
Generalize to New Data
```

---

# 2. Types of Machine Learning

Machine learning can be broadly divided into three categories.

---

## Supervised Learning

Training data contains:

```text
Inputs (X)

and

Known Outputs (Y)
```

---

Examples:

```text
House Price Prediction

Email Classification

Fraud Detection
```

---

## Unsupervised Learning

Data contains:

```text
Inputs Only
```

No labels are available.

The algorithm must discover hidden patterns.

---

Examples:

```text
Customer Segmentation

Clustering

Anomaly Detection
```

---

## Semi-Supervised Learning

Only a small portion of the data is labelled.

The remaining data is unlabelled.

---

Examples:

```text
Medical Imaging

Document Classification

Speech Recognition
```

---

# 3. Supervised Learning

Supervised learning uses labelled examples.

The model learns by observing:

```text
Input
     ↓
Output
```

relationships.

---

## Example

Suppose a dataset contains:

| Study Hours | Exam Score |
|------------|------------|
| 2 | 45 |
| 4 | 60 |
| 6 | 75 |

The machine learns how study time influences performance.

---

## General Structure

```text
Predictors (X)
        ↓
Learning Algorithm
        ↓
Response (Y)
```

---

# 4. Components of Supervised Learning

---

## Inputs (Predictors)

Represented by:

```text
X = (X₁, X₂, X₃, ...)
```

Examples:

- Age
- Income
- Study Hours
- Product Price

---

## Outputs (Responses)

Represented by:

```text
Y
```

Examples:

- Sales
- House Price
- Pass/Fail
- Fraud/Legitimate

---

## Prediction Function

The objective is to learn:

```text
h(X)
```

that predicts:

```text
Y
```

from:

```text
X
```

---

# 5. Goal of Supervised Learning

The purpose is not simply to fit existing data.

The true objective is:

```text
Accurate Future Predictions
```

---

Models should perform well on:

```text
Data Never Seen Before
```

---

This concept is known as:

```text
Generalization
```

---

# 6. Regression vs Classification

The two major supervised learning tasks are:

```text
Regression

Classification
```

---

# 7. Regression

Regression predicts:

```text
Continuous Numerical Values
```

---

Examples:

- House Prices
- Revenue
- Temperature
- Stock Prices
- Sales Volume

---

## Example

```text
Input:
House Size

Output:
House Price
```

---

# 8. Applications of Regression

Regression is commonly used for:

---

## Prediction

Forecast future values.

---

## Trend Analysis

Understand changes over time.

---

## Time Series Analysis

Analyze sequential observations.

---

## Cause-and-Effect Analysis

Understand how variables influence one another.

---

# 9. Regression Model

A common representation is:

```text
Y = f(X) + ε
```

Where:

```text
Y = Output

f(X) = True Relationship

ε = Random Error
```

---

## Interpretation

Real-world relationships are rarely perfect.

Therefore:

```text
Y ≠ f(X)
```

exactly.

Some randomness always exists.

---

# 10. Prediction vs Inference

Regression serves two important purposes.

---

## Prediction

Goal:

```text
Accurately Predict Future Values
```

Example:

```text
Predict house price
for a new property.
```

---

## Inference

Goal:

```text
Understand Relationships
```

Example:

```text
Does income influence spending?
```

---

# 11. Types of Regression

Several regression methods exist.

---

## Linear Regression

Fits a straight-line relationship.

---

## Logistic Regression

Predicts probabilities and classes.

---

## Ridge Regression

Adds regularization to reduce overfitting.

---

## Lasso Regression

Performs variable selection.

---

## Polynomial Regression

Models nonlinear relationships.

---

## Bayesian Regression

Incorporates probabilistic assumptions.

---

# 12. Classification

Classification predicts:

```text
Categories
```

rather than numbers.

---

Examples:

```text
Spam / Not Spam

Fraud / Legitimate

Pass / Fail

Benign / Malignant
```

---

# 13. Classification Examples

---

## Healthcare

Predict:

```text
Benign

or

Malignant
```

tumors.

---

## Finance

Predict:

```text
Fraudulent

or

Legitimate
```

transactions.

---

## Email Filtering

Predict:

```text
Spam

or

Not Spam
```

emails.

---

## News Categorization

Predict categories:

```text
Sports

Finance

Weather

Entertainment
```

---

# 14. Classification Process

Classification usually consists of two stages.

---

## Stage 1: Model Construction

Use labelled training data.

---

Example:

| Rank | Years | Tenured |
|--------|--------|--------|
| Professor | 5 | Yes |
| Assistant | 3 | No |

---

The algorithm builds classification rules.

---

## Stage 2: Prediction

Apply the model to unseen records.

Example:

```text
Professor
4 Years
?
```

Predict:

```text
Tenured = Yes
```

---

# 15. Training and Test Data

Datasets are typically divided into:

---

## Training Set

Used to build the model.

---

## Test Set

Used to evaluate the model.

---

Structure:

```text
Dataset
     ↓
Training Set
     +
Test Set
```

---

# 16. Why Test Data Is Important

A model may memorize training examples.

This is called:

```text
Overfitting
```

---

To evaluate real-world performance:

```text
Use Independent Test Data
```

---

# 17. Mean Squared Error (MSE)

For regression problems, one of the most common evaluation metrics is:

```text
Mean Squared Error
(MSE)
```

---

## Formula

```text
MSE

=

Average of

(Actual - Predicted)²
```

---

# 18. Calculating MSE

Steps:

### Step 1

Build a regression model.

---

### Step 2

Generate predictions.

---

### Step 3

Calculate errors.

```text
Error = Actual - Predicted
```

---

### Step 4

Square the errors.

---

### Step 5

Compute the average.

---

# 19. Interpretation of MSE

---

## Lower MSE

```text
Better Predictions
```

---

## Higher MSE

```text
Poorer Predictions
```

---

Goal:

```text
Minimize MSE
```

---

# 20. Training MSE vs Test MSE

Two different errors are important.

---

## Training MSE

Error measured on training data.

---

## Test MSE

Error measured on unseen test data.

---

# 21. 
