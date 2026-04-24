# Learning

Foundations, not tips. If you want to understand *why* the techniques in `prompting/` and `agents/` work, this is where to start.

## Sections

- **[Papers](papers/)** — landmark papers with a one-paragraph TL;DR and a link. Each TL;DR is written to be read before the paper, not instead of it.
- **[Courses](courses/)** — courses a maintainer completed and endorses. No "this looks good" — someone finished it.
- **[Architecture explainers](architecture/)** — RAG, KV cache, MoE, fine-tuning/LoRA, tokenization, quantization. Links to the best source-backed primer for each, not yet-another-blog-post.
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
- **[Mixture-of-experts (MoE)](architecture/mixture-of-experts.md)** `[paper]` — Add sparse capacity by routing tokens through selected experts.
- **[Fine-tuning and LoRA](architecture/fine-tuning-lora.md)** `[paper]` — Adapt model behavior with full or parameter-efficient training.
- **[Tokenization: BPE and SentencePiece](architecture/tokenization.md)** `[paper]` — Map raw text into subword token IDs.
- **[TurboQuant](architecture/turboquant.md)** `[paper]` — Compress high-dimensional vectors for KV cache and vector search.

## Status

Partially seeded in v0.5. `papers/`, `architecture/`, and `safety/` are live; `courses/` is still being seeded.
