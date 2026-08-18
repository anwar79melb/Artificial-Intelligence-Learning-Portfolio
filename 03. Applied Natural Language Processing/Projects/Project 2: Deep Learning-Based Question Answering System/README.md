# Project 2: Deep Learning-Based Question Answering System

## Course
**Applied Natural Language Processing**

---

# Project Overview

Question Answering (QA) systems are designed to automatically answer questions posed by users in natural language. They play a critical role in modern AI applications, including:

- Search engines
- Virtual assistants
- Customer support chatbots
- Intelligent tutoring systems
- Knowledge management systems
- Scientific information retrieval

A QA system aims to identify the most relevant answer from a given body of text rather than simply retrieving documents. Modern QA systems combine Natural Language Processing (NLP) with Deep Learning to understand context, interpret questions, and locate answer spans within textual passages.

In this project, students will design, implement, train, and evaluate a Deep Learning-based Question Answering system using the **Stanford Question Answering Dataset (SQuAD 2.0)**. The project focuses on building a complete QA architecture consisting of Input, Embedding, Encoder, Attention, and Output layers. 【1-bfb687】

---

# Project Aim

The aim of this project is to develop a Neural Question Answering system capable of identifying answers from a given text passage in response to user questions.

Students will gain practical experience in:

- Reading comprehension tasks
- Deep learning for NLP
- Word embeddings
- Sequence modelling
- Attention mechanisms
- Span prediction
- Model evaluation
- Ethical analysis of NLP systems

---

# Background

Question Answering systems attempt to satisfy human information needs by locating accurate answers to natural language questions.

### Example Questions

```text
Who is the founder of Apple?
```

```text
What is the average age of onset of autism?
```

Modern QA systems typically operate using:

```text
Question
      ↓
Text Retrieval
      ↓
Reading Comprehension
      ↓
Answer Extraction
```

Instead of generating entirely new information, the system identifies the most appropriate answer span from a provided context. 【1-bfb687】

---

# Dataset

## Stanford Question Answering Dataset (SQuAD 2.0)

The project uses:

**SQuAD 2.0**

Dataset website:

https://rajpurkar.github.io/SQuAD-explorer/

---

## Dataset Description

SQuAD 2.0 contains:

- Approximately 100,000 answerable questions
- Approximately 50,000 unanswerable questions
- Wikipedia-based contexts and passages

The dataset is designed to test machine reading comprehension by requiring models to locate answers directly within provided passages. 【1-bfb687】

---

## Example

### Context

```text
Apollo used Saturn family rockets as launch vehicles.
Apollo/Saturn vehicles were also used for an Apollo
Applications Program, which consisted of Skylab,
a space station that supported three manned missions
in 1973–74.
```

### Question

```text
What space station supported
three manned missions in 1973–1974?
```

### Answer

```text
Skylab
```【1-bfb687】

---

# Project Tasks

Students are required to implement a complete Deep Learning Question Answering architecture.

---

# Task 1: Input Layer

## Objective

Load and prepare the dataset for model training.

---

## Requirements

Students must:

- Import the SQuAD dataset.
- Parse context passages.
- Parse questions.
- Extract answers and answer spans.
- Handle answerable and unanswerable cases.
- Prepare training, validation, and testing datasets.

---

## Expected Outputs

- Context dataset
- Question dataset
- Answer span labels
- Dataset statistics

---

# Task 2: Embedding Layer

## Objective

Convert textual data into numerical vector representations.

---

## Requirements

Students must use:

```text
GloVe Word Embeddings
```

---

## Embedding Options

Students may choose:

```text
100-Dimensional Embedding
```

or

```text
300-Dimensional Embedding
```

---

## Required Activities

### Text Tokenization

Convert words into tokens.

---

### Vocabulary Construction

Build vocabulary mapping.

---

### Embedding Matrix Construction

Create embedding lookup tables.

---

### Out-of-Vocabulary (OOV) Handling

