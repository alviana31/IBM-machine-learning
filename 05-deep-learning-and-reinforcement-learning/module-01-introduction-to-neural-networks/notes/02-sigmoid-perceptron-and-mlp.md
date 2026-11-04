# Sigmoid, Perceptron, and Multi-Layer Perceptron

## 1. Sigmoid Activation Function

The sigmoid function is an activation function that converts input values into a range between 0 and 1.

Its formula is:

\[
\sigma(x)=\frac{1}{1+e^{-x}}
\]

Characteristics:

- When x is negative, the output approaches 0.
- When x is positive, the output approaches 1.
- When x = 0, the output is 0.5.
- The function is differentiable, making it useful in neural network training.

## 2. Perceptron

A perceptron is one of the basic building blocks of a neural network.

It receives input values, combines them using weights, and applies an activation function to produce an output.

The perceptron is similar to Logistic Regression because both use weighted inputs and an activation function.

## 3. Multi-Layer Perceptron (MLP)

A Multi-Layer Perceptron is a neural network consisting of multiple layers of interconnected neurons.

It consists of:

- Input Layer
- One or more Hidden Layers
- Output Layer

By stacking multiple layers, an MLP can learn more complex patterns and create non-linear decision boundaries.

## 4. Feed-Forward Computation

Feed-forward is the process of passing input data through the network from the input layer to the output layer.

The general process is:

1. Input data enters the network.
2. Input values are multiplied by their weights.
3. The results are combined to produce Z-values.
4. An activation function transforms Z-values into A-values.
5. The output is passed to the next layer.
6. The final layer produces the prediction.

## 5. Steps to Build a Multi-Layer Perceptron

1. Initialize weights with random values between -1 and 1.
2. Perform feed-forward computation.
3. Calculate the loss function.
4. Calculate gradients for all weights using backpropagation.
5. Update weight matrices using a learning rate.
6. Repeat the process for a fixed number of iterations.
7. Plot accuracy and log loss to observe changes during training.

## 6. Implementation with Scikit-Learn

The course introduces building an MLP using Scikit-Learn. The implementation involves defining hidden layers and activation functions.

Further neural network implementations using Keras are covered in subsequent modules.