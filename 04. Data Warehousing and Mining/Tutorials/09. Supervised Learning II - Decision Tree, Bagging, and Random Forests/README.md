# Tutorial 09: Supervised Learning II - Decision Trees, Bagging, and Random Forests

## Overview

In previous tutorials, we studied regression models as a major category of supervised learning. Another powerful and widely used supervised learning technique is the **Decision Tree**.

Decision trees are simple, intuitive, and highly interpretable machine learning models that make predictions using a sequence of decisions. They are widely used in:

- Medical diagnosis
- Fraud detection
- Risk assessment
- Customer segmentation
- Credit approval
- Market prediction

Although decision trees are easy to understand, a single decision tree can be unstable and prone to overfitting. To address this limitation, modern machine learning uses **ensemble methods** such as:

- Bagging
- Random Forests
- Boosting

This tutorial introduces decision tree learning, information gain, entropy, classification trees, pruning, bootstrapping, bagging, and random forests.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain decision trees

✅ Describe decision tree induction

✅ Explain recursive binary splitting

✅ Understand entropy and information gain

✅ Explain purity and impurity measures

✅ Build classification trees

✅ Explain tree stopping criteria

✅ Understand overfitting

✅ Explain pruning techniques

✅ Interpret confusion metrics

✅ Understand bootstrapping

✅ Explain bagging

✅ Explain out-of-bag error

✅ Understand random forests

✅ Compare single trees and ensemble models

---

# 1. What is a Decision Tree?

A Decision Tree is a supervised learning model that represents decisions and outcomes using a tree-like structure.

---

## Main Idea

A decision tree repeatedly asks questions about data.

Example:

```text
Passenger Female?
        |
      Yes
        |
    Survived
```

---

Each question divides the dataset into smaller and more homogeneous groups.

---

## General Structure

```text
Root Node
      ↓
Decision
      ↓
Branches
      ↓
Leaf Nodes
      ↓
Predictions
```

---

# 2. Why Decision Trees Are Popular

Decision trees are among the most commonly used machine learning techniques.

---

## Advantages

### Easy to Understand

Rules are highly interpretable.

---

### Minimal Data Preparation

Little preprocessing is required.

---

### Fast Prediction

Once trained, predictions are very efficient.

---

### Handles Different Data Types

Supports:

```text
Numerical Variables

Categorical Variables
```

---

### Feature Importance

Identifies the most important predictors.

---

# 3. Limitations of Decision Trees

Despite their strengths, decision trees have weaknesses.

---

## Overfitting

Large trees often memorize training data.

---

## Instability

Small changes in data may create very different trees.

---

## Computational Cost

Training can become expensive for large datasets.

---

## Poor Generalization

Complex trees often perform poorly on unseen data.

---

# 4. Example: Titanic Survival Prediction

A famous machine learning problem involves predicting survival on the Titanic.

---

## Possible Predictors

```text
Sex

Age

Number of Family Members
```

---

## Target Variable

```text
Survived

or

Did Not Survive
```

---

Typical questions include:

```text
Male or Female?

Age Above 30?

Travelling Alone?
```

---

# 5. Decision Tree Structure

Decision trees consist of a hierarchy of nodes.

---

## Root Node

Starting point of the tree.

---

## Internal Nodes

Represent decision rules.

---

## Branches

Represent outcomes of decisions.

---

## Leaf Nodes

Contain final predictions.

---

Example:

```text
Age < 30?
      |
   Yes / No
```

---

# 6. Decision Tree Induction

Decision tree induction is the process of constructing a tree from training data.

---

## Basic Strategy

A top-down recursive approach is used.

---

Process:

```text
Start with All Data
         ↓
Choose Best Attribute
         ↓
Split Dataset
         ↓
Repeat for Each Branch
         ↓
Stop
```

---

# 7. Decision Tree Learning Algorithm

The general algorithm follows:

---

### Step 1

Place all training examples at the root.

---

### Step 2

Find the best splitting attribute.

---

### Step 3

Partition the dataset.

---

### Step 4

Repeat recursively.

---

### Step 5

Stop when no further useful split exists.

---

# 8. Stopping Conditions

Tree growth stops when:

---

## Condition 1

All records belong to the same class.

---

## Condition 2

No attributes remain.

---

## Condition 3

No training samples remain.

---

## Condition 4

Predefined stopping conditions are reached.

---

# 9. Recursive Binary Splitting

Most decision trees use:

```text
Recursive Binary Splitting
```

---

## Definition

The dataset is repeatedly divided into two groups.

---

Example:

```text
Age ≤ 30

Age > 30
```

---

Each split attempts to improve classification performance.

---

# 10. The Goal of Splitting

The objective is to create groups that are as pure as possible.

---

Example:

Not Ideal:

```text
50% Survived

50% Died
```

---

Ideal:

```text
100% Survived
```

or

```text
100% Died
```

---

This idea leads to:

```text
Purity Measures
```

---

# 11. Entropy

Entropy measures disorder or uncertainty.

---

## High Entropy

Classes are mixed.

Example:

```text
50% Yes

50% No
```

---

