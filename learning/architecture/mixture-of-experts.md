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

## Kimi K3 case study

The Kimi K3 technical report describes Stable LatentMoE, which projects the 7,168-dimensional hidden state into a 3,584-dimensional latent space before the expert layers. Its architecture table lists 896 routed experts with 16 active per token, two shared experts, 2.8 trillion total parameters, and 104 billion active parameters. This is a concrete example of why total and active parameter counts must be reported separately.

The same report presents the latent projection and training recipe as stability and efficiency improvements. Treat those conclusions as author-reported until they are reproduced independently.

**Source:** Moonshot AI, *Kimi K3: Open Frontier Intelligence.* (2026). [Technical report](https://github.com/MoonshotAI/Kimi-K3/blob/main/k3_tech_report.pdf)

## Read it when

- You see a model report "total parameters" and "active parameters" separately.
- You are comparing dense and sparse model serving costs.
- You need to understand expert parallelism or routing failures.

## Related entries

- `learning/papers/scaling-laws.md` — explains why adding capacity matters.
- `providers/models/README.md` — model directories often need to distinguish dense and sparse lines.
- `providers/moonshot/models/kimi-k3.md` — hosted, open-weight, and report-backed Kimi K3 details.
- `self-hosted/hardware/README.md` — MoE inference has memory and routing implications beyond raw parameter count.

## Status

`[paper]`. Last reviewed 2026-08-06.
