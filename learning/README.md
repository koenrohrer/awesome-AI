# Learning

Foundations, not tips. If you want to understand *why* the techniques in `prompting/` and `agents/` work, this is where to start.

## Sections

- **[Papers](papers/)** — landmark papers with a one-paragraph TL;DR and a link. Each TL;DR is written to be read before the paper, not instead of it.
- **[Courses](courses/)** — courses a maintainer completed and endorses. No "this looks good" — someone finished it.
- **[Architecture explainers](architecture/)** — RAG, KV cache, disaggregated serving, MTP/speculative decoding, MoE, fine-tuning/LoRA, tokenization, and quantization, with source-backed primers.
- **[Safety](safety/)** — red-teaming, jailbreak resistance, prompt injection. Tilts toward defensive content.

## Inclusion bar

Same as the rest of the repo:

- **Papers** — `[paper]`. Full citation and direct link to the paper (not to a blog post *about* the paper).
- **Courses** — a maintainer completed it. Name the provider, date of completion, and one honest line on whether it was worth the time.
- **Explainers** — direct link only if it's considered a definitive treatment by the community. No self-referential "here's my blog post about transformers."
- **Safety** — `[paper]` or `[provider-doc]` for claims about attack/defense efficacy.

## Architecture — systems concepts

- **[Retrieval-augmented generation (RAG)](architecture/rag.md)** `[paper]` — Retrieve external evidence, then condition generation on it.
- **[KV cache and PagedAttention](architecture/kv-cache.md)** `[paper]` — Reuse attention keys and values during decoding; key serving bottleneck.
- **[Disaggregated LLM serving](architecture/disaggregated-llm-serving.md)** `[paper]` — Split prefill and decode workers, then transfer KV cache across serving resources.
- **[Multi-head latent attention (MLA)](architecture/multi-head-latent-attention.md)** `[paper]` — Compress cached keys and values into latent vectors to reduce long-context decoding memory.
- **[Multi-token prediction (MTP)](architecture/multi-token-prediction.md)** `[paper]` — Draft and verify several future tokens per decoding step to reduce autoregressive latency.
- **[Kimi Linear / Kimi Delta Attention (KDA)](architecture/kimi-linear.md)** `[paper]` — Mix KDA and MLA layers to reduce long-context cache and decode costs.
- **[Native Sparse Attention / DeepSeek Sparse Attention](architecture/native-sparse-attention.md)** `[paper]` — Train sparse long-context attention paths around GPU-friendly block access.
- **[Mixture-of-experts (MoE)](architecture/mixture-of-experts.md)** `[paper]` — Add sparse capacity by routing tokens through selected experts.
- **[Fine-tuning and LoRA](architecture/fine-tuning-lora.md)** `[paper]` — Adapt model behavior with full or parameter-efficient training.
- **[Tokenization: BPE and SentencePiece](architecture/tokenization.md)** `[paper]` — Map raw text into subword token IDs.
- **[TurboQuant](architecture/turboquant.md)** `[paper]` — Compress high-dimensional vectors for KV cache and vector search.

## Status

Partially seeded in v0.5. `papers/`, `architecture/`, and `safety/` are live; `courses/` is still being seeded.
