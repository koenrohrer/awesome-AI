# Kimi Linear / Kimi Delta Attention (KDA) `[paper]`

## One-sentence TL;DR

Kimi Linear is a hybrid attention architecture that mixes Kimi Delta Attention with MLA to reduce long-context cache and decode costs.

## Citation

Kimi Team, Yu Zhang, Zongyu Lin, Xingcheng Yao, Jiaxi Hu, Fanqing Meng, et al. (2025). *Kimi Linear: An Expressive, Efficient Attention Architecture.* [arxiv.org/abs/2510.26692](https://arxiv.org/abs/2510.26692)

## What the architecture does

Full softmax attention keeps a KV cache that grows with sequence length. Linear attention replaces that unbounded history with a recurrent state, but earlier variants often lost quality on tasks that depend on long-range retrieval or precise memory updates.

Kimi Linear is a hybrid design. Its core module, Kimi Delta Attention (KDA), extends Gated DeltaNet with finer-grained gating so the model can update a limited recurrent memory more selectively. The published Kimi Linear model mixes KDA layers with Multi-head Latent Attention (MLA) layers in a 48B-total-parameter MoE model with 3B activated parameters.

The paper also introduces a chunkwise algorithm for KDA that uses a specialized diagonal-plus-low-rank transition structure. That implementation detail matters because linear-attention designs only help deployment if their kernels are efficient on real hardware.

## What the paper claims

The paper reports that, under the same training recipe, Kimi Linear outperforms a full-MLA baseline across the evaluated short-context, long-context, and reinforcement-learning settings. It also reports up to 75% lower KV-cache usage and up to 6x decoding throughput at 1M context.

Treat these as paper-reported results. The evaluated model is a specific hybrid of KDA, MLA, and MoE, so the headline numbers are not a generic guarantee for every linear-attention model or serving stack.

## Why it matters

- Linear attention changes the sequence-mixing architecture rather than only compressing an existing KV cache.
- KDA targets long-context decoding where cache growth and memory movement dominate cost.
- Hybrid KDA/MLA placement acknowledges that linear attention and full attention have different strengths.
- Runtime support matters because KDA needs specialized kernels and serving integration.

## Read it when

- You are comparing softmax attention, MLA, and linear-attention long-context tradeoffs.
- You need to evaluate claims about constant-state or reduced-cache decoding.
- You are deciding whether a Kimi Linear checkpoint or KDA runtime path fits a long-context workload.

## Related entries

- `learning/architecture/kv-cache.md` — the cache bottleneck Kimi Linear tries to reduce.
- `learning/architecture/mixture-of-experts.md` — the reported Kimi Linear model uses sparse expert routing.
- `learning/architecture/turboquant.md` — compresses vectors after the model has produced them, rather than changing the attention architecture.

## Status

`[paper]`. Current as of 2026-06-15; re-check checkpoint and runtime support before treating KDA speedups as available in a specific serving stack.
