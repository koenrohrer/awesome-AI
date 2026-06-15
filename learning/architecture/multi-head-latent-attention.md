# Multi-head latent attention (MLA) `[paper]`

## One-sentence TL;DR

MLA reduces inference-time KV-cache pressure by storing a compressed latent representation of keys and values instead of full per-head key/value tensors.

## Citation

DeepSeek-AI, Aixin Liu, Bei Feng, Bin Wang, Bingxuan Wang, et al. (2024). *DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model.* [arxiv.org/abs/2405.04434](https://arxiv.org/abs/2405.04434)

## What the architecture does

Standard multi-head attention caches keys and values for every previous token at every layer. That cache speeds up autoregressive decoding, but it grows with sequence length, batch size, layer count, head count, and head dimension.

Multi-head latent attention changes what gets cached. DeepSeek-V2 projects the attention input into a low-rank latent vector for keys and values. Learned up-projections define the key/value views needed for attention, and the paper notes that those projections can be absorbed into query and output projections during inference. The cache stores the compressed latent vector rather than full key and value tensors.

DeepSeek-V2 also uses decoupled rotary position embeddings because ordinary RoPE conflicts with low-rank KV compression. The model caches the compressed KV latent plus a small decoupled positional key.

## What the paper claims

The DeepSeek-V2 paper reports that MLA reduces KV cache by 93.3% and raises maximum generation throughput to 5.76x versus DeepSeek 67B in the authors' comparison. It also reports stronger ablation performance than MHA, GQA, and MQA in the DeepSeek-V2 setting.

Treat these as paper-reported results, not a portable runtime guarantee. DeepSeek-V2 also changes model scale, MoE routing, training data, and implementation details, so the headline throughput number is not MLA in isolation.

## Why it matters

- KV cache can dominate memory use during long-context decoding.
- MLA reduces cache size at the model-architecture level rather than only paging or quantizing an existing cache.
- Smaller cache can increase feasible batch size or context length when memory bandwidth is the serving bottleneck.
- Efficient use depends on runtime support for MLA kernels and the exact model implementation.

## Read it when

- You are evaluating DeepSeek-family inference-efficiency claims.
- You need to compare MHA, MQA, GQA, and MLA cache tradeoffs.
- You are separating model-architecture KV savings from runtime techniques like PagedAttention or KV quantization.

## Related entries

- `learning/architecture/kv-cache.md` — the inference bottleneck MLA targets.
- `learning/architecture/mixture-of-experts.md` — DeepSeek-V2 combines MLA with sparse expert routing.
- `learning/architecture/turboquant.md` — compresses KV-cache vectors after the model architecture has produced them.

## Status

`[paper]`. Current as of 2026-06-15; re-check serving-stack support before treating MLA as available for a specific runner or model family.
