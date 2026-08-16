# Tutorial 06: Frequent Pattern Mining and Association Rule Mining

## Overview

One of the most valuable goals of data mining is discovering hidden relationships within large datasets.

Businesses, healthcare organizations, scientific researchers, e-commerce platforms, and social networks are often interested in questions such as:

```text
Which products are frequently purchased together?

Which customer behaviors tend to occur together?

Which DNA sequences appear together?

Which webpages are frequently visited together?
```

Frequent Pattern Mining provides techniques for discovering these recurring relationships.

The most famous application of frequent pattern mining is:

```text
Market Basket Analysis
```

which identifies products that customers often purchase together.

This tutorial introduces frequent patterns, association rules, support, confidence, closed patterns, maximal patterns, the Apriori algorithm, and the FP-Growth algorithm.

---

# Learning Outcomes

After completing this tutorial, you should be able to:

✅ Define frequent patterns

✅ Explain frequent itemsets

✅ Calculate support

✅ Calculate confidence

✅ Generate association rules

✅ Distinguish closed patterns from maximal patterns

✅ Explain the downward closure property

✅ Understand Apriori pruning

✅ Explain the Apriori algorithm

✅ Explain FP-Growth

✅ Understand FP-Trees

✅ Compare Apriori and FP-Growth

✅ Apply frequent pattern mining to business problems

---

# 1. Market Basket Analysis

Market Basket Analysis studies customer purchasing behavior.

The objective is to discover items that are frequently bought together.

---

## Example

A supermarket may discover:

```text
Beer
+
Diapers
```

are frequently purchased together.

---

This knowledge can be used for:

- Product placement
- Recommendation systems
- Cross-selling
- Promotions
- Marketing campaigns

---

## Example Questions

```text
Customers who buy a laptop
often buy what else?

What products should be promoted together?

What products are frequently purchased together?
```

---

# 2. What is Frequent Pattern Mining?

A Frequent Pattern is a pattern that appears repeatedly in a dataset.

Patterns can represent:

- Items
- Itemsets
- Sequences
- Substructures
- Customer behaviours

---

## Definition

```text
Frequent Pattern

=
A pattern that occurs
frequently in a dataset
```

---

# 3. Why is Frequent Pattern Mining Important?

Frequent patterns reveal hidden relationships within data.

These relationships support many other data mining tasks.

---

## Applications

### Association Analysis

Discover relationships between items.

---

### Classification

Use patterns as predictive features.

---

### Clustering

Group similar records.

---

### Sequential Pattern Analysis

Analyze events over time.

---

### Web Mining

Examine browsing behavior.

---

### Bioinformatics

Analyze biological sequences.

---

# 4. Important Applications

Frequent Pattern Mining is used in:

---

## Retail

- Market basket analysis
- Store layout optimization
- Product bundling

---

## E-Commerce

- Recommendation systems
- Cross-selling

---

## Web Analytics

- User click patterns
- Navigation behavior

---

## Healthcare

- Disease pattern analysis
- Drug response analysis

---

## Biology

- DNA sequence mining
- Gene pattern discovery

---

# 5. Itemsets

The basic unit of frequent pattern mining is the:

```text
Itemset
```

---

## Definition

An itemset is a collection of one or more items.

---

## Examples

```text
{Beer}
```

---

```text
{Beer, Diaper}
```

---

```text
{Beer, Diaper, Milk}
```

---

# 6. K-Itemsets

A k-itemset contains exactly:

```text
k Items
```

---

Examples:

### 1-Itemset

```text
{Beer}
```

---

### 2-Itemset

```text
{Beer, Diaper}
```

---

### 3-Itemset

```text
{Beer, Diaper, Milk}
```

---

# 7. Support

Support measures how frequently an itemset appears within the dataset.

---

## Formula

```text
Support(X)

=
Transactions Containing X
-------------------------
Total Transactions
```

---

Higher support indicates a more common pattern.

---

# 8. Example of Support

Suppose there are:

```text
5 Transactions
```

and:

```text
{Beer, Diaper}
```

appears in:

```text
3 Transactions
```

Then:

```text
Support

=
3 / 5

=
60%
```

---

# 9. Frequent Itemsets

An itemset is considered frequent when its support exceeds a predefined threshold.

---

## Minimum Support

```text
MinSup
```

is the minimum frequency required.

---

Example:

```text
MinSup = 50%
```

---

Any itemset with support greater than or equal to:

```text
50%
```

is considered frequent.

---

# 10. Example Transaction Database

| Transaction ID | Items |
|----------|----------|
| 10 | Beer, Nuts, Diaper |
| 20 | Beer, Coffee, Diaper |
| 30 | Beer, Diaper, Eggs |
| 40 | Nuts, Eggs, Milk |
| 50 | Nuts, Coffee, Diaper, Eggs, Milk |

---

Assume:

```text
MinSup = 50%
```

---

# 11. Frequent 1-Itemsets

Support Counts:

