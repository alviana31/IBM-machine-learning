# Recurrent Neural Networks (RNNs)

## 1. Introduction to RNN

Recurrent Neural Networks (RNNs) are neural networks that use previous outputs as inputs while maintaining hidden states.

RNNs are commonly used for sequential data, especially in:

- Natural Language Processing
- Speech Recognition
- Time Series Forecasting

## 2. How RNNs Work

RNNs process input data one step at a time. Each new input updates the hidden state based on the previous state and the current input.

This allows the network to consider the context of previous inputs.

The two main outputs of an RNN are:

- **Prediction:** The output generated at a particular sequence step.
- **State:** A summary of information from previous steps.

The general process can be represented as:

\[
h_t=f(h_{t-1},x_t)
\]

\[
y_t=g(h_t)
\]

Where:
- \(h_t\) = Current hidden state.
- \(h_{t-1}\) = Previous hidden state.
- \(x_t\) = Current input.
- \(y_t\) = Current output.

## 3. Mathematical Components

The course introduces three weight matrices:

- \(U\): Input-to-hidden weights, with dimensions \(s \times r\).
- \(W\): Hidden-to-hidden weights, with dimensions \(s \times s\).
- \(V\): Hidden-to-output weights, with dimensions \(t \times s\).

These weight matrices are shared across all positions in the sequence.

## 4. Backpropagation Through Time (BPTT)

Backpropagation Through Time is a training method used for RNNs.

It applies backpropagation across the sequence steps to update the network parameters.

## 5. RNN Limitations

RNNs can experience vanishing and exploding gradient problems, especially when processing long sequences.

In practice, sequence lengths are often limited:

- Padding is applied when an input is shorter than the maximum sequence length.
- Truncation is applied when an input is longer than the maximum sequence length.

## 6. RNN Applications

RNNs can be applied to different types of sequential data:

- Sales forecasting
- Loss rate prediction
- Network traffic forecasting
- Speech recognition
- Manufacturing sensor data
- Genome sequences