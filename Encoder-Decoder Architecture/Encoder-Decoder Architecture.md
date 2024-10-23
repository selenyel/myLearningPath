# Generative AI Advancements

Exciting developments in Generative AI, including new Vertex AI features:
- GenAI Studio
- Model Garden
- Gen AI API

---

## Encoder-Decoder Architecture

- Example: *The cat ate the mouse* → *Le chat a mangé la souris*.
- Takes sequences as input and generates sequences as output.

### Encoder Stage
- Produces a vector representation of the input sentence.

### Decoder Stage
- Generates the output sequence one token at a time, using the current state and previously decoded tokens.

---

## RNN and Transformer Blocks

The internal mechanism of an encoder-decoder can be:
- **RNN (Recurrent Neural Network)** or
- **Transformer Blocks** as in modern powerful language models.

### RNN Encoder
- Takes each token in the input sequence one at a time.
- Produces a state representing the token and all previously ingested tokens.

### RNN Decoder
- Uses the encoded vector representation of the input to produce an output sequence, one token at a time, by combining the current state with previously decoded tokens.

---

## Training Phase

- Requires **input-output pairs** (e.g., source-target language sentence pairs).
- The model adjusts its weights based on the error between the generated output and the true output.

### Error Calculation
- Difference between what the neural network generates and the true output sequence in your dataset.

### Teacher Forcing Method
- Instead of learning from its own faulty output, the machine is fed the correct output to guide it through the learning process.

---

## Decoder Token Generation

There are different approaches to generating output tokens:
1. **Greedy Search**: Selects the token with the highest probability.
2. **Beam Search**: Evaluates the probability of sentence chunks instead of individual tokens, keeping the most likely sequence.

---

## Sample Code

```python
model = keras.Sequential()
model.add(Embedding(input_dim=1000, output_dim=64))
model.add(GRU(256, return_sequences=True))
model.add(Dense(VOCAB_SIZE, activation="softmax"))


In this example:

The embedding layer turns tokens into vector representations.
The GRU layer processes the sequence.
The dense softmax layer generates the word probabilities.

---

Attention Mechanism and Transformer Models
The key difference between RNN-based methods and transformer-based methods is the attention mechanism.

---

___________________________________

| The cat ate the mouse. (finish) |
___________________________________

     X ---> unroll the RNN inputs
     H
(Hin)|
     |
     v
     _
  P |Y| ---> Dense softmax layer
     -
     |
     v
  ______
  | Le | ---> First token output
  ______


---

This state is passed to the softmax layer to produce the word probabilities.

model.add(Dense(VOCAB_SIZE, activation="softmax"))

---

Key Notes
Greedy Search: Takes the highest probability token.
Beam Search: Generates more likely sentence chunks.
Attention Mechanism: Improves upon RNNs in transformer models.
