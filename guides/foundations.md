# Read the foundations first

## The Short Version

Read the foundations in layers: architecture, scaling, instruction tuning, preference optimization, retrieval, serving mechanics, and safety.

The goal is not to read every paper before building. It is to understand the assumptions behind modern LLM behavior before relying on tactics, benchmarks, or provider claims.

Start with the Transformer and scaling laws. Then read the alignment papers that explain why assistants behave differently from base language models.

After that, use the architecture explainers to understand practical system choices such as retrieval, tokenization, KV cache, fine-tuning, and mixture-of-experts. Add safety early if your system receives untrusted content or can take actions.

## Use This Guide When

Use this when you want a first reading order for the repo's learning section, or when a design discussion depends on terms like transformer, scaling, RLHF, RAG, KV cache, LoRA, MoE, tokenization, jailbreak, or prompt injection.

## Fast Path

- **[Attention Is All You Need](../learning/papers/attention-is-all-you-need.md)** `[paper]` — learn the Transformer baseline before evaluating architecture claims.
- **[Scaling laws](../learning/papers/scaling-laws.md)** `[paper]` — understand why model size, data, and compute tradeoffs matter.
- **[InstructGPT / RLHF](../learning/papers/instructgpt.md)** `[paper]` — read the assistant-training recipe that made instruction-following central.
- **[Direct Preference Optimization](../learning/papers/dpo.md)** `[paper]` — see the simpler preference-optimization path that removes the RL loop.
- **[Retrieval-augmented generation](../learning/architecture/rag.md)** `[paper]` — understand when knowledge belongs in retrieved context instead of model weights.
- **[Tokenization: BPE and SentencePiece](../learning/architecture/tokenization.md)** `[paper]` — learn why text length, cost, and formatting failures often start at the tokenizer.
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]` — read before building systems that ingest webpages, emails, documents, or database rows.

## Decision Points

- If you are learning model internals, read Transformer, scaling laws, tokenization, KV cache, and MoE before provider model pages.
- If you are learning assistant behavior, read InstructGPT, DPO, and Constitutional AI before debating alignment terminology.
- If you are building with private or changing documents, read RAG and indirect prompt injection together.
- If you are adapting a model, read fine-tuning and LoRA before assuming retrieval or prompting is the right lever.
- If you are evaluating serving or latency claims, read KV cache and multi-token prediction before comparing benchmarks.

## Field Notes

Foundational papers are not operating manuals. They define the concepts and tradeoffs that later tools inherit. A provider model page may change quickly; these entries are more stable because they explain mechanisms rather than current product surfaces.

Safety is part of the foundation, not a later polish pass. When a model receives untrusted content, summarizes external material, or calls tools, prompt injection and jailbreak failure modes become design inputs.

## What To Avoid

- Do not use one paper as a universal proof that a product choice is correct.
- Do not treat RAG, fine-tuning, and longer context as interchangeable fixes.
- Do not read provider model catalogs before you understand the concepts used to describe them.
- Do not defer safety reading until after an agent or retrieval workflow is already designed.
- Do not turn the learning section into a general bibliography; the entries here are curated starting points.

## Evidence Library

- **[Attention Is All You Need](../learning/papers/attention-is-all-you-need.md)** `[paper]`
- **[Scaling laws](../learning/papers/scaling-laws.md)** `[paper]`
- **[InstructGPT / RLHF](../learning/papers/instructgpt.md)** `[paper]`
- **[Direct Preference Optimization](../learning/papers/dpo.md)** `[paper]`
- **[Constitutional AI](../learning/papers/constitutional-ai.md)** `[paper]`
- **[Retrieval-augmented generation](../learning/architecture/rag.md)** `[paper]`
- **[KV cache and PagedAttention](../learning/architecture/kv-cache.md)** `[paper]`
- **[Multi-token prediction](../learning/architecture/multi-token-prediction.md)** `[paper]`
- **[Mixture-of-experts](../learning/architecture/mixture-of-experts.md)** `[paper]`
- **[Fine-tuning and LoRA](../learning/architecture/fine-tuning-lora.md)** `[paper]`
- **[Tokenization: BPE and SentencePiece](../learning/architecture/tokenization.md)** `[paper]`
- **[TurboQuant](../learning/architecture/turboquant.md)** `[paper]`
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]`
- **[GCG: Universal Adversarial Attacks](../learning/safety/gcg-attack.md)** `[paper]`
- **[Jailbroken: How Does LLM Safety Training Fail?](../learning/safety/jailbreak-failure-modes.md)** `[paper]`
