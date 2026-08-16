# Tutorial 10: Unsupervised Learning and Clustering

## Overview

Unlike supervised learning, where models learn from labelled data, **unsupervised learning** works with data that contains no predefined labels or target values.

The goal of unsupervised learning is to discover:

- Hidden structures
- Natural groupings
- Similarities
- Relationships
- Patterns

One of the most important unsupervised learning techniques is:

```text
Clustering
```

Clustering automatically groups similar objects together and separates dissimilar objects into different groups.

Applications of clustering can be found in:

- Marketing
- Healthcare
- Finance
- Image Processing
- Customer Segmentation
- Biology
- Climate Science
- Information Retrieval

This tutorial introduces clustering, similarity measures, hierarchical clustering, density-based clustering, K-Means, K-Medoids, DBSCAN, OPTICS, and the Elbow Method.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Explain unsupervised learning

✅ Define clustering

✅ Identify real-world clustering applications

✅ Evaluate clustering quality

✅ Understand similarity and distance measures

✅ Explain hierarchical clustering

✅ Distinguish AGNES and DIANA

✅ Interpret dendrograms

✅ Explain density-based clustering

✅ Understand DBSCAN

✅ Understand OPTICS

✅ Explain K-Means clustering

✅ Explain K-Medoids clustering

✅ Apply the Elbow Method

✅ Compare major clustering approaches

---

# 1. What is Unsupervised Learning?

Unsupervised learning is a machine learning approach where no labelled output exists.

---

## Supervised Learning

Contains:

```text
Input Data (X)

and

Output Labels (Y)
```

---

## Unsupervised Learning

Contains:

```text
Input Data Only
```

No target labels are available.

The algorithm must discover hidden structures independently.

---

## Goal

```text
Find Hidden Patterns

Without Prior Labels
```

---

# 2. Why Use Unsupervised Learning?

Many real-world datasets do not contain labels.

Examples:

- Customer purchasing records
- Website visitor behaviour
- Scientific measurements
- Sensor readings
- Social media activity

Organizations want to discover patterns automatically.

---

# 3. What is Clustering?

Clustering is the process of organizing unlabelled data into groups called:

```text
Clusters
```

---

## Definition

A cluster is a collection of objects that are:

```text
Similar Within the Cluster

and

Different From Other Clusters
```

---

# 4. Why Clustering Matters

Clustering helps organizations understand data without manually assigning categories.

---

## Example

A retailer may discover:

```text
High-Spending Customers

Budget Customers

Occasional Buyers
```

without predefined labels.

---

# 5. Applications of Clustering

Clustering has applications across many industries.

---

## Marketing

Customer segmentation and targeted campaigns.

---

## Healthcare

Patient grouping and disease analysis.

---

## Biology

Species classification and taxonomy.

---

## Information Retrieval

Document grouping and search optimization.

---

## Image Processing

Image segmentation and object recognition.

---

## Climate Science

Weather pattern identification.

---

## City Planning

Grouping geographical regions with similar characteristics.

---

## Finance

Market research and customer profiling.

---

# 6. Image Segmentation

One important application is:

```text
Computer Vision
```

---

The goal is to divide images into meaningful regions.

Applications include:

- Medical imaging
- Self-driving cars
- Object detection
- Satellite imagery

---

# 7. What Makes a Good Cluster?

A good clustering solution should maximize similarity within clusters and minimize similarity between clusters.

---

## High Intra-Cluster Similarity

Objects inside a cluster should be very similar.

---

## Low Inter-Cluster Similarity

Different clusters should be clearly distinguishable.

---

# 8. Measuring Cluster Quality

Cluster quality depends on:

### Similarity Measures

How similarity is calculated.

---

### Algorithm Design

How clusters are formed.

---

### Hidden Patterns

The ability to discover meaningful structures.

---

# 9. Similarity and Dissimilarity

Clustering requires methods for comparing objects.

---

## Similarity

Measures how alike two objects are.

---

## Dissimilarity

Measures how different two objects are.

---

Most clustering algorithms use:

```text
Distance Functions
```

---

# 10. Important Distance Measures

Several distance metrics are commonly used.

---

## Euclidean Distance

Straight-line distance between points.

---

## Manhattan Distance

Distance travelled along grid paths.

---

## Minkowski Distance

Generalized distance measure.

---

These metrics determine how clusters are formed.

---

# 11. Euclidean Distance

Most commonly used in clustering.

---

Formula Conceptually:

```text
Straight-Line Distance
Between Two Points
```

---

Applications:

- K-Means
- Hierarchical Clustering
- Data Visualization

---

# 12. Manhattan Distance

Measures movement along horizontal and vertical paths.

---

Example:

```text
Walking Through City Streets
```

instead of travelling directly.

---

Useful when movement is constrained.

---

# 13. Types of Data Used in Clustering

Clustering supports many different data types.

---

## Continuous Variables

Examples:

```text
Height

Weight

Salary
```

---

## Binary Variables

Examples:

```text
Male/Female

True/False
```

---

## Nominal Variables

Examples:

```text
Religion

Nationality
```

---

## Ordinal Variables

Examples:

