# KV cache and PagedAttention `[paper]`

## One-sentence TL;DR

KV cache stores attention keys and values from previous tokens so autoregressive decoding can reuse them; PagedAttention makes that cache manageable at serving scale.

## Citation

Kwon, W., Li, Z., Zhuang, S., Sheng, Y., Zheng, L., Yu, C. H., Gonzalez, J. E., Zhang, H., & Stoica, I. (2023). *Efficient Memory Management for Large Language Model Serving with PagedAttention.* SOSP 2023. [arxiv.org/abs/2309.06180](https://arxiv.org/abs/2309.06180)

## What KV cache does

Autoregressive models generate one token at a time. Without caching, each new token would require recomputing attention keys and values for all previous tokens. KV cache stores those tensors and reuses them on later decoding steps.

That makes generation much faster, but it moves the bottleneck to memory. Longer context windows, larger batches, beam search, parallel sampling, and chat workloads all increase cache pressure.

## What PagedAttention changed

PagedAttention applies an operating-system-style paging idea to KV cache. Instead of allocating large contiguous blocks for each request, it stores keys and values in fixed-size blocks that can be mapped, shared, and freed more flexibly.

That matters because live serving workloads are dynamic: requests enter and leave at different lengths, prompts vary widely, and decoding branches may share prefixes. Better cache management increases effective batch size without changing model weights.

## Why it matters

- KV cache is often the limiting resource for long-context inference.
- Serving throughput is not just "model speed"; it is also memory allocation, batching, and cache reuse.
- Techniques like prefix caching, paged attention, speculative decoding, and KV quantization all build on this same bottleneck.

## Read it when

- You are choosing between local runners or hosted inference engines.
- You are trying to understand why long context gets expensive.
- You are evaluating claims about KV cache compression, including TurboQuant and KIVI.

## Related entries

- `learning/architecture/turboquant.md` — compresses KV cache vectors rather than paging them.
- `learning/papers/attention-is-all-you-need.md` — the attention mechanism that creates keys and values.
- `self-hosted/runners/README.md` — where runner-specific serving tradeoffs will land.

## Status

`[paper]`.
