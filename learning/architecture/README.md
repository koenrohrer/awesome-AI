# Architecture explainers

Source-backed explainers for foundational AI/LLM architecture topics: transformers, retrieval, KV cache, disaggregated serving, mixture-of-experts, fine-tuning, tokenization, quantization, and related systems concepts.

## Entries

- **[Retrieval-augmented generation (RAG)](rag.md)** `[paper]` — Retrieve external evidence, then condition generation on it; useful when parametric memory is stale or incomplete.
- **[KV cache and PagedAttention](kv-cache.md)** `[paper]` — Reuse attention keys and values during decoding; the main memory bottleneck for long-context serving.
- **[Context Folding](context-folding.md)** `[paper]` — Branch into subtasks, then fold completed trajectories out of the active context.
- **[Agent harnesses](agent-harnesses.md)** `[provider-doc]` — Runtime boundaries for tools, permissions, state, isolation, evaluation, and recovery.
- **[Disaggregated LLM serving](disaggregated-llm-serving.md)** `[paper]` — Split prefill and decode workers, then transfer KV cache across serving resources.
- **[Multi-head latent attention (MLA)](multi-head-latent-attention.md)** `[paper]` — Compress cached keys and values into latent vectors to reduce long-context decoding memory.
- **[Multi-token prediction (MTP)](multi-token-prediction.md)** `[paper]` — Draft and verify several future tokens per decoding step to reduce autoregressive latency.
- **[Kimi Linear / Kimi Delta Attention (KDA)](kimi-linear.md)** `[paper]` — Mix KDA and MLA layers to reduce long-context cache and decode costs.
- **[Native Sparse Attention / DeepSeek Sparse Attention](native-sparse-attention.md)** `[paper]` — Train sparse long-context attention paths around GPU-friendly block access.
- **[Mixture-of-experts (MoE)](mixture-of-experts.md)** `[paper]` — Route tokens through a sparse subset of experts to add capacity without activating every parameter.
- **[Fine-tuning and LoRA](fine-tuning-lora.md)** `[paper]` — Adapt a pretrained model to a task or domain; LoRA makes that adaptation parameter-efficient.
- **[Tokenization: BPE and SentencePiece](tokenization.md)** `[paper]` — Split text into subword units; tokenization defines the model's vocabulary and cost surface.
- **[TurboQuant](turboquant.md)** `[paper]` — Compress high-dimensional vectors for KV cache and vector search with near-optimal distortion claims.

## Inclusion bar

A link belongs here only if it is considered a definitive or near-definitive treatment by the community, or if a maintainer ran its exercises end-to-end and found them sound. No self-referential "here's my blog post about transformers."

## Status

Seeded with paper-backed primers in v0.5. Diffusion, RLHF architecture, DPO architecture, context extension, and quantized weight formats are still open.