```text
Low

Medium

High
```

---

## Ratio Variables

Examples:

```text
Population

Revenue

Distance
```

---

# 14. Standardization

Variables often have different scales.

---

Example:

```text
Income = 80,000

Age = 25
```

---

Income dominates distance calculations.

Therefore data is standardized before clustering.

---

## Z-Score Standardization

Transforms data using:

```text
Mean

Standard Deviation
```

---

This ensures variables have comparable scales.

---

# 15. Data Structures Used in Clustering

Two common formats exist.

---

## Data Matrix

Rows:

```text
Objects
```

Columns:

```text
Attributes
```

---

## Dissimilarity Matrix

Stores pairwise distances between all objects.

---

Used extensively in hierarchical clustering.

---

# 16. Major Clustering Approaches

There are four major clustering families.

---

## Partitioning Methods

Examples:

```text
K-Means

K-Medoids
```

---

## Hierarchical Methods

Examples:

```text
AGNES

DIANA
```

---

## Density-Based Methods

Examples:

```text
DBSCAN

OPTICS
```

---

## Grid-Based Methods

Examples:

```text
STING

CLIQUE
```

---

# 17. Hierarchical Clustering

Hierarchical clustering builds a hierarchy of clusters.

---

Output:

```text
Dendrogram
```

---

A dendrogram visualizes how clusters merge or split.

---

# 18. Types of Hierarchical Clustering

Two major approaches exist.

---

## Agglomerative

Bottom-up approach.

---

## Divisive

Top-down approach.

---

# 19. Agglomerative Clustering (AGNES)

AGNES stands for:

```text
Agglomerative Nesting
```

---

Process:

```text
Start With Individual Objects
         ↓
Merge Closest Clusters
         ↓
Repeat
         ↓
One Large Cluster
```

---

This is the most commonly used hierarchical clustering method.

---

# 20. Divisive Clustering (DIANA)

DIANA stands for:

```text
Divisive Analysis
```

---

Process:

```text
One Large Cluster
        ↓
Split
        ↓
More Clusters
        ↓
Individual Objects
```

---

Opposite of AGNES.

---

# 21. Dendrograms

A dendrogram is a tree diagram representing cluster formation.

---

## Purpose

Visualize:

- Cluster merging
- Cluster splitting
- Cluster relationships

---

## Benefit

Allows users to select different numbers of clusters.

---

# 22. Distance Between Clusters

Hierarchical clustering requires methods for measuring cluster-to-cluster distance.

---

# 23. Single Link

Distance between:

```text
Closest Two Points
```

from different clusters.

---

Produces elongated clusters.

---

# 24. Complete Link

Distance between:

```text
Farthest Two Points
```

from different clusters.

---

Produces compact clusters.

---

# 25. Average Link

Uses:

```text
Average Pairwise Distance
```

between clusters.

---

Balances single and complete linkage.

---

# 26. Centroid Linkage

Uses distance between:

```text
Cluster Centroids
```

---

Widely used in numerical datasets.

---

# 27. Medoid Linkage

Uses distance between:

```text
Representative Objects
```

called medoids.

---

Less sensitive to outliers.

---

# 28. Cluster Characteristics

Important cluster properties include:

---

## Centroid

Center point of a cluster.

---

## Radius

Average distance from objects to centroid.

---

## Diameter

Average distance among cluster members.

---

These measurements help evaluate cluster compactness.

---

# 29. Density-Based Clustering

Density-based methods define clusters using density rather than distance.

---

Main idea:

```text
Dense Regions
=
Clusters
```

---

Sparse regions separate clusters.

---

# 30. Advantages of Density-Based Methods

✅ Discover arbitrary shapes

✅ Detect outliers

✅ Handle noise

✅ Flexible clustering boundaries

---

# 31. DBSCAN

DBSCAN stands for:

```text
Density-Based Spatial Clustering
of Applications with Noise
```

---

One of the most popular clustering algorithms.

---

# 32. Core DBSCAN Parameters

---

## Eps (ε)

Maximum neighborhood radius.

---

## MinPts

Minimum number of points required to form a dense region.

---

# 33. DBSCAN Point Types

Three point categories exist.

---

## Core Points

Dense regions.

---

## Border Points

Near dense regions.

---

## Outliers (Noise)

Insufficient neighboring points.

---

# 34. DBSCAN Algorithm

---

### Step 1

Select a point.

---

### Step 2

Find neighboring points within:

```text
Eps
```

---

### Step 3

Check:

```text
MinPts
```

requirement.

---

### Step 4

Grow cluster.

---

### Step 5

Repeat until all points are processed.

---

# 35. Advantages of DBSCAN

✅ Finds clusters of arbitrary shape

✅ Detects noise

✅ No requirement to specify K

✅ Handles outliers naturally

---

# 36. Limitations of DBSCAN

❌ Sensitive to parameter selection

❌ Struggles with varying densities

---

This motivated more advanced methods.

---

# 37. OPTICS

OPTICS stands for:

```text
Ordering Points To Identify
Clustering Structure
```

---

Extension of DBSCAN.

---

Designed to handle:

```text
Different Density Levels
```

