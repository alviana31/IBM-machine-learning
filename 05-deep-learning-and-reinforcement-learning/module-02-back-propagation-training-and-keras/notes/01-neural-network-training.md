# Neural Network Training

## 1. Introduction

Training a neural network is the process of adjusting its weights so that the model can produce better predictions.

The training process involves feed-forward computation, loss calculation, backpropagation, and weight updates.

## 2. Steps to Train a Multi-Layer Perceptron

The training process consists of the following steps:

1. Initialize weights with random values between -1 and 1.
2. Perform feed-forward computation.
3. Compute the loss function.
4. Calculate gradients for all weights through backpropagation.
5. Update weight matrices using a learning rate.
6. Repeat steps 2–5 for a fixed number of iterations.
7. Plot accuracy and log loss to observe their changes during training.

## 3. Feed-Forward Computation

Feed-forward is the process of passing input data through the network to generate predictions.

The input values are combined with weights to produce Z-values. An activation function then transforms these values into A-values, which are passed to the next layer.

## 4. Loss Function

A loss function measures the difference between the model's predictions and the actual target values.

The loss value is used during training to determine how much the model needs to improve.

## 5. Training Evaluation

Accuracy and log loss can be plotted during training to observe how the model performs over multiple iterations.