Define and justify a strategy for unseen words.

---

## Justification Required

Students must explain:

- Embedding size selection
- Advantages of GloVe embeddings
- OOV handling strategy
- Expected impact on model performance

---

# Task 3: Encoder Layer

## Objective

Encode contextual meaning of words within context passages and questions.

---

## Requirements

Students must implement a sequence encoder using either:

### Bidirectional LSTM (BiLSTM)

or

### Bidirectional GRU (BiGRU)

---

## Purpose

The encoder should enable each word representation to capture:

```text
Previous Context
+
Current Word
+
Future Context
```

---

## Expected Deliverables

- Encoder architecture
- Hyperparameter selection
- Sequence modelling explanation

---

# Task 4: Attention Layer

## Objective

Implement an attention mechanism to connect questions with relevant context information.

---

## Importance

The Attention Layer is the most important component of modern QA systems.

It allows the model to determine:

```text
Which Context Words
Are Most Relevant
To The Question
```

---

## Requirements

Students must:

- Design an attention mechanism.
- Explain how question-context interaction is performed.
- Justify the design choice.

---

## Expected Deliverables

- Attention architecture diagram
- Attention workflow explanation
- Model implementation

---

# Task 5: Output Layer

## Objective

Predict answer positions within the context passage.

---

## Requirements

Students must implement:

```text
Softmax Output Layers
```

to predict:

### Answer Start Position

```text
Start Index
```

---

### Answer End Position

```text
End Index
```

---

## Outputs

The model should identify:

```text
Answer Span
```

within the context passage.

---

# Recommended QA Architecture

Students should implement the following pipeline:

```text
Input Layer
      ↓
Word Embedding Layer
      ↓
BiLSTM / BiGRU Encoder
      ↓
Attention Layer
      ↓
Output Layer
(Start & End Span Prediction)
```

---

# Model Training Requirements

Students should:

- Train the model on SQuAD data.
- Monitor training performance.
- Evaluate on validation data.
- Tune hyperparameters.

---

## Suggested Hyperparameters

Examples include:

- Learning rate
- Batch size
- Number of epochs
- Hidden layer size
- Embedding dimension
- Dropout rate

---

# Model Evaluation

Students should evaluate the QA system using suitable metrics.

Possible evaluation measures include:

---

## Exact Match (EM)

Whether the predicted answer exactly matches the true answer.

---

## F1 Score

Measures overlap between predicted and actual answers.

---

## Training and Validation Loss

Analyze convergence behaviour.

---

## Sample Prediction Analysis

Evaluate prediction quality manually using examples.

---

# Required Comparative Analysis

Students should critically analyze:

- BiLSTM vs BiGRU performance
- Impact of embedding dimensions
- Attention layer effectiveness
- Error cases and limitations
- Performance on unanswerable questions

---

# Report Requirements

Students must prepare a formal technical report.

---

# Section 1: Introduction

Discuss:

- What is Question Answering?
- Applications of QA systems.
- Modern deep learning approaches.
- Importance of reading comprehension.

---

# Section 2: Dataset Understanding

Include:

### Dataset Structure

Describe contexts, questions, and answers.

---

### Data Exploration

Discuss:

- Number of samples
- Answerable questions
- Unanswerable questions
- Dataset challenges

---

# Section 3: Methodology

Describe the complete architecture.

---

## Input Layer

Data loading and preprocessing.

---

## Embedding Layer

GloVe implementation.

---

## Encoder Layer

BiLSTM or BiGRU design.

---

## Attention Layer

Question-context interaction mechanism.

---

## Output Layer

Answer span prediction strategy.

---

# Section 4: Experimental Results

Include:

### Training Results

- Accuracy trends
- Loss curves

---

### Evaluation Results

- Exact Match
- F1 Score

---

### Visualizations

- Learning curves
- Architecture diagrams
- Sample predictions

---

### Comparison Tables

Present performance comparisons.

---

# Section 5: Conclusions

