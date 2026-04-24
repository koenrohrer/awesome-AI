# Mixture-of-experts (MoE) `[paper]`

## One-sentence TL;DR

MoE increases model capacity by routing each token or example through a sparse subset of expert networks instead of activating the whole model every time.

## Citations

- Shazeer, N., Mirhoseini, A., Maziarz, K., Davis, A., Le, Q., Hinton, G., & Dean, J. (2017). *Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer.* [arxiv.org/abs/1701.06538](https://arxiv.org/abs/1701.06538)
- Fedus, W., Zoph, B., & Shazeer, N. (2021). *Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity.* JMLR. [arxiv.org/abs/2101.03961](https://arxiv.org/abs/2101.03961)

## What the architecture does

A dense transformer applies the same feed-forward layers to every token. An MoE transformer replaces some dense feed-forward blocks with multiple expert networks plus a router. For each token, the router selects one or a few experts, so only a sparse slice of the total parameters is active.

This lets the model have many more total parameters than it uses per token. The tradeoff is systems complexity: routing, load balancing, all-to-all communication, expert parallelism, and training stability become central design problems.

## Why Switch Transformer matters

The original sparsely-gated MoE layer showed the capacity/computation idea. Switch Transformer simplified routing to one expert per token and showed large sparse models could train more efficiently, including lower-precision training.

That simplified version is the clearest starting point for understanding why many modern frontier and open-weight models advertise huge parameter counts while activating only a fraction per token.

## Read it when

- You see a model report "total parameters" and "active parameters" separately.
- You are comparing dense and sparse model serving costs.
- You need to understand expert parallelism or routing failures.

## Related entries

- `learning/papers/scaling-laws.md` — explains why adding capacity matters.
- `providers/models/README.md` — model directories often need to distinguish dense and sparse lines.
- `self-hosted/hardware/README.md` — MoE inference has memory and routing implications beyond raw parameter count.

## Status

`[paper]`.
