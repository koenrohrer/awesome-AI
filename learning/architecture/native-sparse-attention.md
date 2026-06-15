# Native Sparse Attention / DeepSeek Sparse Attention `[paper]`

## One-sentence TL;DR

Native Sparse Attention uses trainable sparse attention paths to reduce long-context attention work while preserving coarse, selected, and local context.

## Citations

- Yuan, J., Gao, H., Dai, D., Luo, J., Zhao, L., Zhang, Z., Xie, Z., Wei, Y. X., Wang, L., Xiao, Z., Wang, Y., Ruan, C., Zhang, M., Liang, W., & Zeng, W. (2025). *Native Sparse Attention: Hardware-Aligned and Natively Trainable Sparse Attention.* [arxiv.org/abs/2502.11089](https://arxiv.org/abs/2502.11089)
- DeepSeek-AI, Aixin Liu, Aoxue Mei, Bangcai Lin, Bing Xue, et al. (2025). *DeepSeek-V3.2: Pushing the Frontier of Open Large Language Models.* [arxiv.org/abs/2512.02556](https://arxiv.org/abs/2512.02556)

## What the architecture does

Full attention compares each query against every previous key. That gives broad context access, but it makes long sequences expensive during training, prefill, and decoding.

Native Sparse Attention replaces that full scan with three trainable attention paths:

- **Compressed attention** summarizes key/value blocks into coarse tokens.
- **Selected attention** keeps fine-grained blocks that look important for the current query.
- **Sliding-window attention** preserves local context around the current token.

The NSA paper designs those paths around contiguous blocks and grouped-query attention so sparse attention can map to GPU-friendly kernels rather than only reducing theoretical FLOPs.

## How DeepSeek Sparse Attention fits

DeepSeek's V3.2 paper names DeepSeek Sparse Attention (DSA) as a key mechanism for reducing long-context computational cost while preserving model performance. It describes DSA as a lightning indexer plus fine-grained token selection, instantiated under Multi-head Latent Attention (MLA).

Do not treat DSA as the same mechanism as the NSA paper's three-path design. Treat both as DeepSeek sparse-attention work aimed at long-context efficiency.

## What the papers claim

The NSA paper reports that a 27B-parameter MoE backbone trained with NSA maintains or exceeds a full-attention baseline across general, long-context, and instruction-reasoning evaluations. It also reports speedups over full attention on 64k-token sequences for decoding, forward propagation, and backward propagation.

The DeepSeek-V3.2 paper reports DSA as the only architectural modification from DeepSeek-V3.1-Terminus to V3.2. Its model-level benchmark results also include reinforcement learning, agentic data synthesis, and other training changes. Do not attribute V3.2 quality claims to sparse attention alone.

## Why it matters

- Sparse attention targets the quadratic cost of full attention, not only KV-cache storage.
- Trainable sparse attention avoids bolting an inference-only pruning rule onto a model trained for full attention.
- Hardware-aligned block selection matters because irregular sparse reads can erase theoretical speedups.
- Practical value depends on model support and serving kernels, not just the attention pattern.

## Read it when

- You are evaluating long-context inference cost claims from DeepSeek-family models.
- You need to distinguish sparse attention from KV-cache paging, quantization, or eviction.
- You are comparing inference-only sparse methods with architectures trained natively for sparse attention.

## Related entries

- `learning/architecture/kv-cache.md` — cache reuse remains part of long-context serving even when attention is sparse.
- `learning/architecture/mixture-of-experts.md` — the NSA experiments use an MoE backbone.
- `learning/architecture/multi-token-prediction.md` — speculative decoding targets serial decode latency rather than attention sparsity.

## Status

`[paper]`. Current as of 2026-06-15; re-check model and runtime support before treating DSA/NSA as available in a specific serving stack.