Discuss:

- Key findings
- Best performing configuration
- Major lessons learned
- Limitations

---

# Section 6: Reproducibility Details

Students must clearly document:

### Dataset Split

Training, validation, and test splits.

---

### Libraries

Examples:

- TensorFlow
- Keras
- PyTorch
- Numpy
- Transformers

---

### Hyperparameters

Document all experimental settings.

---

### Random Seeds

Provide reproducibility details.

---

# Section 7: Ethical Evaluation

Students must critically evaluate ethical concerns associated with Question Answering systems.

---

## Ethical Theories to Apply

### Utilitarianism

Assess impacts on society.

---

### Deontology

Consider duties and obligations.

---

### Rights-Based Ethics

Assess user and information rights.

---

### Justice and Fairness

Evaluate bias and equitable treatment.

---

### Virtue Ethics

Assess ethical behaviour in system design.

---

### Care Ethics

Consider impacts on vulnerable groups.

---

# Ethical Issues to Discuss

Students should identify and analyze issues such as:

---

## Privacy

Exposure of personal information.

---

## Bias

Bias inherited from training data.

---

## Transparency

Difficulty understanding model decisions.

---

## Accountability

Responsibility for incorrect answers.

---

## Misuse

Generation of misleading information.

---

## Attribution

Use of copyrighted or sensitive content.

---

## Human Factors

Trust, usability, and dependence on AI systems.

---

## Environmental Impact

Computational resources required for training.

---

# Required Ethical Deliverables

Students must provide:

- Identification of ethical risks
- Supporting evidence
- Practical mitigation strategies
- Professional recommendations

---

# Submission Requirements

Students must submit the following items.

---

## 1. Jupyter Notebook (.ipynb)

Requirements:

- Fully executable
- Clean code
- Well-commented implementation
- Complete QA architecture

---

## 2. Technical Report (PDF or Word)

The report must include:

- Dataset understanding
- Methodology
- Experiments
- Results
- Conclusions
- Reproducibility information
- Ethical analysis

---

## 3. Presentation Slides (PPT)

Presentation must include:

### Architecture Diagrams

Illustrating all model components.

---

### Performance Comparison Tables

Showing progress and final outcomes.

---

### Visualizations

Examples:

- Training curves
- Validation curves
- Sample predictions
- Evaluation summaries

---

## 4. Data Evidence (.csv)

Provide supporting evidence including:

- Sample predictions
- Evaluation results
- Hyperparameter configurations
- Final metrics

---

## 5. Recorded Video Presentation

Students must submit a recorded presentation explaining:

- Project motivation
- Architecture design
- Experimental setup
- Results
- Ethical considerations

---

# Assessment Structure

| Component | Marks |
|------------|------------|
| Input Layer | 5 |
| Embedding Layer | 10 |
| Encoder Layer | 10 |
| Attention Layer | 10 |
| Output Layer | 10 |
| Understanding & Methodology | 15 |
| Human Factors | 5 |
| Ethics & Social Issues | 10 |
| Presentation Quality | 10 |
| Explanation & Viva | 15 |
| **Total** | **100** |

---

# Expected Learning Outcomes

Upon successful completion of this project, students should be able to:

✅ Build an end-to-end Question Answering system.

✅ Apply GloVe word embeddings.

✅ Implement Bidirectional LSTM or GRU encoders.

✅ Design and apply attention mechanisms.

✅ Predict answer spans using neural networks.

✅ Evaluate machine reading comprehension systems.

✅ Analyze ethical and social implications of NLP systems.

✅ Communicate technical findings professionally.

---

# Project Goal

The goal of this project is to develop a deep learning-based Question Answering system capable of identifying correct answers from textual passages using the Stanford Question Answering Dataset (SQuAD). Through the implementation of word embeddings, sequence encoders, attention mechanisms, and span prediction techniques, students will gain practical experience in modern Natural Language Processing, machine reading comprehension, and ethical AI development.
