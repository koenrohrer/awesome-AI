# Attention Is All You Need `[paper]`

## One-sentence TL;DR

Introduces the **Transformer** — an architecture built entirely on self-attention with no recurrence or convolutions. Sets the foundation for essentially every modern LLM.

## Citation

Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., Kaiser, Ł., & Polosukhin, I. (2017). *Attention Is All You Need.* NeurIPS 2017. [arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762)

## What the paper introduced

- **Self-attention as the sole sequence-modeling primitive.** Replaces the RNN/CNN stacks that dominated sequence modeling at the time.
- **Multi-head attention.** Multiple parallel attention computations, concatenated and projected — each "head" can attend to different aspects of the input.
- **Positional encoding.** Since the architecture has no inherent notion of order, positions are injected additively via sinusoidal encodings.
- **Encoder-decoder structure** for the original machine-translation task. Modern decoder-only LLMs (GPT family) use only the decoder half.

## Why it's the bedrock paper

Every subsequent LLM inherits the core machinery. Understand the transformer and you understand why scaling laws work the way they do, why context-window extensions are non-trivial (attention is quadratic in sequence length), why long-context / sparse-attention / linear-attention variants exist, and why mixture-of-experts layers fit so naturally into the stack.

## Read it when

- You're first learning how LLMs work under the hood.
- You're about to modify inference (KV cache, attention kernels, context extension).
- You're evaluating architectural claims ("Mamba replaces attention," "RWKV is attention-free") — you need the baseline to compare against.

## Related entries

- `learning/papers/scaling-laws.md` — what happens when you scale transformers up.
- `learning/papers/instructgpt.md` — how you make transformers useful beyond next-token prediction.

## Status

`[paper]`.
