# Introduction to Supervised Machine Learning

## 1. What is Machine Learning?

Machine Learning (ML) is a branch of Artificial Intelligence (AI) that enables computers to learn patterns from data and make predictions or decisions without being explicitly programmed for every task.

Instead of writing specific rules for every situation, machine learning algorithms use data to identify patterns and relationships.

## 2. Types of Machine Learning

Machine learning is commonly divided into several types:

### Supervised Learning

Supervised learning uses labeled data to train a model. Each training example contains input data and its corresponding target value.

The model learns the relationship between the inputs and targets, then uses that relationship to make predictions on new data.

### Unsupervised Learning

Unsupervised learning works with data that does not have predefined labels. The algorithm attempts to discover patterns, structures, or groups within the data.

### Reinforcement Learning

Reinforcement learning involves an agent that learns by interacting with an environment. It receives rewards or penalties based on its actions and uses this feedback to improve its decisions.

## 3. Understanding Supervised Learning

Supervised learning is based on a dataset containing:

- **Features (X):** The input variables used by the model.
- **Target (y):** The value that the model is expected to predict.
- **Labels:** The known target values associated with training examples.

During training, the algorithm learns the relationship between the features and the target.

After training, the model can use this learned relationship to predict target values for new observations.

### Basic Workflow

1. Collect labeled data.
2. Separate input features and target values.
3. Train the model using the training data.
4. Allow the model to learn its parameters.
5. Use the trained model to make predictions.
6. Evaluate the model's performance.

## 4. Regression vs. Classification

Supervised learning problems can be divided into two main categories.

### Regression

Regression is used when the target variable is numerical and continuous.

Examples:
- Predicting house prices.
- Estimating sales revenue.
- Predicting temperature.

### Classification

Classification is used when the target variable represents a category or class.

Examples:
- Identifying whether an email is spam or not spam.
- Classifying images into different categories.
- Predicting whether a customer will leave a service.

### Main Difference

| Aspect | Regression | Classification |
|---|---|---|
| Output | Numerical value | Category or class |
| Example | House price | Spam or not spam |
| Target | Continuous or numerical | Categorical |

## 5. Important Machine Learning Terms

- **Training:** The process of teaching a model using training data.
- **Prediction:** The output produced by a trained model.
- **Model:** A mathematical representation of patterns learned from data.
- **Parameters:** Values learned by the model during training.
- **Hyperparameters:** Settings chosen before or during model training that control the learning process.
- **Observation:** One individual data record or example.

## Key Takeaway

Supervised machine learning learns from labeled examples. Regression predicts numerical values, while classification predicts categories. Understanding these differences is important before selecting an appropriate machine learning algorithm.