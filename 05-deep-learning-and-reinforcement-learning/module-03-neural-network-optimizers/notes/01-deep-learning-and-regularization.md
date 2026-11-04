# Deep Learning and Regularization

## 1. Deep Learning

A deep neural network technically has two or more hidden layers, often with many additional layers.

Deep Learning uses neural networks to identify patterns and relationships in data that may be difficult to observe directly.

It can be applied to:

- Supervised Learning
- Unsupervised Learning
- Semi-Supervised Learning

Deep Learning can also reduce the need for manual feature engineering.

## 2. Regularization

Regularization is used to prevent overfitting and improve the generalization of neural networks.

Common regularization techniques include:

### Regularization Penalty

A penalty is added to the cost function to control the size of model weights.

Example of a regularized loss function:

\[
L=\frac{1}{2n}\sum_{i=1}^{n}(\hat{y}_i-y_i)^2+
\lambda\sum_{j=1}^{m}W_j^2
\]

The additional penalty helps prevent the model from relying too heavily on large weight values.

### Dropout

Dropout randomly removes a subset of neurons during each training iteration or batch.

Its purpose is to prevent the network from depending too much on specific neurons and make the model more robust.

During testing, neuron weights are rescaled to reflect the proportion of time they were active during training.

### Early Stopping

Early stopping is a technique that stops training when the model's performance starts to get worse.

Example:

- Check validation log loss every 10 epochs.
- If the validation log loss becomes higher than the previous check, stop training.
- Use the previous model with better validation performance.

## 3. Other Regularization Techniques

The course also introduces:

- L2 (Ridge) regularization
- L1 (Lasso) regularization
- Dropout
- Batch Normalization
- Data Shuffling