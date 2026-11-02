# Module 6 – Model Interpretability and Modeling Unbalanced Classes

## Overview

This module covers two important topics in supervised machine learning classification: model interpretability and modeling unbalanced classes.

Model interpretability focuses on understanding how a machine learning model produces predictions and how its behavior can be explained to humans. Modeling unbalanced classes focuses on handling datasets where one class has significantly more observations than another.

## Learning Objectives

After completing this module, I should be able to:

- Explain why model interpretability is important.
- Differentiate between self-interpretable and non-self-interpretable models.
- Understand model-agnostic explanations and surrogate models.
- Explain the challenges caused by unbalanced classification datasets.
- Differentiate between upsampling and downsampling.
- Understand class weighting and stratified sampling.
- Describe random and synthetic oversampling techniques.
- Understand NearMiss, Tomek Links, Edited Nearest Neighbors, and balanced bagging.

## Topics Covered

### 1. Model Interpretability
- Importance of model interpretability
- Self-interpretable models
- Non-self-interpretable models
- Model-agnostic explanations
- Surrogate models

### 2. Modeling Unbalanced Classes
- Introduction to unbalanced classes
- Upsampling and downsampling
- Class weighting
- Stratified sampling
- Random oversampling
- Synthetic oversampling: SMOTE and ADASYN
- NearMiss
- Tomek Links
- Edited Nearest Neighbors
- Balanced bagging (also called blagging in the course material)

## Module Structure

```text
module-06-model-interpretability-and-unbalanced-classes/
├── README.md
├── notes/
│   ├── 01-model-interpretability.md
│   ├── 02-model-agnostic-explanations-and-surrogate-models.md
│   ├── 03-understanding-unbalanced-classes.md
│   └── 04-approaches-to-unbalanced-classification.md
└── notebooks/
    └── README.md
```

## Key Takeaways

- A model with high predictive performance is not always easy to understand.
- Interpretability helps users understand, evaluate, and debug model predictions.
- Self-interpretable models have structures that humans can understand directly.
- Non-self-interpretable models may require additional explanation methods.
- Class imbalance can make accuracy misleading.
- Resampling and class weighting are common approaches to handling unbalanced datasets.
- Resampling must be applied only to training data after the train-test split.
- Cross-validation can help compare different balancing techniques.

## Practical Application

These concepts are useful when building classification systems in areas such as healthcare, finance, fraud detection, and other applications where prediction quality and model transparency are important.

## Learning Progress

- [ ] Complete the Model Interpretability lessons.
- [ ] Complete the Modeling Unbalanced Classes lessons.
- [ ] Review the practice labs.
- [ ] Complete the module review and graded quiz.