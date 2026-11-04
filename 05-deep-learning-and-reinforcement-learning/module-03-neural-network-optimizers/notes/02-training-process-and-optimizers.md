# Neural Network Training Process and Optimizers

## 1. Training Neural Networks

Training neural networks requires careful calculation of weight derivatives and a process that allows the model to reach convergence.

The training process can be affected by how data is presented and how gradients are calculated.

## 2. Batching Methods

Batching methods determine how training data is used to calculate gradients and update model weights.

The course introduces three methods:

### Full-Batch Gradient Descent

Uses the entire training dataset to calculate gradients for an update.

### Mini-Batch Gradient Descent

Uses a smaller subset of the training dataset for each update.

### Stochastic Gradient Descent (SGD)

Uses individual data points to calculate updates, introducing randomness into the training process.

## 3. Data Shuffling

Data shuffling changes the order of training samples during each epoch.

This helps the model avoid processing data in the same fixed order and supports better convergence.

## 4. Neural Network Optimizers

Optimizers are methods used to adjust neural network weights during training.

They improve the weight-update process using approaches beyond basic gradient descent.

The main purpose of an optimizer is to help the model minimize its loss function and reach convergence.

## 5. Important Training Concepts

- **Gradient:** Indicates how the loss changes with respect to model weights.
- **Convergence:** The process of reaching a stable optimization result.
- **Batch:** A subset of training data processed during an update.
- **Epoch:** One complete pass through the training dataset.
- **Optimizer:** A method used to update model parameters during training.