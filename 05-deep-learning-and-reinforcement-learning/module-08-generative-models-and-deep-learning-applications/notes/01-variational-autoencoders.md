# Variational Autoencoders (VAE)

## 1. Introduction to VAE

A Variational Autoencoder (VAE) is a generative model that learns a representation of data in a latent space.

Unlike a basic autoencoder that maps input data into a compressed representation, a VAE learns probability distributions for its latent variables.

The latent factors are modeled using a normal distribution.

## 2. VAE Architecture

A VAE consists of an encoder and a decoder.

### Encoder

The encoder processes the input data and produces two important parameters:

- Mean (\(\mu\)): Represents the center of the latent probability distribution.
- Standard Deviation (\(\sigma\)): Represents the spread of the distribution.

These parameters define the distribution used to sample a latent representation.

### Latent Space

The latent representation is sampled from the probability distribution defined by the encoder.

This allows the model to represent variations in the input data.

### Decoder

The decoder receives the sampled latent representation and attempts to generate or reconstruct an output.

## 3. How VAE Works

The general process is:

1. Input data is passed to the encoder.
2. The encoder calculates the mean (\(\mu\)) and standard deviation (\(\sigma\)).
3. A latent representation is sampled from the learned distribution.
4. The sampled representation is passed to the decoder.
5. The decoder generates an output.
6. The model evaluates the generated output using its loss function.

```text
Input Data
    |
    v
  Encoder
    |
    v
 Mean (μ) and Standard Deviation (σ)
    |
    v
 Latent Sampling
    |
    v
  Decoder
    |
    v
Generated / Reconstructed Output
```

## 4. VAE Loss Function

The VAE objective combines two main components:

### Reconstruction Loss

Measures how different the generated or reconstructed output is from the original input.

The model aims to produce an output that is similar to the original data.

### Regularization Loss

Encourages the learned latent distribution to remain close to a standard normal distribution.

The standard normal distribution has:

- Mean = 0
- Standard Deviation = 1

The overall objective can be represented as:

\[
L = L_{\text{reconstruction}} + L_{\text{regularization}}
\]

## 5. Applications of VAE

VAEs can be used to generate new samples and learn structured latent representations.

One example covered in the course material is image generation.

The model learns latent factors and uses samples from the learned distributions to generate images.

## 6. Key Takeaways

- VAE is a generative model based on latent probability distributions.
- Its encoder produces mean and standard deviation parameters.
- The decoder uses sampled latent representations to generate outputs.
- Its loss combines reconstruction and regularization components.
- The regularization component encourages the latent distribution to approach a standard normal distribution.