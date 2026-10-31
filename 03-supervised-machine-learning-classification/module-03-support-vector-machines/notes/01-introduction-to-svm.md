# Introduction to Support Vector Machines (SVM)

## 1. Definition of SVM

Support Vector Machine (SVM) is a supervised machine learning algorithm commonly used for classification.

The main objective of SVM is to find a decision boundary that separates data points belonging to different classes.

This boundary is called a hyperplane.

## 2. Hyperplane

A hyperplane is a decision boundary used to separate data into different classes.

In a two-dimensional dataset, the hyperplane can be represented as a line. In higher-dimensional data, it becomes a surface or a boundary with more dimensions.

The position of the hyperplane determines how the data is classified.

## 3. Support Vectors

Support vectors are the data points located closest to the decision boundary.

These points are important because they influence the position and orientation of the hyperplane.

SVM uses these points to determine the separating boundary between classes.

## 4. Margin

The margin is the distance between the decision boundary and the nearest data points from each class.

SVM aims to find a hyperplane with a large margin between the classes.

A larger margin can help the model generalize to unseen data.

## 5. How SVM Works

The general process of SVM classification is:

1. Receive labeled training data.
2. Identify the separating boundary between classes.
3. Determine the support vectors.
4. Find a suitable hyperplane that separates the classes.
5. Use the hyperplane to classify new observations.

## 6. SVM for Classification

SVM can be used to classify data into different categories.

For example, an SVM model can classify email messages into two groups:

- Spam
- Not Spam

The model learns the separating boundary from the training data and uses it to predict the class of new messages.

## 7. Summary

SVM is a classification algorithm that searches for an effective decision boundary between classes.

The hyperplane, support vectors, and margin are important concepts for understanding how SVM performs classification.