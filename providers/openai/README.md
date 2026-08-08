# OpenAI `[provider-doc]`

*Last reviewed: 2026-08-06. GPT-5.6 is generally available across the OpenAI API, ChatGPT, and Codex. Verify exact access and pricing against the live [models page](https://developers.openai.com/api/docs/models) before deployment.*

## Product surfaces

- **[Codex](codex.md)** — OpenAI's coding-agent surface for parallel software-engineering work and automations.
- **[ChatGPT Desktop](chatgpt-desktop.md)** — desktop app surface for local workflows, screenshots, files, and IDE-connected chat.
- **[Image generation](image-generation.md)** — GPT Image and related image-generation APIs/tools.

## Model pages

- [GPT-5.6 Sol](models/gpt-5-6-sol.md)
- [GPT-5.6 Terra](models/gpt-5-6-terra.md)
- [GPT-5.6 Luna](models/gpt-5-6-luna.md)
- [GPT-5.5](models/gpt-5-5.md)
- [GPT-5.5 Pro](models/gpt-5-5-pro.md)
- [GPT-5.4](models/gpt-5-4.md)
- [GPT-5.4 Pro](models/gpt-5-4-pro.md)
- [GPT-5.4 mini](models/gpt-5-4-mini.md)
- [GPT-5.4 nano](models/gpt-5-4-nano.md)
- [GPT-5.3 Instant](models/gpt-5-3-instant.md)
- [GPT-5.3-Codex](models/gpt-5-3-codex.md)
- [GPT-5-Codex](models/gpt-5-codex.md)
- [codex-mini-latest](models/codex-mini-latest.md)

## Current model lines

| Line | API ID | Role | Input / output per 1M tokens |
|---|---|---|---|
| GPT-5.6 Sol | `gpt-5.6-sol` (`gpt-5.6` alias) | Flagship tier for complex reasoning and coding | $5 / $30 |
| GPT-5.6 Terra | `gpt-5.6-terra` | Balanced capability-and-cost tier | $2 / $12 |
| GPT-5.6 Luna | `gpt-5.6-luna` | Cost-sensitive, high-volume tier | $0.20 / $1.20 |
| GPT-5.5 | `gpt-5.5` | Previous frontier tier; active for pinned workloads | $5 / $30 |
| GPT-5.5 Pro | `gpt-5.5-pro` | Previous higher-compute tier; active for pinned workloads | $30 / $180 |
| GPT-5.4 family | `gpt-5.4*` | Older main, Pro, mini, and nano tiers | See each model page |
| Codex models | `gpt-5.3-codex`, `gpt-5-codex`, `codex-mini-latest` | Coding-specialized models | See each model page |

The three GPT-5.6 API models support text and image input, text output, a 1.05M-token context window, 128K-token output, and reasoning efforts from `none` through `max`. Their per-model pages list the same broad Responses API tool set. OpenAI's current model pages are authoritative when launch-post prices or capabilities differ.

## System cards

- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)
- [GPT-5.4 Thinking system card](https://openai.com/index/gpt-5-4-thinking-system-card)
- [GPT-5.3 Instant system card](https://openai.com/index/gpt-5-3-instant-system-card/)
- [GPT-5.3-Codex system card](https://openai.com/index/gpt-5-3-codex-system-card/)
- [Addendum to GPT-5 system card: GPT-5-Codex](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)

OpenAI publishes family-level system cards rather than a separate card for every API alias. Read the current family card with the per-model catalog page.

## Strengths (cited)

- **Broad hosted tool surface.** GPT-5.6 supports web search, file search, code interpreter, hosted shell, apply patch, computer use, MCP, and related Responses API tools. [GPT-5.6 Sol model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol).
- **Three current cost tiers.** Sol, Terra, and Luna share the core GPT-5.6 context, modality, and tool surface while exposing different prices and rate limits. [Models page](https://developers.openai.com/api/docs/models).
- **Product/API availability.** OpenAI launched GPT-5.6 across ChatGPT, Codex, and the API on July 9, 2026. [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/).

## Weaknesses (cited)

- **Catalog breadth.** OpenAI maintains overlapping general, Pro, Codex, image, realtime, and specialist lines. Confirm the exact alias on the [models page](https://developers.openai.com/api/docs/models).
- **Feature support varies by alias.** GPT-5.5 Pro, for example, omits streaming and several tools supported by base GPT-5.5. Compare their [model pages](https://developers.openai.com/api/docs/models/compare).
- **Long-context pricing changes above a threshold.** GPT-5.6 requests with more than 272K input tokens use higher input and output rates. Check the per-model pricing notes before estimating cost.

## Fits

- Multimodal agent workflows that need hosted tools
- Coding agents that combine planning, computer use, and repository edits
- Knowledge-work automation across documents, spreadsheets, and presentations
- Mixed-model systems that route work among Sol, Terra, and Luna by task value

## Provider-specific quirks

- **Responses API is the primary surface.** OpenAI's [GPT-5.6 guidance](https://developers.openai.com/api/docs/guides/latest-model) directs reasoning, tool-calling, and multi-turn workflows there.
- **`gpt-5.6` routes to Sol.** Use the suffixed Terra and Luna IDs when you want those tiers.
- **GPT-5.6 cache writes are billed.** Cache writes cost 1.25 times uncached input; cache reads receive the discount listed on each [model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol).
- **Codex models remain separate.** The [model catalog](https://developers.openai.com/api/docs/models) keeps coding-specialized aliases separate from the GPT-5.6 family.

## Official docs

- [Models](https://developers.openai.com/api/docs/models)
- [Model comparison](https://developers.openai.com/api/docs/models/compare)
- [GPT-5.6 model guidance](https://developers.openai.com/api/docs/guides/latest-model)
- [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/)
- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.5 model page](https://developers.openai.com/api/docs/models/gpt-5.5)
- [GPT-5.5 Pro model page](https://developers.openai.com/api/docs/models/gpt-5.5-pro)

## Status

`[provider-doc]`. GPT-5.6 is generally available; GPT-5.5 and older lines remain available for evaluated or pinned workloads.
