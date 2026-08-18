# AI Capstone Portfolio

## Overview

This portfolio brings together the six major projects completed during my **Graduate Certificate in Artificial Intelligence**. While each project was developed within a different course, collectively they represent a structured learning journey through software engineering, machine learning, deep learning, natural language processing, computer vision, and data mining.

Across these projects, I worked with:

- Object-oriented software systems
- Structured and tabular datasets
- Healthcare datasets
- Image datasets
- Social media text
- Machine reading comprehension datasets

The projects demonstrate the complete AI and analytics lifecycle:

```text
Problem Definition
        ↓
Data Collection
        ↓
Data Preprocessing
        ↓
Exploratory Analysis
        ↓
Model Development
        ↓
Validation & Evaluation
        ↓
Interpretation
        ↓
Ethical Considerations
```

The portfolio reflects both theoretical understanding and practical implementation skills across multiple Artificial Intelligence domains.

---

# Portfolio Journey

## 1. Library Management System

### Project Repository Link: https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/tree/main/01.%20Advanced%20Object%20Oriented%20Programming/Projects

### Course
Advanced Object-Oriented Programming

### Project Focus

The first project established the software engineering foundations that support modern intelligent systems.

A desktop-based Library Management System was designed and implemented using advanced object-oriented design principles. The system supported realistic library operations including:

- Book and copy management
- Member management
- Borrowing and return processing
- Reservation management
- Fine calculation
- Recommendation functionality

### Technical Concepts Applied

- Object-Oriented Programming (OOP)
- Encapsulation
- Composition
- Polymorphism
- Layered Architecture
- Defensive Programming
- Service-Based Business Logic
- Rule-Based Recommendation Systems

### Validation

The application was validated using scenario-based testing, including both normal and edge-case workflows.

### Key Outcome

Developed a robust and extensible software solution demonstrating how well-designed software architecture supports complex real-world business rules and operational workflows.

---

## 2. Handwritten Digit Recognition Using Neural Networks

### Project Repository Link: https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/tree/main/02.%20Neural%20Network%20and%20Deep%20Learning/Projects

### Course
Neural Networks and Deep Learning

### Project Focus

This project introduced neural network fundamentals through handwritten digit classification using the MNIST dataset.

The study investigated multiple Multilayer Perceptron (MLP) architectures and optimisation strategies before extending the solution using Convolutional Neural Networks (CNNs).

### Models Implemented

#### Multilayer Perceptron (MLP)

Using:

- Stochastic Gradient Descent (SGD)
- RMSprop
- Adam

#### Regularised MLP

Using:

- Dropout Regularisation
- Deep Network Variants

#### CNN Extension Model

Used for comparison with fully connected architectures.

### Evaluation Methods

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- Confusion Matrix
- Classification Report
- Test Accuracy

### Key Findings

- Adam consistently outperformed SGD and RMSprop.
- Dropout reduced overfitting and improved generalisation.
- CNN significantly outperformed all MLP architectures.
- CNN achieved approximately 99% classification accuracy.

### Key Outcome

Demonstrated how optimisation strategies, regularisation techniques, and architectural choices affect learning performance and generalisation.

---

## 3. Vehicle Recognition for Road Safety Monitoring

### Project Repository Link: https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/tree/main/02.%20Neural%20Network%20and%20Deep%20Learning/Projects

### Course
Neural Networks and Deep Learning

### Project Focus

This project applied deep learning to a real-world computer vision problem involving automated vehicle detection for road safety monitoring systems.

The dataset contained approximately:

```text
17,760 Images
```

including:

- Vehicles
- Non-Vehicles

### Data Preparation

- Image Resizing
- RGB Conversion
- Pixel Normalisation
- Training/Validation/Test Splitting

### Models Implemented

#### Convolutional Neural Network (CNN)

Used as the primary image classification model.

#### Recurrent Neural Network (LSTM)

Implemented by converting images into sequential representations for comparative analysis.

### Evaluation Methods

- Accuracy
- ROC Curves
- AUC
- Confusion Matrices

### Results

| Model | Test Accuracy | AUC |
|---------|---------|---------|
| CNN | ~99.7% | ~1.00 |
| LSTM | ~87.6% | ~0.94 |

### Key Findings

The CNN substantially outperformed the LSTM model because spatial visual features are more effectively captured through convolutional operations than sequential processing.

### Key Outcome

Demonstrated the importance of matching neural network architecture to data structure and problem domain.

---

## 4. Deep Learning-Based Sentiment Analysis on Twitter Airline Reviews

### Project Repository Link: https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/tree/main/03.%20Applied%20Natural%20Language%20Processing/Projects

### Course
Applied Natural Language Processing

### Project Focus

This project investigated sentiment classification of noisy social media text using recurrent neural network architectures.

The task involved three-class classification:

- Positive
- Neutral
- Negative

### NLP Pipeline

- Text Cleaning
- Tokenisation
- Word Embeddings
- Sequence Modelling
- Classification

### Models Implemented

#### SimpleRNN

Embedding → RNN → Dense → Softmax

#### GRU

Embedding → GRU → Dropout → Dense → Softmax

#### LSTM

Embedding → LSTM → Dropout → Dense → Softmax

### Regularisation Techniques

