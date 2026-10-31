# Introduction to Classification

## 1. What is Classification?

Classification is a supervised machine learning task used to predict the category or class of a given observation based on its input features.

Unlike regression, which predicts continuous numerical values, classification predicts discrete labels.

For example:
- Email classification: Spam or Not Spam.
- Medical classification: Positive or Negative.
- Customer classification: Potential Customer or Regular Customer.

## 2. Supervised Learning

Classification belongs to supervised learning because the model is trained using labeled data.

A labeled dataset contains:
- Features (X): Input variables used to make predictions.
- Target (y): The class or category that the model needs to predict.

During training, the model learns the relationship between the input features and their corresponding labels.

## 3. Types of Classification

### Binary Classification

Binary classification involves predicting one of two possible classes.

Examples:
- Spam or Not Spam.
- Yes or No.
- Fraud or Not Fraud.

### Multiclass Classification

Multiclass classification involves predicting one class from more than two possible categories.

Examples:
- Classifying images into different animal categories.
- Predicting product categories.
- Classifying types of flowers.

## 4. Classification Workflow

A general classification workflow consists of:

1. Collecting a labeled dataset.
2. Preparing and cleaning the data.
3. Separating features and target variables.
4. Splitting the dataset into training and testing sets.
5. Training a classification model.
6. Making predictions.
7. Evaluating model performance.

## 5. Classification vs. Regression

| Aspect | Classification | Regression |
|---|---|---|
| Prediction | Categories or labels | Continuous values |
| Output | Discrete | Numerical |
| Example | Spam or Not Spam | House price |
| Common Metrics | Accuracy, Precision, Recall | MAE, MSE, R-squared |

## Conclusion

Classification is used to solve problems where the target variable represents a category or class. Understanding its basic concepts is important before learning classification algorithms such as Logistic Regression.