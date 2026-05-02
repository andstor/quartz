---
title: Transformers
date: "2026-05-02"
tags: [ai, architecture]
---
# Transformers

The **Transformer** is a neural network architecture introduced in the 2017 paper *Attention Is All You Need* by Vaswani et al. It replaced recurrence with **self-attention**, enabling models to process sequences in parallel and capture long-range dependencies efficiently.

## Core mechanism

The key innovation is **scaled dot-product attention**:

$$
\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V
$$

Queries, keys, and values are linear projections of the input. Multiple attention heads run in parallel, each learning different relationship patterns.

## Architecture

The original Transformer has two halves:

- **Encoder** — processes the input sequence into contextual representations (used in [[BERT]], sentence embeddings)
- **Decoder** — generates output tokens autoregressively, attending to both the encoder output and previously generated tokens (used in [[Large Language Models|LLMs]])

Modern LLMs like GPT are *decoder-only*, while embedding models are often *encoder-only*.

## Why it matters

- **Parallelism**: Unlike RNNs, all positions are processed simultaneously during training
- **Scalability**: Performance improves predictably with more data and compute (scaling laws)
- **Versatility**: The same architecture handles text, code, images (ViT), audio, and multimodal inputs

## Landmark models

| Model | Type | Notable for |
|-------|------|-------------|
| BERT | Encoder | Bidirectional pre-training |
| GPT series | Decoder | Generative language modeling |
| T5 | Encoder-decoder | Text-to-text framing |
| Vision Transformer (ViT) | Encoder | Applying attention to image patches |

## Related

- [[Deep Learning]]
- [[Large Language Models]]
- [[Embeddings]]
