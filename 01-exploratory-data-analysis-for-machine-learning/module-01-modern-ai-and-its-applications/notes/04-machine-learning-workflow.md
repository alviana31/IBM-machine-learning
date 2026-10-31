# Machine Learning Workflow

## 1. Introduction

A Machine Learning workflow is a series of steps used
to develop a model, starting from defining a problem
until the model is deployed.

## 2. Steps in the Machine Learning Workflow

### 2.1 Problem Statement

Define the problem that needs to be solved.

A clear problem statement helps determine what kind
of data and Machine Learning approach are needed.

### 2.2 Data Collection

Collect relevant data from available sources.

The collected data will be used to understand the problem
and develop the Machine Learning model.

### 2.3 Data Exploration and Preprocessing

Explore the dataset to understand its structure,
characteristics, and quality.

Preprocessing prepares the data before it is used
for model training.

### 2.4 Modeling

Select and train a Machine Learning algorithm
using the prepared data.

The model learns patterns from the training data.

### 2.5 Validation

Evaluate the model to understand how well it performs.

Validation helps determine whether the model can
produce reliable results.

### 2.6 Decision-Making and Deployment

Use the evaluation results to decide whether the model
is suitable for its intended purpose.

A model that is ready for use can then be deployed
into an application or system.

## 3. Basic Machine Learning Terminology

### Target

The category or value that a model attempts to predict.

### Features

The explanatory variables used by a model to make
predictions.

### Example or Observation

A single data point in a dataset, usually represented
by one row in a table.

### Label

The actual value of the target variable for a
specific observation.

## 4. Example: Iris Dataset

In the Iris dataset, a flower can be represented
by several measurements:

- Sepal length
- Sepal width
- Petal length
- Petal width

These measurements are features used to predict
the flower species.

The flower species is the target variable.

Each row represents one observation, while the
actual species recorded for that row is its label.

## 5. Machine Learning Libraries

The course introduces several Python libraries:

| Library | Main Purpose |
|---|---|
| NumPy | Numerical analysis |
| Pandas | Data manipulation and DataFrames |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine Learning |
| TensorFlow | Deep Learning |
| Keras | Deep Learning |

Jupyter Notebook is also used as an environment
for working with Python code and data.

## Key Takeaways

- A Machine Learning project follows several development steps.
- Data preparation is an important part of the workflow.
- Features are used to predict the target.
- An observation represents one data point.
- A label is the actual target value for an observation.