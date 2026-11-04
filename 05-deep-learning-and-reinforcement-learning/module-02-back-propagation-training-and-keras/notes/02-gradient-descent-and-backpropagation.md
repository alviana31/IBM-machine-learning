# Gradient Descent and Backpropagation

## 1. Gradient Descent

Gradient descent is an optimization method used to minimize the cost function by updating the parameters of a neural network.

The process starts with initial weights and updates them iteratively based on the calculated gradients.

## 2. Learning Rate

The learning rate controls the size of each update during optimization.

- A learning rate that is too large may cause unstable updates.
- A learning rate that is too small may make training slower.

## 3. Backpropagation

Backpropagation is the process of calculating gradients for the weights in a neural network.

These gradients are used to determine how the weights should be updated to reduce the loss function.

## 4. Gradient Descent Variations

### Full-Batch Gradient Descent

Uses the entire training dataset to calculate each update.

### Stochastic Gradient Descent (SGD)

Updates the model using individual data points. This introduces randomness into the optimization process.

### Mini-Batch Gradient Descent

Uses a subset of training data for each update. It provides a balance between computational efficiency and training stability.

## 5. Data Shuffling

Data shuffling changes the order of training data during each epoch.

This helps the model avoid learning from a fixed data order and supports better convergence.