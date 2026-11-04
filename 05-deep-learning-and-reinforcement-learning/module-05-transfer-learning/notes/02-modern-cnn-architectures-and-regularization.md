# Modern CNN Architectures and Regularization

## 1. Inception V3

Inception is a CNN architecture that focuses on increasing network width and depth while maintaining computational efficiency.

It uses Inception modules to process different feature maps in parallel.

These modules combine:

- Convolutions with different filter sizes.
- Pooling operations.
- Parallel feature extraction.

The outputs from different branches are combined through filter concatenation.

## 2. ResNet-50

ResNet-50 is a deep CNN architecture that uses special skip connections and batch normalization.

Skip connections allow the output of an earlier layer to be added directly to a later layer.

This helps deep networks learn residual mappings and supports convergence without compromising model accuracy.

The main building blocks include:

- Convolution blocks.
- Identity blocks.

The residual mapping can be represented as:

\[
F(x)+x
\]

Where:
- \(F(x)\) is the learned residual mapping.
- \(x\) is the original input.

## 3. Regularization Techniques

The course introduces several techniques to reduce overfitting in neural networks.

### L1 (Lasso) Regularization

Adds a penalty based on the absolute values of model weights.

### L2 (Ridge) Regularization

Adds a penalty based on the squared values of model weights.

### Dropout

Randomly removes a subset of neurons during training to prevent excessive dependence on specific neurons.

### Batch Normalization

A technique used in neural networks to normalize layer activations during training.

### Data Shuffling

Changes the order of training samples to support better model convergence.

## 4. Key Takeaways

- Transfer Learning reduces the need to train large models from scratch.
- Fine-tuning helps pretrained models adapt to new tasks.
- Inception V3 uses parallel feature extraction.
- ResNet-50 uses skip connections to support deep network training.
- Regularization techniques help reduce overfitting.