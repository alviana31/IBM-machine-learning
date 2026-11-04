# Sequence-to-Sequence Models and Beam Search

## 1. Sequence-to-Sequence Models

Sequence-to-Sequence (Seq2Seq) models are designed to process an input sequence and generate an output sequence.

They use an encoder, a hidden state, and a decoder.

### Main Components

- **Encoder:** Processes the input sequence and produces a hidden representation.
- **Hidden State:** Stores information from the input sequence.
- **Decoder:** Uses the hidden representation to generate the output sequence.

The hidden state contains information about the previous words in the input sentence.

Its vector size remains the same regardless of the sentence length.

## 2. Beam Search

Beam Search is a decoding method used to improve sequence generation.

It addresses a limitation of greedy inference, where the model selects one word at a time based on the most likely choice.

If an incorrect word is selected early, it can affect the entire generated sequence.

Beam Search maintains multiple possible sequence hypotheses and compares them until the end-of-sequence token (EOS) is reached.

The most likely complete sequence is then selected.

## 3. Key Takeaways

- Seq2Seq uses an encoder and decoder to process sequences.
- Hidden states transfer information between sequence steps.
- Beam Search considers multiple possible outputs.
- Beam Search can produce better complete sequences than choosing each word independently.