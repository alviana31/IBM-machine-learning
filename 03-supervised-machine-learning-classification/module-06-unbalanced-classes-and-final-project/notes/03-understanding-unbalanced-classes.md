# Understanding Unbalanced Classes

## 1. Introduction

An unbalanced classification dataset is a dataset in which the number of observations in one class is significantly different from the number of observations in another class.

For example, consider a fraud detection dataset:

- 9,500 transactions are legitimate.
- 500 transactions are fraudulent.

The legitimate class is the majority class, while the fraudulent class is the minority class.

## 2. Why Class Imbalance Is a Problem

Classification algorithms are commonly optimized to improve accuracy. When one class has many more observations than another, a model may favor the majority class.

For example, a model that predicts every transaction as legitimate in the example above would achieve 95% accuracy, even though it fails to identify every fraudulent transaction.

This shows that accuracy alone may not provide a complete evaluation of an imbalanced classification model.

## 3. Majority and Minority Classes

- **Majority class:** The class with the largest number of observations.
- **Minority class:** The class with the smallest number of observations.

The minority class is often the class that requires more attention, especially when missing its observations has serious consequences.

## 4. Common Approaches

The course introduces three general approaches to balancing classes.

### 4.1 Downsampling

Downsampling reduces the number of observations in the majority class.

The goal is to make the majority class closer in size to the minority class.

**Advantage:**
- Reduces the dominance of the majority class.
- Can reduce training data size.

**Disadvantage:**
- Removes observations that may contain useful information.

### 4.2 Upsampling

Upsampling increases the number of observations in the minority class.

One simple method is to duplicate observations from the minority class.

**Advantage:**
- Retains the original majority-class observations.
- Gives the model more minority-class examples during training.

**Disadvantage:**
- Duplicating observations may increase the risk of overfitting.

### 4.3 Combining Upsampling and Downsampling

Both approaches can be combined.

For example, a dataset can first use synthetic oversampling to increase minority-class observations and then downsample some majority-class observations.

The choice of approach depends on the dataset and should be evaluated carefully.

## 5. Why Accuracy Is Not Enough

For imbalanced classification, other evaluation metrics can provide more useful information.

Common classification metrics include:

- Precision
- Recall
- F1-score
- Confusion Matrix
- ROC-AUC

Recall is particularly relevant when identifying minority-class observations is important.

However, the appropriate metric depends on the project's objective and the consequences of false positives and false negatives.

## 6. Correct Order of Data Preparation

The course emphasizes the following order when using over- or undersampling:

1. Split the dataset into training and testing sets.
2. Use stratified train-test splitting when appropriate to preserve class proportions.
3. Apply over- or undersampling only to the training data.
4. Train the classification model.
5. Evaluate the model using the untouched test data.

Resampling before splitting can cause information from duplicated or related observations to appear in both training and testing sets. This can lead to misleading evaluation results.

## 7. Key Takeaways

- Unbalanced classes occur when class frequencies differ significantly.
- A model may favor the majority class.
- Accuracy can be misleading when classes are unbalanced.
- Downsampling reduces majority-class observations.
- Upsampling increases minority-class observations.
- The train-test split must be performed before resampling.
- Model performance should be evaluated using metrics appropriate to the problem.

## 8. Conclusion

Handling unbalanced classes is important for building reliable classification models. Choosing an appropriate balancing method and evaluating the model with suitable metrics can improve the model's ability to recognize minority-class observations.