## Low Entropy

Classes are nearly pure.

Example:

```text
100% Yes
```

---

# 12. Interpretation of Entropy

---

## Entropy = 0

Pure node.

---

Example:

```text
All Survived
```

---

## High Entropy

Mixed node.

---

Example:

```text
Half Survived

Half Died
```

---

# 13. Information Gain

One of the most important concepts in decision tree learning.

---

## Definition

Information Gain measures how much uncertainty decreases after a split.

---

Formula Conceptually:

```text
Information Gain

=

Entropy Before Split

-

Entropy After Split
```

---

# 14. Choosing the Best Split

The preferred attribute is:

```text
Attribute
With Highest Information Gain
```

---

Example:

Possible attributes:

```text
Age

Sex

Income
```

---

If:

```text
Sex
```

produces the largest reduction in uncertainty,

it becomes the split attribute.

---

# 15. Why Information Gain Works

A good split produces:

✅ More homogeneous groups

✅ Lower uncertainty

✅ Better prediction accuracy

---

Decision trees continue selecting:

```text
Highest Information Gain
```

until stopping criteria are reached.

---

# 16. Continuous Attributes

Many variables are continuous.

Examples:

```text
Age

Income

Height

Weight
```

---

A split point must be selected.

Example:

```text
Age ≤ 35

Age > 35
```

---

# 17. Finding the Best Split Point

Procedure:

---

### Step 1

Sort values.

---

### Step 2

Evaluate possible split points.

---

### Step 3

Calculate Information Gain.

---

### Step 4

Choose the split with:

```text
Highest Information Gain
```

---

# 18. Other Attribute Selection Measures

Decision trees are not limited to Information Gain.

Several alternatives exist.

---

## Gain Ratio

Reduces bias toward attributes with many values.

---

## Gini Index

Measures impurity.

Widely used in CART trees.

---

## CHAID

Uses Chi-Square statistics.

---

## G-Statistic

Based on probability distributions.

---

# 19. Gini Index

The Gini Index is one of the most common impurity measures.

---

## Interpretation

### High Gini

```text
Mixed Classes
```

---

### Low Gini

```text
Pure Classes
```

---

Goal:

```text
Minimize Gini
```

during splitting.

---

# 20. Purity vs Impurity

Decision tree splitting seeks:

```text
Maximum Purity
```

or equivalently:

```text
Minimum Impurity
```

---

Common impurity measures include:

```text
Entropy

Gini Index
```

---

# 21. Classification Trees

Classification Trees predict categorical outcomes.

---

Examples:

```text
Spam / Not Spam

Fraud / Legitimate

Survive / Not Survive
```

---

Prediction Rule:

```text
Assign Most Common Class
in Terminal Node
```

---

# 22. Classification Tree Example

Suppose a leaf contains:

```text
20 Pass

5 Fail
```

---

Prediction becomes:

```text
Pass
```

because it is the majority class.

---

# 23. The Overfitting Problem

Large trees often fit training data perfectly.

---

This causes:

```text
Overfitting
```

---

Symptoms:

✅ Excellent training performance

❌ Poor test performance

---

# 24. Managing Tree Growth

Several techniques reduce overfitting.

---

## Minimum Samples Per Leaf

Example:

```text
At Least 10 Records
```

required in a leaf.

---

## Maximum Depth

Limit:

```text
Tree Height
```

---

# 25. Tree Pruning

Pruning removes unnecessary branches.

---

Goal:

```text
Simpler Tree

Better Generalization
```

---

# 26. Pre-Pruning

Stop tree growth early.

---

Examples:

```text
Maximum Depth

Minimum Samples

Minimum Gain
```

---

Advantage:

✅ Faster trees

---

Disadvantage:

❌ May stop growth too early

---

# 27. Post-Pruning

Build a complete tree first.

Then remove branches.

---

Advantages:

✅ Better performance

✅ Reduces overfitting

✅ Often more accurate

---

# 28. Reduced Error Pruning

Procedure:

---

### Step 1

Start at leaves.

---

### Step 2

Remove a branch.

---

### Step 3

Evaluate performance.

---

### Step 4

Keep the change only if accuracy does not decrease.

---

# 29. Cost Complexity Pruning

Also called:

```text
Weakest Link Pruning
```

---

Uses:

```text
Alpha (α)
```

to balance:

```text
Tree Size

and

Prediction Accuracy
```

---

# 30. Handling Missing Values

Decision trees can accommodate missing data.

---

Methods include:

### Most Common Value

Assign most frequent value.

---

### Probabilistic Assignment

Distribute according to observed probabilities.

---

# 31. Why Decision Trees Scale Well

Decision trees are popular because they:

✅ Learn quickly

✅ Produce understandable rules

✅ Work with databases

✅ Handle large datasets efficiently

---

# 32. Classification Metrics Review

Classification trees are evaluated using confusion matrices.

---

| | Predicted Positive | Predicted Negative |
|----------|----------|----------|
| Actual Positive | TP | FN |
| Actual Negative | FP | TN |

---

# 33. Important Metrics

---

## Accuracy

