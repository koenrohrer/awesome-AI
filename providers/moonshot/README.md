# Moonshot AI `[provider-doc]`

*Last reviewed: 2026-04-22. Moonshot's primary model family is Kimi. Verify against [Moonshot AI's platform](https://platform.moonshot.ai/) before building a cost model.*

## Current model lines

| Model | Context | Notable feature |
|---|---|---|
| Kimi K2 series | Long (100K+) | Mixture-of-experts flagship |
| Kimi chat models | Long | Consumer-facing chat (kimi.com) |

Exact model IDs and pricing are listed on the [Moonshot platform docs](https://platform.moonshot.ai/docs). Moonshot has historically published open weights for selected Kimi releases on [HuggingFace](https://huggingface.co/moonshotai).

## Strengths (cited)

- **Long-context claims.** Kimi was one of the early Chinese labs to push to very long context windows; current documentation reflects ongoing investment in long-context inference. Verify the current model's context limit on the docs page before relying on it.
- **Open-weight availability.** Select Kimi releases appear on HuggingFace under [moonshotai](https://huggingface.co/moonshotai), making local evaluation and fine-tuning possible — unusual among frontier-scale Chinese models.
- **Competitive agentic benchmarks.** Model announcements include benchmark tables on coding, math, and agent evals. Always cross-check with an independent benchmark (e.g., LiveCodeBench, SWE-Bench) rather than relying solely on provider-reported numbers.

## Weaknesses (cited)

- **Documentation ecosystem is thinner** than Anthropic/OpenAI/Google — primary docs are bilingual with some English gaps. Expect to cross-reference the Chinese docs and community writeups on HuggingFace.
- **Tooling coverage in Western agent frameworks** (LangChain, LlamaIndex, etc.) lags — OpenAI-compatible endpoints are the most common integration path.

## Best-fit tasks

- Cost-sensitive long-context workflows (where published pricing beats the Western-frontier trio)
- Tasks where open weights matter (self-hosting, fine-tuning, reproducibility)
- Cross-lingual tasks involving Chinese — Moonshot's training is Chinese-first

## Provider-specific quirks

- **OpenAI-compatible API.** Platform exposes a `chat/completions` endpoint that mirrors OpenAI's format — existing OpenAI client code generally works with a base-URL change.
- **Open-weight distribution** uses HuggingFace conventions; inference tooling is the same as any Llama-family model of similar architecture (vLLM, llama.cpp for quantized variants).

## Official docs

- [Moonshot AI platform](https://platform.moonshot.ai/)
- [Platform docs](https://platform.moonshot.ai/docs)
- [Open-weight releases on HuggingFace](https://huggingface.co/moonshotai)

## Status

`[provider-doc]`. Model IDs, context windows, and pricing rotate quickly for this provider — treat as a pointer.