```text
Beer = 3

Nuts = 3

Diaper = 4

Eggs = 3
```

---

Support Values:

```text
Beer = 60%

Nuts = 60%

Diaper = 80%

Eggs = 60%
```

---

All satisfy:

```text
MinSup = 50%
```

Therefore:

```text
Frequent 1-Itemsets
```

---

# 12. Frequent 2-Itemsets

Example:

```text
{Beer, Diaper}
```

appears in:

```text
3 Transactions
```

Support:

```text
3 / 5

=
60%
```

---

Since:

```text
60% > 50%
```

the itemset is frequent.

---

# 13. Association Rules

Association Rules identify relationships among frequent itemsets.

---

## General Form

```text
X → Y
```

Meaning:

```text
If X occurs,

Y tends to occur.
```

---

# 14. Confidence

Confidence measures the reliability of a rule.

---

## Formula

```text
Confidence(X → Y)

=
Support(X ∪ Y)
--------------
Support(X)
```

---

Confidence is the probability that Y appears when X appears.

---

# 15. Example Association Rule

Rule:

```text
Beer → Diaper
```

---

Support:

```text
60%
```

---

Confidence:

```text
100%
```

---

Interpretation:

```text
Every customer
who purchased Beer
also purchased Diapers.
```

---

# 16. Another Example

Rule:

```text
Diaper → Beer
```

---

Support:

```text
60%
```

---

Confidence:

```text
75%
```

---

Interpretation:

```text
75% of customers
who buy Diapers
also buy Beer.
```

---

# 17. Closed Patterns

Large datasets generate huge numbers of frequent patterns.

A compressed representation is needed.

---

## Definition

An itemset is closed if:

```text
It is frequent

and

No larger frequent itemset
has the same support.
```

---

# 18. Advantages of Closed Patterns

✅ Compact representation

✅ No information loss

✅ Preserves support values

✅ Reduces storage

---

Because support can still be recovered, closed patterns are considered:

```text
Lossless Compression
```

---

# 19. Maximal Patterns

Another way to reduce pattern count.

---

## Definition

An itemset is maximal if:

```text
It is frequent

and

No larger frequent itemset
exists.
```

---

# 20. Advantages and Disadvantages

### Advantages

✅ Very compact

✅ Fewer patterns

✅ Lower storage costs

---

### Disadvantage

❌ Actual support information may be lost

---

Therefore maximal patterns provide:

```text
Lossy Compression
```

---

# 21. Closed vs Maximal Patterns

| Feature | Closed Patterns | Maximal Patterns |
|----------|----------|----------|
| Preserve Support | Yes | No |
| Compression | Good | Better |
| Information Loss | None | Some |
| Preferred for Analysis | Often | Sometimes |

---

# 22. Downward Closure Property

One of the most important principles in frequent pattern mining.

---

## Principle

```text
Every subset
of a frequent itemset
must also be frequent.
```

---

Example:

If:

```text
{Beer, Diaper, Nuts}
```

is frequent,

then:

```text
{Beer, Diaper}
```

must also be frequent.

---

# 23. Apriori Pruning Principle

The downward closure property leads to:

```text
Apriori Principle
```

---

## Principle

```text
If an itemset
is infrequent,

all larger supersets
must also be infrequent.
```

---

Example:

If:

```text
{Beer, Nuts}
```

is not frequent,

then:

```text
{Beer, Nuts, Milk}
```

cannot be frequent.

---

Thus we eliminate many candidates.

---

# 24. Why Apriori Works

Without pruning:

```text
Millions of possibilities
```

may need evaluation.

---

With pruning:

```text
Many candidates
are removed immediately.
```

---

This makes mining scalable.

---

# 25. Apriori Algorithm

Apriori is one of the most important frequent pattern mining algorithms.

---

## Main Idea

```text
Generate Candidates

Count Support

Prune Infrequent Patterns

Repeat
```

---

# 26. Apriori Workflow

```text
Find Frequent 1-Itemsets
            ↓
Generate 2-Item Candidates
            ↓
Count Supports
            ↓
Prune
            ↓
Generate 3-Item Candidates
            ↓
Count Supports
            ↓
Prune
            ↓
Continue Until No Patterns Remain
```

---

# 27. Example of Apriori

Transaction Database:

```text
T1 = A C D

T2 = B C E

T3 = A B C E

T4 = B E
```

Assume:

```text
MinSup = 2
```

---

First scan finds:

```text
A

B

C

E
```

as frequent.

---

Second scan generates:

```text
AC

BC

BE

CE
```

---

Third scan produces:

```text
BCE
```

---

Eventually all frequent itemsets are discovered.

---

# 28. Candidate Generation

Apriori generates larger candidates from smaller frequent patterns.

---

Example:

Frequent 3-itemsets:

```text
ABC

ABD
```

---

Generate:

```text
ABCD
```

---

This process is called:

```text
Self-Joining
```

---

# 29. Candidate Pruning

Generated candidates are validated before support counting.

---

Example:

