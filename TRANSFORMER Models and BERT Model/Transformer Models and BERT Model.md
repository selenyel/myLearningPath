# Summary of Transformers

## Introduction
- Hi, I'm **Sanjana Reddy**, a machine learning engineer at Google's Advanced Solutions Lab.
- There has been significant excitement around generative AI and new advancements, including features like Gen AI Studio, Model Garden, and Gen AI API.
- This session aims to provide a solid understanding of the underlying concepts behind generative AI, specifically focusing on transformer models and the BERT model.

## Evolution of Language Modeling
- Language modeling has evolved over the years:
  - **2013**: Introduction of neural networks to represent text (e.g., Word2Vec, N-grams).
  - **2014**: Development of sequence-to-sequence models (RNNs, LSTMs) improved NLP tasks like translation and text classification.
  - **2015**: Breakthroughs with attention mechanisms and models like Transformers and BERT.

## Transformer Architecture
- **Transformers** are based on the 2017 paper "Attention Is All You Need."
- Previous models could represent words as vectors but lacked context, leading to issues with words like "bank."

## Transformer Architecture
- A **Transformer** is an encoder-decoder model utilizing attention mechanisms.
- It processes large amounts of data simultaneously and improves machine translation performance.
- The architecture consists of:
  - An **Encoder**: Encodes the input sequence.
  - A **Decoder**: Decodes the encoded representation for specific tasks.

## Encoder and Decoder Components
- The encoder consists of multiple identical layers (e.g., six in the original paper).
- Each encoder has two sub-layers:
  1. **Self-Attention Layer**: Encodes relevant parts of the input words.
  2. **Feedforward Layer**: Processes the output from the self-attention layer.

- The decoder also has self-attention and feedforward layers, along with an encoder-decoder attention layer to focus on relevant input parts.

## Self-Attention Mechanism
- Input embeddings are divided into **query, key,** and **value** vectors, computed with learned weights.
- These vectors allow the model to focus on relevant words by applying softmax scores to values.
- Final embeddings are produced by performing multi-headed attention and concatenating results.

## Variations of Transformers
- There are various transformer models now, including:
  - **BERT (Bidirectional Encoder Representations from Transformers)**: Developed by Google in 2018, uses only the encoder component.
  - BERT has two versions: **BERT Base** (12 layers) and **BERT Large** (24 layers).

## BERT Training and Functionality
- BERT was trained on two tasks:
  1. **Masked Language Model**: Predicting masked words in a sentence (masking 15% of words).
  2. **Next Sentence Prediction**: Learning relationships between two sentences.

- To train BERT, three embeddings are provided:
  1. **Token Embeddings**: Representing each token in the input.
  2. **Segment Embeddings**: Identifying different segments in input pairs.
  3. **Position Embeddings**: Learning the order of words in the sequence.

## Applications of BERT
- BERT can solve various NLP tasks, including:
  - Text classification
  - Sentence pair classification
  - Question answering
  - Single sentence tagging

## Conclusion
- Transformers and BERT significantly enhance NLP capabilities through advanced attention mechanisms and multi-task training.