- Dropout
- Recurrent Dropout
- Spatial Dropout
- L2 Regularisation
- Early Stopping
- Learning Rate Scheduling

### Evaluation Methods

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Training/Validation Loss Curves

### Key Findings

- LSTM achieved the strongest macro-level performance.
- GRU offered comparable performance with slightly higher precision.
- SimpleRNN underperformed both gated architectures.
- Overfitting remained a challenge despite extensive regularisation.

### Key Outcome

Demonstrated how gating mechanisms improve handling of noisy text and long-range dependencies in sentiment analysis tasks.

---

## 5. Deep Learning-Based Question Answering System

### Project Repository Link: https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/tree/main/03.%20Applied%20Natural%20Language%20Processing/Projects

### Course
Applied Natural Language Processing

### Project Focus

This project extended NLP work from classification to machine reading comprehension and extractive question answering.

A complete Question Answering pipeline was implemented using the SQuAD v2.0 dataset.

### Architecture

```text
Input Layer
      ↓
GloVe Embeddings
      ↓
Bidirectional LSTM Encoder
      ↓
Bi-Directional Attention
      ↓
Span Prediction
```

### Components Implemented

- GloVe Word Embeddings
- Bidirectional LSTM Encoder
- Attention Mechanism
- Start-End Span Prediction
- Answerability Detection

### Evaluation Methods

- Exact Match (EM)
- Token-Level Evaluation
- Span Prediction Accuracy
- Answerability Classification
- Training and Validation Loss Analysis

### Key Findings

- The attention mechanism successfully learned meaningful context-question relationships.
- The model frequently identified relevant answer regions.
- Boundary prediction remained a major source of error.
- Answerability detection for SQuAD v2.0 proved challenging.

### Key Outcome

Demonstrated a complete deep learning-based reading comprehension system and provided practical experience with sequence modelling and attention-based architectures.

---

## 6. Health Dataset Analysis and Prediction

### Project Repository Link: https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/tree/main/04.%20Data%20Warehousing%20and%20Mining/Projects

### Course
Data Warehousing and Mining

### Project Focus

This project applied classical and machine learning techniques to cardiovascular disease risk prediction.

The dataset originally contained:

```text
70,000 Patient Records
```

with:

- Demographic Variables
- Clinical Variables
- Lifestyle Variables

### Feature Engineering

- Age Conversion
- BMI Calculation
- Standardisation
- Data Cleaning
- Outlier Removal

### Models Implemented

#### Logistic Regression

#### Decision Tree

#### Random Forest

#### Support Vector Machine (SVM)

### Evaluation Methods

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Feature Importance Analysis

### Results

| Model | Accuracy | ROC-AUC |
|---------|---------|---------|
| Random Forest | 0.734 | 0.799 |
| Logistic Regression | 0.732 | 0.797 |

### Key Findings

Key predictors included:

- Systolic Blood Pressure
- Diastolic Blood Pressure
- Age
- Cholesterol
- BMI

Random Forest produced the strongest predictive performance, while Logistic Regression offered near-equivalent performance with superior interpretability.

### Key Outcome

Demonstrated practical application of supervised learning, feature engineering, model comparison, and healthcare analytics.

---

# Skills Developed Across the Portfolio

## Software Engineering

- Object-Oriented Programming
- Design Patterns
- Layered Architecture
- Defensive Programming
- System Testing

## Classical and Machine Learning

- Logistic Regression
- Decision Trees
- Random Forests
- Support Vector Machines
- Model Selection
- Hyperparameter Optimisation

## Deep Learning

- Multilayer Perceptrons
- Convoluted Neural Network (CNN)
- Recurrent Neural Network (RNN)
- Gated Recurrent Units (GRUs)
- Long-short_term-memory (LSTM)
- Attention Mechanisms

## Natural Language Processing

- Text Preprocessing
- Word Embeddings
- Sentiment Analysis
- Question Answering
- Reading Comprehension

## Computer Vision

- Image Classification
- Feature Extraction
- CNN-Based Recognition Systems

## Data Analytics

- Exploratory Data Analysis
- Feature Engineering
- Statistical Analysis
- Data Visualisation

## Model Validation & Evaluation

- Confusion Matrices
- ROC Curves
- ROC-AUC
- Precision
- Recall
- F1 Score
- Exact Match
- Classification Reports
- Training/Validation Monitoring
- Regularization
- Overfitting Analysis
- Feature Importance Analysis

---

# Reflection

These six projects document my progression from traditional software engineering to advanced Artificial Intelligence applications.

The journey began with designing a robust object-oriented software system and progressed toward increasingly sophisticated analytical techniques, including:

- Classical Learning
- Machine Learning
- Deep Learning
- Natural Language Processing
- Computer Vision
- Healthcare Analytics
- Reading Comprehension Systems

Throughout the program I gained practical experience in:

- Building complete end-to-end solutions
- Working with structured and unstructured data
- Developing interpretable and high-performance models
- Evaluating model generalisation
- Comparing competing approaches
- Communicating technical findings
- Considering ethical and responsible AI deployment

Collectively, these projects represent a practical application of modern AI methodologies across diverse real-world domains and provide a strong foundation for future work in Artificial Intelligence, Data Science, and Machine Learning.