Candidate:

```text
ACDE
```

If:

```text
ADE
```

is not frequent,

then:

```text
ACDE
```

must be removed.

---

This dramatically reduces computational cost.

---

# 30. Limitations of Apriori

Despite its importance, Apriori has major drawbacks.

---

## Multiple Database Scans

Database must be scanned repeatedly.

---

## Huge Candidate Sets

Many candidate itemsets are generated.

---

## Expensive Support Counting

Support must be computed repeatedly.

---

# 31. Improving Apriori

Several improvements have been proposed.

---

## Partitioning

Reduce database scans.

---

## Dynamic Itemset Counting (DIC)

Reduce scan costs.

---

## Direct Hashing and Pruning (DHP)

Reduce candidate generation.

---

# 32. FP-Growth

FP-Growth is designed to overcome Apriori limitations.

---

Instead of generating candidates:

```text
Compress Data
```

into an:

```text
FP-Tree
```

---

# 33. Main Idea of FP-Growth

```text
Build FP-Tree
         ↓
Generate Conditional Trees
         ↓
Discover Frequent Patterns
```

---

No large candidate generation is required.

---

# 34. FP-Growth Process

## Step 1

Scan database.

---

## Step 2

Find frequent items.

---

## Step 3

Construct FP-Tree.

---

## Step 4

Generate conditional pattern bases.

---

## Step 5

Generate conditional FP-Trees.

---

## Step 6

Recursively discover patterns.

---

# 35. FP-Tree

An FP-Tree is a compressed representation of transaction data.

---

It stores:

```text
Frequent Items

Shared Paths

Support Counts
```

---

# 36. Benefits of FP-Trees

### Completeness

Preserves important information.

---

### Compactness

Stores only frequent items.

---

### Efficiency

Reduces processing overhead.

---

### Scalability

Handles large datasets more effectively.

---

# 37. Conditional Pattern Base

A conditional pattern base contains prefix paths associated with an item.

---

Example:

For item:

```text
P
```

collect all paths leading to:

```text
P
```

---

These become the basis for further mining.

---

# 38. Conditional FP-Tree

Conditional pattern bases are converted into:

```text
Conditional FP-Trees
```

---

These allow recursive pattern growth.

---

# 39. Frequent Pattern Growth

FP-Growth recursively expands patterns.

---

Example:

If:

```text
ABC
```

is frequent

and:

```text
D
```

frequently occurs with:

```text
ABC
```

then:

```text
ABCD
```

becomes a new frequent pattern.

---

# 40. Apriori vs FP-Growth

| Characteristic | Apriori | FP-Growth |
|----------|----------|----------|
| Candidate Generation | Yes | No |
| Database Scans | Many | Few |
| Memory Usage | Higher | Lower |
| Speed | Slower | Faster |
| Scalability | Moderate | High |
| Dataset Compression | No | Yes |

---

# 41. Practical Tools

Python libraries can implement frequent pattern mining.

---

## Apriori

```python
from efficient_apriori import apriori
```

---

## FP-Growth

```python
import pyfpgrowth
```

---

These libraries automate itemset mining and rule generation.

---

# 42. Real-World Applications

Frequent Pattern Mining is widely used in:

---

## Retail

Market basket analysis.

---

## E-Commerce

Recommendation systems.

---

## Banking

Fraud pattern identification.

---

## Healthcare

Disease correlation analysis.

---

## Telecommunications

Customer behavior analysis.

---

## Bioinformatics

DNA sequence mining.

---

# Complete Frequent Pattern Mining Pipeline

```text
Transaction Database
          ↓
Frequent Itemsets
          ↓
Support Calculation
          ↓
Association Rules
          ↓
Confidence Evaluation
          ↓
Interesting Patterns
          ↓
Business Intelligence
```

---

# Summary

In this tutorial we explored:

- Frequent Patterns
- Market Basket Analysis
- Itemsets
- Support
- Confidence
- Association Rules
- Closed Patterns
- Maximal Patterns
- Downward Closure Property
- Apriori Principle
- Candidate Generation
- Candidate Pruning
- Apriori Algorithm
- FP-Growth
- FP-Trees
- Conditional Pattern Bases
- Conditional FP-Trees

Frequent Pattern Mining is a fundamental area of data mining that discovers recurring relationships in data. These patterns provide valuable business insights, support recommendation systems, enable association analysis, and form the foundation for many advanced analytics applications.

---

# Self-Assessment Checklist

✅ Define frequent patterns.

✅ Explain itemsets and k-itemsets.

✅ Calculate support.

✅ Calculate confidence.

✅ Generate association rules.

✅ Distinguish closed and maximal patterns.

✅ Explain the downward closure property.

✅ Explain Apriori pruning.

✅ Describe the Apriori algorithm.

✅ Understand candidate generation.

✅ Explain FP-Growth.

✅ Explain FP-Trees.

✅ Compare Apriori and FP-Growth.

✅ Describe real-world applications of frequent pattern mining.
