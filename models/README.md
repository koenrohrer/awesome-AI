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

- **[Claude (Anthropic)](claude.md)** `[provider-doc]` — Opus/Sonnet/Haiku, extended thinking, 90%-off prompt caching, strict tool use.
- **[GPT (OpenAI)](gpt.md)** `[provider-doc]` — Broad multimodality, hosted tools, o-series reasoning, Batch API discount.
- **[Gemini (Google)](gemini.md)** `[provider-doc]` — 1M-token context, native video/audio, explicit context caching, thinking budgets.

More providers (Kimi, Qwen, DeepSeek, Grok, Llama, Mistral) land in v0.3.

## Editorial rules

- Every strength/weakness carries a citation. "It feels smarter" doesn't ship.
- Pricing and context window are updated on model release, not on schedule. If you spot a stale number, open an issue.
- No model-vs-model grand rankings. If a benchmark ranks them, link it with its date and methodology.
