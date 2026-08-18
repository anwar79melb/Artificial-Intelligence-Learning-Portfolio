# Project 01: Handwritten Digit Recognition Using Multilayer Perceptrons

## Module

Neural Networks and Deep Learning

## Assignment Overview

Handwritten digit recognition is one of the classic problems in machine learning and serves as an excellent introduction to neural network-based classification.

In this assignment, you will design, train, and evaluate a Multilayer Perceptron (MLP) capable of recognizing handwritten digits from the MNIST dataset. The objective is to investigate how neural networks learn visual patterns and to compare the effect of different optimization algorithms on model performance.

The project will guide you through the complete deep learning workflow:

1. Data preparation
2. Neural network design
3. Model training
4. Performance evaluation
5. Result interpretation
6. Discussion of ethical implications

---

# Background

The MNIST dataset contains grayscale images of handwritten digits ranging from 0 to 9.

Dataset characteristics:

- 60,000 training images
- 10,000 testing images
- Image size: 28 × 28 pixels
- 10 output classes (digits 0-9)

Each image is represented as a matrix of pixel values and must be processed before it can be used for neural network training.

---

# Project Requirements

## Stage 1: Environment Setup

Create a Python project or Jupyter Notebook and import all required libraries.

Examples include:

- TensorFlow
- Keras
- NumPy
- Matplotlib

You may include additional libraries if required.

### Expected Outcome

A working development environment capable of loading and training neural network models.

---

## Stage 2: Data Acquisition and Preparation

Load the MNIST dataset using the Keras dataset API.

Perform the necessary preprocessing steps to prepare the data for model training.

### Requirements

- Load training and testing datasets.
- Examine dataset dimensions.
- Display sample images.
- Scale pixel values to a consistent range.
- Ensure the same preprocessing pipeline is applied to both training and testing datasets.

### Discussion

Explain why normalization is important when training neural networks.

---

## Stage 3: Design a Neural Network Classifier

Develop a Multilayer Perceptron (MLP) for digit classification.

Your design should include:

- An input layer
- One or more hidden layers
- An output layer capable of predicting ten digit classes

### Considerations

Experiment with:

- Number of hidden layers
- Number of neurons
- Activation functions

Provide justification for your chosen architecture.

---

## Stage 4: Configure the Learning Process

Prepare the model for training by selecting suitable learning parameters.

### Select and justify:

#### Loss Function

Choose a loss function appropriate for a multi-class classification problem.

#### Optimizer

Evaluate at least two different optimization algorithms.

Examples:

- SGD
- Adam
- RMSProp

#### Evaluation Metric

Select suitable metrics for monitoring performance during training.

---

## Stage 5: Train the Model

Train your neural network using the prepared dataset.

### Record

- Number of epochs
- Batch size
- Training accuracy
- Training loss

### Visualisation

Plot training curves for:

- Accuracy
- Loss

and discuss what they reveal about model learning.

---

## Stage 6: Evaluate Performance

Test the trained model using unseen data.

### Include

- Test accuracy
- Test loss
- General observations

Discuss whether the model appears to generalise well.

---

## Stage 7: Make Predictions

Use the trained model to classify several test images.

### For each prediction:

- Display the image
- Show the predicted digit
- Show the actual digit
- Indicate whether the prediction was correct

### Analysis

Identify examples where the model made mistakes and discuss possible reasons.

---

## Stage 8: Optimizer Comparison

Compare the performance of the optimizers you selected.

### Consider

- Accuracy
- Training speed
- Stability
- Convergence behaviour

Summarise your findings and identify the best-performing optimizer for this problem.

---

# Report Requirements

Prepare a technical report between **1000 and 1200 words**.

Your report should contain the following sections.

---

## 1. Introduction

Provide an overview of:

- Image classification
- Neural networks
- Handwritten digit recognition
- Project objectives

---

## 2. Literature Review

Research and summarise previous work related to:

- Artificial Neural Networks
- Multilayer Perceptrons
- MNIST classification
- Deep learning-based image recognition

Use academic and credible sources.

---

## 3. Methodology

Describe your implementation process.

Include:

- Dataset preparation
- Network architecture
- Hyperparameters
- Optimizer selection
- Training strategy

Justify the decisions you made.

---

## 4. Results and Discussion

Present:

- Accuracy results
- Loss values
- Graphs
- Screenshots
- Prediction samples

Interpret the results rather than simply presenting them.

---

## 5. Challenges and Lessons Learned

Discuss:

- Technical difficulties encountered
- Debugging experiences
- Hyperparameter tuning challenges
- Areas for future improvement

---

## 6. Ethical Considerations

Evaluate the ethical implications of AI-powered image classification systems.

Possible discussion topics include:

- Data bias
- Fairness
- Transparency
- Privacy
- Responsible AI development
- Professional obligations of software developers

Suggest practical measures that could reduce ethical risks.

---

## 7. References

Provide complete references for all information sources used throughout your report.

Use a consistent academic referencing style.

---

# Deliverables

Submit the following:

### Source Code

- Python script (.py) or
- Jupyter Notebook (.ipynb)

### Technical Report

- PDF or Word document

### Supporting Evidence

- Training screenshots
- Evaluation outputs
- Accuracy graphs
- Prediction examples

---

# Extension Challenge (Optional)

Attempt one or more of the following:

- Add Dropout regularization.
- Add Batch Normalization.
- Compare shallow and deep MLP architectures.
- Compare three or more optimizers.
- Create a confusion matrix for the final model.
- Visualise incorrectly classified digits.

These extensions are not required but can strengthen your analysis and understanding.
