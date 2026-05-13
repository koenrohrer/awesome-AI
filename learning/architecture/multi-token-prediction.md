# Multi-token prediction (MTP) `[paper]`

## One-sentence TL;DR

Multi-token prediction asks a model or drafter to propose several future tokens, then uses the target model to verify those tokens in parallel instead of decoding strictly one token at a time.

## Citations

- Leviathan, Y., Kalman, M., & Matias, Y. (2023). *Fast Inference from Transformers via Speculative Decoding.* ICML 2023. [arxiv.org/abs/2211.17192](https://arxiv.org/abs/2211.17192)
- Gloeckle, F., Idrissi, B. Y., Roziere, B., Lopez-Paz, D., & Synnaeve, G. (2024). *Better & Faster Large Language Models via Multi-token Prediction.* [arxiv.org/abs/2404.19737](https://arxiv.org/abs/2404.19737)

## What the technique does

Standard autoregressive decoding emits one token per target-model step. That serial path is slow because every new token depends on the previous token, and large model inference is often limited by memory bandwidth rather than raw arithmetic.

Speculative decoding changes the serving pattern. A smaller approximation model proposes a short run of future tokens. The large target model evaluates those proposed positions in parallel, accepts the prefix that matches its own distribution, and corrects the first rejected token. When the draft is good, one target-model pass yields several output tokens while preserving the target model's output distribution.

Multi-token prediction is one way to make those draft tokens better. The Gloeckle et al. paper trains a model to predict the next `n` tokens from the same position using multiple output heads on a shared trunk. That auxiliary objective can improve sample efficiency and can also supply draft heads for faster inference.

## How Google used it in Gemma 4

Google's Gemma 4 docs use MTP as the architecture behind Gemma 4 speculative decoding. Instead of a fully independent draft model, Gemma 4's MTP drafter is a smaller assistant that shares the target model's input embedding table and consumes the target model's last-layer activations. Google also documents KV-cache sharing, so the drafter does not recompute context the target model already processed.

For the `E2B` and `E4B` edge models, Google adds an efficient embedder that clusters similar tokens and limits final vocabulary scoring to likely clusters. For `Gemma 4 26B A4B`, Google notes an MoE-specific caveat: at batch size 1, each drafted token can route to different experts and offset the gain from speculative verification. Higher batch sizes improve expert reuse and can unlock local speedups.

Google's May 2026 release post reports up to a 3x Gemma 4 inference speedup from MTP drafters, with no degradation in output quality because the primary Gemma 4 model still performs final verification. Treat that as a provider-reported speedup: realized gains depend on hardware, batch size, runtime support, draft acceptance rate, and generation length.

## Why it matters

- It targets decode latency, not model quality by itself.
- It is most useful when the target model has idle compute but is bottlenecked on serial token generation or memory movement.
- Dense models often benefit more cleanly than MoE models because verifying multiple tokens reuses the same dense weights.
- Short completions and low-acceptance tasks have less room to amortize drafter overhead.

## Read it when

- You are evaluating "tokens per second" claims for local or hosted inference.
- You need to separate prompt processing speedups from decode speedups.
- You are choosing runtimes for Gemma 4, Qwen, DeepSeek, or other models that expose draft heads or assistant models.

## Related entries

- `learning/architecture/kv-cache.md` — speculative drafters still depend on efficient cache reuse.
- `learning/architecture/mixture-of-experts.md` — MoE routing changes the economics of verifying multiple drafted tokens.
- `providers/google/models/gemma-4.md` — Google-specific Gemma 4 deployment notes.

## Official implementation notes

- Google Gemma docs: [Speed-up Gemma 4 with Multi-Token Prediction](https://ai.google.dev/gemma/docs/mtp/overview)
- Google release post: [Accelerating Gemma 4: faster inference with multi-token prediction drafters](https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/)

## Status

`[paper]`. Current as of 2026-05-13; re-check runtime support before presenting an MTP speedup as available in a specific serving stack.
