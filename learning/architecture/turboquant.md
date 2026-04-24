# TurboQuant `[paper]`

## One-sentence TL;DR

TurboQuant is an online vector quantization method aimed at compressing KV cache and vector-search embeddings while preserving inner-product quality.

## Citation

Zandieh, A., Daliri, M., Hadian, M., & Mirrokni, V. (2025). *TurboQuant: Online Vector Quantization with Near-optimal Distortion Rate.* [arxiv.org/abs/2504.19874](https://arxiv.org/abs/2504.19874)

## Official research post

Google Research introduced TurboQuant publicly in March 2026: [TurboQuant: Redefining AI efficiency with extreme compression](https://research.google/blog/turboquant-redefining-ai-efficiency-with-extreme-compression/).

## What the method does

TurboQuant targets high-dimensional vectors, including the keys and values stored in transformer KV caches. It randomly rotates vectors, applies scalar quantization to the rotated coordinates, then uses a 1-bit Quantized Johnson-Lindenstrauss residual step to reduce bias in inner-product estimates.

That matters because attention depends on dot products. A KV compression method that saves memory but corrupts attention scores can degrade generation quality, especially on long-context tasks.

## What the paper claims

The paper reports near-optimal distortion rates, quality-neutral KV cache quantization around 3.5 bits per channel, marginal degradation around 2.5 bits per channel, and strong nearest-neighbor recall with very low indexing time.

Google's research post additionally reports long-context evaluations on open-source Gemma and Mistral models, with at least 6x KV memory reduction on needle-in-a-haystack-style tasks and up to 8x attention-logit speedup on H100 for a 4-bit setting.

Treat those as paper/provider claims until reproduced in the specific runtime, model family, hardware, and context lengths you care about.

## Why it matters

- KV cache, not model weights, can dominate memory use at long context.
- Quantizing the cache is a different problem from quantizing weights.
- Deployment value depends on kernel support and integration into inference engines, not just the algorithm.

## Read it when

- You are comparing KV cache compression methods like KIVI, SnapKV, PyramidKV, and TurboQuant.
- You are trying to serve long-context workloads under tight GPU memory limits.
- You need to separate memory-stock headlines from actual inference-system tradeoffs.

## Related entries

- `learning/architecture/kv-cache.md` — the cache bottleneck TurboQuant targets.
- `self-hosted/runners/README.md` — runtime support will determine whether this is usable outside research code.
- `self-hosted/hardware/README.md` — memory savings are hardware- and workload-dependent.

## Status

`[paper]`. Current as of 2026-04-24; re-check framework support before presenting TurboQuant as production-ready.
