# Building Neural Networks with Keras

## 1. Introduction to Keras

Keras is a high-level library used to build and train neural network models. It can run on different backends, including TensorFlow.

Keras simplifies neural network implementation through a straightforward programming interface.

## 2. Training Workflow

A common workflow for training a neural network with Keras consists of:

1. Compile the model by specifying the loss function, metrics, and optimizer.
2. Fit the model using training data, batch size, and number of epochs.
3. Make predictions on new data.
4. Evaluate the model's results.

## 3. Creating a Sequential Model

The Sequential model allows layers to be added one by one.

Example:

```python
from keras.models import Sequential
from keras.layers import Dense, Activation

model = Sequential()

# First layer
model.add(Dense(units=4, input_dim=3))
model.add(Activation('sigmoid'))

# Second layer
model.add(Dense(units=4))
model.add(Activation('sigmoid'))
```

## 4. Model Compilation

Before training, the model needs to be compiled by specifying:

- Loss function
- Optimizer
- Evaluation metrics

## 5. Model Training

The `fit()` method is used to train the model using the training dataset.

Important parameters include:

- `batch_size`: Number of samples processed in each batch.
- `epochs`: Number of complete passes through the training dataset.

## 6. Prediction and Evaluation

After training, the model can use `predict()` to generate predictions and `evaluate()` to measure its performance on a dataset.