more effectively.

---

# 38. Advantages of OPTICS

✅ Better than DBSCAN for varying densities

✅ Reveals clustering structure

✅ Flexible parameter selection

✅ Useful visualization capabilities

---

# 39. K-Means Clustering

K-Means is one of the most widely used partitioning algorithms.

---

Goal:

```text
Partition Data
Into K Clusters
```

---

# 40. K-Means Workflow

K-Means alternates between:

---

### Assignment

Assign points to nearest centroid.

---

### Update

Move centroids to cluster means.

---

Repeat until convergence.

---

# 41. K-Means Algorithm

---

Initial Setup

Choose:

```text
K Clusters
```

---

### Step 1

Initialize centroids.

---

### Step 2

Calculate distances.

---

### Step 3

Assign points.

---

### Step 4

Recalculate centroids.

---

### Step 5

Repeat until stable.

---

# 42. Example of K-Means

Suppose:

```text
K = 2
```

---

The algorithm:

```text
Assign Points
        ↓
Update Centers
        ↓
Assign Again
        ↓
Update Again
        ↓
Converge
```

---

Final clusters emerge through iteration.

---

# 43. Advantages of K-Means

✅ Simple

✅ Fast

✅ Scalable

✅ Easy to implement

✅ Works well for large datasets

---

# 44. Limitations of K-Means

Major weakness:

```text
Sensitive to Outliers
```

---

Extreme values can shift the mean substantially.

---

Requires:

```text
Number of Clusters (K)
```

to be predetermined.

---

# 45. K-Medoids

K-Medoids is similar to K-Means but uses:

```text
Actual Data Objects
```

instead of averages.

---

Representative objects are called:

```text
Medoids
```

---

# 46. Advantages of K-Medoids

✅ Robust to outliers

✅ Uses real observations

✅ More stable in noisy datasets

---

# 47. PAM Algorithm

PAM stands for:

```text
Partitioning Around Medoids
```

---

Process:

### Select Initial Medoids

↓

### Assign Objects

↓

### Swap Medoids

↓

### Evaluate Cost

↓

### Repeat Until No Improvement

---

# 48. Choosing the Correct Number of Clusters

One of the most important practical issues is selecting K.

---

Common solution:

```text
Elbow Method
```

---

# 49. Elbow Method

The Elbow Method evaluates clustering quality using:

```text
Within-Cluster Sum of Squares
(WSS)
```

---

Goal:

```text
Minimize WSS
```

---

# 50. Steps of the Elbow Method

---

### Step 1

Run K-Means with different values of K.

Example:

```text
K = 1 to 10
```

---

### Step 2

Calculate WSS.

---

### Step 3

Plot:

```text
K vs WSS
```

---

### Step 4

Identify the:

```text
Elbow Point
```

---

# 51. Interpreting the Elbow

Initially:

```text
More Clusters
=
Large Improvement
```

---

Beyond a certain point:

```text
Additional Clusters
=
Small Improvement
```

---

This bend forms the:

```text
Elbow
```

---

The elbow often indicates the optimal K.

---

# Comparison of Clustering Methods

| Method | Requires K | Handles Noise | Handles Arbitrary Shapes | Sensitive to Outliers |
|----------|----------|----------|----------|----------|
| K-Means | Yes | No | No | Yes |
| K-Medoids | Yes | Better | No | Less |
| Hierarchical | No | Moderate | Moderate | Moderate |
| DBSCAN | No | Yes | Yes | No |
| OPTICS | No | Yes | Yes | No |

---

# Complete Clustering Workflow

```text
Collect Data
       ↓
Preprocess Data
       ↓
Normalize Features
       ↓
Choose Similarity Measure
       ↓
Select Clustering Algorithm
       ↓
Generate Clusters
       ↓
Evaluate Quality
       ↓
Interpret Results
       ↓
Business Insights
```

---

# Summary

In this tutorial we explored:

- Unsupervised Learning
- Clustering
- Similarity Measures
- Distance Metrics
- Euclidean Distance
- Manhattan Distance
- Hierarchical Clustering
- AGNES
- DIANA
- Dendrograms
- Cluster Linkage Methods
- Density-Based Clustering
- DBSCAN
- OPTICS
- K-Means
- K-Medoids
- PAM
- Outlier Handling
- Elbow Method

Clustering is one of the most powerful techniques in unsupervised learning. By grouping similar objects and discovering hidden structures within data, clustering enables organizations to perform customer segmentation, anomaly detection, image analysis, market research, scientific discovery, and business intelligence without requiring labelled datasets.

---

# Self-Assessment Checklist

✅ Define unsupervised learning.

✅ Explain clustering.

✅ Identify clustering applications.

✅ Explain cluster quality.

✅ Understand distance measures.

✅ Explain hierarchical clustering.

✅ Distinguish AGNES and DIANA.

✅ Interpret dendrograms.

✅ Explain DBSCAN.

✅ Describe core, border, and outlier points.

✅ Explain OPTICS.

✅ Explain K-Means.

✅ Explain K-Medoids.

✅ Compare clustering algorithms.

✅ Apply the Elbow Method.
