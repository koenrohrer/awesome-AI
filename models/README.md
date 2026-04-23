# Models

Per-provider deep dives. One file per provider, structured identically so you can compare apples to apples.

## File structure (each `<provider>.md`)

```
# <Provider>

## Current models (as of YYYY-MM-DD)
| Model | Context | Input $/1M | Output $/1M | Notes |

## Strengths (cited)
- Bullet + citation (paper or benchmark)

## Weaknesses (cited)
- Bullet + citation

## Best-fit tasks
- Short list based on the above.

## Provider-specific quirks
- Prompting conventions (e.g., Claude and XML tags, cited to provider docs).
- API quirks worth knowing.

## Official docs
- Direct links.
```

## Providers we plan to cover

**Closed frontier:** Claude, GPT, Gemini, Grok
**Open weights:** Llama, Mistral, Qwen, DeepSeek, Kimi, Phi
**Specialist:** Mixtral, Command R, Yi, Hermes fine-tunes

## Entries

### Closed frontier

- **[Claude (Anthropic)](claude.md)** `[provider-doc]` — Opus/Sonnet/Haiku, extended thinking, 90%-off prompt caching, strict tool use.
- **[GPT (OpenAI)](gpt.md)** `[provider-doc]` — Broad multimodality, hosted tools, o-series reasoning, Batch API discount.
- **[Gemini (Google)](gemini.md)** `[provider-doc]` — 1M-token context, native video/audio, explicit context caching, thinking budgets.
- **[Grok (xAI)](grok.md)** `[provider-doc]` — OpenAI-compatible endpoint, integrated live X/web data, select older weights occasionally released.

### Open-weight and Chinese labs

- **[Gemma (Google DeepMind)](gemma.md)** `[provider-doc]` — Gemma 4 open models in `E2B`, `E4B`, `26B A4B`, and `31B` sizes for edge-to-workstation deployment.
- **[Kimi (Moonshot AI)](kimi.md)** `[provider-doc]` — MoE flagship with long-context focus; selected releases published as open weights.
- **[Qwen (Alibaba)](qwen.md)** `[provider-doc]` — The most consistently open-weight frontier-adjacent family; specialist variants (Coder, VL, Math, Audio).
- **[DeepSeek](deepseek.md)** `[provider-doc]` — MoE + open-weight reasoning (R1); aggressive hosted-API pricing.
- **[Llama (Meta)](llama.md)** `[provider-doc]` — Reference open-weight family; first-class support in every major open-source inference stack.
- **[Mistral](mistral.md)** `[provider-doc]` — Dual-track proprietary + Apache-2.0 open-weight MoE; EU-based.

More providers (Phi, Command R, Yi) land in a later wave.

## Editorial rules

- Every strength/weakness carries a citation. "It feels smarter" doesn't ship.
- Pricing and context window are updated on model release, not on schedule. If you spot a stale number, open an issue.
- No model-vs-model grand rankings. If a benchmark ranks them, link it with its date and methodology.
