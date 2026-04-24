# Architecture explainers

The best explainers for foundational AI/LLM architectures -- transformers, retrieval, KV cache, mixture-of-experts, fine-tuning, tokenization, quantization, and similar.

## Entries

- **[Retrieval-augmented generation (RAG)](rag.md)** `[paper]` — Retrieve external evidence, then condition generation on it; useful when parametric memory is stale or incomplete.
- **[KV cache and PagedAttention](kv-cache.md)** `[paper]` — Reuse attention keys and values during decoding; the main memory bottleneck for long-context serving.
- **[Mixture-of-experts (MoE)](mixture-of-experts.md)** `[paper]` — Route tokens through a sparse subset of experts to add capacity without activating every parameter.
- **[Fine-tuning and LoRA](fine-tuning-lora.md)** `[paper]` — Adapt a pretrained model to a task or domain; LoRA makes that adaptation parameter-efficient.
- **[Tokenization: BPE and SentencePiece](tokenization.md)** `[paper]` — Split text into subword units; tokenization defines the model's vocabulary and cost surface.
- **[TurboQuant](turboquant.md)** `[paper]` — Compress high-dimensional vectors for KV cache and vector search with near-optimal distortion claims.

## Inclusion bar

A link belongs here only if it is considered a definitive or near-definitive treatment by the community, or if a maintainer ran its exercises end-to-end and found them sound. No self-referential "here's my blog post about transformers."

## Status

Seeded with paper-backed primers in v0.5. Diffusion, RLHF architecture, DPO architecture, context extension, speculative decoding, and quantized weight formats are still open.