```text
(TP + TN)
----------
Total
```

---

## Error Rate

```text
(FP + FN)
----------
Total
```

---

## Sensitivity (Recall)

```text
TP
-----
TP + FN
```

---

## Specificity

```text
TN
-----
TN + FP
```

---

## Balanced Accuracy

```text
(Sensitivity + Specificity)
--------------------------
2
```

---

# 34. Single Trees vs Ensembles

A single tree is often unstable.

Machine learning therefore uses:

```text
Ensembles
```

---

## Definition

Combine multiple models to improve prediction quality.

---

# 35. Ensemble Learning

Instead of one tree:

```text
Tree 1

Tree 2

Tree 3

...
```

combined together.

---

Result:

✅ Higher accuracy

✅ Better stability

✅ Lower variance

---

# 36. Bootstrapping

Bootstrapping is:

```text
Random Sampling
With Replacement
```

---

Example:

Original Data:

```text
A B C D E
```

Bootstrap Sample:

```text
A A B D E
```

---

Notice duplicates are allowed.

---

# 37. Bagging

Bagging stands for:

```text
Bootstrap Aggregation
```

---

Process:

```text
Bootstrap Sample
         ↓
Train Tree
         ↓
Repeat Many Times
         ↓
Combine Predictions
```

---

# 38. Why Bagging Works

Individual trees have:

```text
High Variance
```

---

Averaging many trees:

```text
Reduces Variance
```

---

Results become more stable.

---

# 39. Bagging for Classification

Each tree votes.

Example:

```text
Tree 1 → Yes

Tree 2 → Yes

Tree 3 → No
```

---

Final Prediction:

```text
Yes
```

using:

```text
Majority Vote
```

---

# 40. Out-of-Bag Error (OOB)

When bootstrap samples are created:

```text
Some Records
Are Not Selected
```

---

These records become:

```text
Out-of-Bag Samples
```

---

# 41. Why OOB Error Matters

OOB samples provide a built-in test set.

---

Benefits:

✅ No additional validation data needed

✅ Fast evaluation

✅ Reliable accuracy estimate

---

# 42. Random Forests

Random Forests improve bagging further.

---

Problem with bagging:

Trees remain similar because they consider all predictors.

---

Solution:

```text
Random Forest
```

---

# 43. How Random Forests Work

For every split:

```text
Random Subset
of Predictors
```

is selected.

---

Only those predictors are considered.

---

This increases diversity among trees.

---

# 44. Random Forest Workflow

```text
Create Bootstrap Sample
          ↓
Grow Tree
          ↓
Use Random Features
          ↓
Repeat Hundreds of Times
          ↓
Combine Predictions
```

---

# 45. Advantages of Random Forests

✅ High accuracy

✅ Reduced overfitting

✅ Handles large datasets

✅ Handles many variables

✅ Robust to noise

✅ Provides variable importance

---

# 46. Bagging vs Random Forest

| Feature | Bagging | Random Forest |
|----------|----------|----------|
| Bootstrap Samples | Yes | Yes |
| Multiple Trees | Yes | Yes |
| Random Feature Selection | No | Yes |
| Diversity | Lower | Higher |
| Accuracy | Good | Typically Better |

---

# 47. Real-World Applications

Random Forests are used in:

---

## Banking

Fraud detection.

---

## Healthcare

Disease prediction.

---

## Marketing

Customer segmentation.

---

## Insurance

Risk assessment.

---

## Retail

Demand forecasting.

---

# Complete Decision Tree Learning Pipeline

```text
Training Data
       ↓
Feature Selection
       ↓
Information Gain
       ↓
Tree Construction
       ↓
Tree Pruning
       ↓
Classification
       ↓
Performance Evaluation
       ↓
Bagging / Random Forest
       ↓
Improved Predictions
```

---

# Summary

In this tutorial we explored:

- Decision Trees
- Decision Tree Induction
- Recursive Binary Splitting
- Entropy
- Information Gain
- Gini Index
- Purity and Impurity Measures
- Classification Trees
- Tree Depth
- Overfitting
- Pre-Pruning
- Post-Pruning
- Reduced Error Pruning
- Cost Complexity Pruning
- Confusion Metrics
- Bootstrapping
- Bagging
- Out-of-Bag Error
- Random Forests

Decision Trees provide one of the most intuitive approaches to classification and prediction. By combining multiple trees through ensemble methods such as Bagging and Random Forests, machine learning systems achieve greater stability, reduced overfitting, and improved predictive performance while maintaining strong interpretability and practical usefulness.

---

# Self-Assessment Checklist

✅ Define a Decision Tree.

✅ Explain recursive binary splitting.

✅ Calculate information gain conceptually.

✅ Interpret entropy.

✅ Explain the Gini Index.

✅ Understand classification trees.

✅ Describe stopping criteria.

✅ Explain overfitting.

✅ Differentiate pre-pruning and post-pruning.

✅ Explain confusion matrix metrics.

✅ Define bootstrapping.

✅ Explain bagging.

✅ Explain out-of-bag error.

✅ Describe Random Forests.

✅ Compare bagging and random forests.
