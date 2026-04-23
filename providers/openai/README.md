# OpenAI `[provider-doc]`

*Last reviewed: 2026-04-23. OpenAI's catalog is moving quickly; GPT-5.5 launched today for ChatGPT and Codex with API access announced as coming soon. Verify exact availability against the live [models page](https://developers.openai.com/api/docs/models), [GPT-5.5 launch post](https://openai.com/index/introducing-gpt-5-5/), and current system-card pages before building around a specific snapshot.*

## Product surfaces

- **[Codex](codex.md)** — OpenAI's coding-agent surface for parallel software-engineering work and automations.
- **[ChatGPT Desktop](chatgpt-desktop.md)** — desktop app surface for local workflows, screenshots, files, and IDE-connected chat.
- **[Image generation](image-generation.md)** — GPT Image and related image-generation APIs/tools.

## Model pages

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

| Line | Role | Notable feature |
|---|---|---|
| GPT-5.5 | Current ChatGPT/Codex flagship; API soon | Stronger agentic coding, computer use, research, and document/spreadsheet work |
| GPT-5.5 Pro | Higher-compute ChatGPT tier; API soon | Harder-question / higher-accuracy path |
| GPT-5.4 | Current API flagship | 1.05M context, native computer use, default API starting point |
| GPT-5.4 Pro | Max-compute API flagship | Slower, more expensive, deeper reasoning path |
| GPT-5.4 mini / nano | Fast and cheap GPT-5.4-class models | Strong fit for subagents, coding helpers, high-volume tasks |
| GPT-5.3 Instant | Fast GPT-5-series conversational model | Better web-search flow and lower latency than heavier models |
| GPT-5.3-Codex / GPT-5.2-Codex / GPT-5-Codex | Agentic coding | Codex-tuned coding models with long-horizon tool use |
| `codex-mini-latest` | Budget Codex helper | Fast Codex CLI / IDE workload tier |

The live API docs still recommend `gpt-5.4` as the default API starting point. OpenAI's April 23, 2026 GPT-5.5 launch post says `gpt-5.5` and `gpt-5.5-pro` are coming to the API soon; until the live models page lists them, treat them as product-available rather than generally callable API models.

## System cards

- [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)
- [GPT-5.4 Thinking system card](https://openai.com/index/gpt-5-4-thinking-system-card)
- [GPT-5.3 Instant system card](https://openai.com/index/gpt-5-3-instant-system-card/)
- [GPT-5.3-Codex system card](https://openai.com/index/gpt-5-3-codex-system-card/)
- [Addendum to GPT-5 system card: GPT-5-Codex](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)
- [GPT-5 system card](https://openai.com/blog/gpt-5-system-card/)

OpenAI does not currently expose a separate public system-card page for every API alias on the models page. For example, `gpt-5.4-pro`, `gpt-5.4-mini`, and `gpt-5.4-nano` are documented on the models page and launch posts, but the main public safety document is still anchored on GPT-5.4 Thinking.

## Strengths (cited)

- **Broad hosted tools surface.** `web_search`, `file_search`, `computer_use`, `hosted shell`, `apply_patch`, and related tools are exposed directly in the Responses API. [Models page](https://developers.openai.com/api/docs/models), [tools docs](https://platform.openai.com/docs/guides/tools).
- **Strong agentic coding depth.** GPT-5.5 is now OpenAI's newest product model for agentic coding in ChatGPT and Codex, while GPT-5.4 remains the live default API starting point. See [Introducing GPT-5.5](https://openai.com/index/introducing-gpt-5-5/), [Introducing GPT-5.4](https://openai.com/index/introducing-gpt-5-4/), and the [GPT-5.3-Codex model page](https://developers.openai.com/api/docs/models/gpt-5.3-codex).
- **Wide product/API convergence.** The same core line now spans ChatGPT, the API, and Codex, reducing “web model vs API model” drift for many workflows. [Introducing GPT-5.4](https://openai.com/index/introducing-gpt-5-4/).
- **Automatic prompt caching and flexible scaling paths.** OpenAI supports prompt caching, batch, flex processing, and background mode in the main API stack. See the [API docs](https://developers.openai.com/api/docs/models) and [pricing](https://openai.com/api/pricing/).

## Weaknesses (cited)

- **Catalog sprawl.** OpenAI now has overlapping mainline GPT-5, GPT-5.4 variants, Codex variants, and specialized models; model choice is less obvious than “just use the flagship.” The [models page](https://developers.openai.com/api/docs/models) is authoritative.
- **Feature support varies by alias.** `gpt-5.4-pro` supports a narrower subset of structured-output/tooling features than `gpt-5.4`, and Codex-optimized models differ again. Always check the per-model page.
- **Safety docs do not map 1:1 to every alias.** You often need to read a flagship system card plus addenda and launch posts to understand a family.

## Best-fit tasks

- Multimodal agent workflows that need hosted tools rather than self-hosted infrastructure
- Coding agents that mix planning, computer use, and repo edits
- Knowledge-work automation across documents, spreadsheets, and presentations
- Small/large mixed-model systems where GPT-5.4 coordinates and mini/nano handle support tasks

## Provider-specific quirks

- **Responses API is the primary surface.** New tool support lands there first. Older Chat Completions integrations still work for many models, but new builds should bias toward Responses.
- **Model-specific tool support matters.** The models page now lists supported tools per model; do not assume parity across aliases.
- **Codex models remain separate.** Even though GPT-5.4 absorbed a lot of Codex capability, dedicated Codex models still exist and are easier to justify for coding-only workloads.

## Official docs

- [Models](https://developers.openai.com/api/docs/models)
- [GPT-5.5 launch post](https://openai.com/index/introducing-gpt-5-5/)
- [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)
- [GPT-5.4 launch post](https://openai.com/index/introducing-gpt-5-4/)
- [GPT-5.4 mini and nano launch post](https://openai.com/index/introducing-gpt-5-4-mini-and-nano/)
- [GPT-5.4 model page](https://developers.openai.com/api/docs/models/gpt-5.4)
- [GPT-5.4 Pro model page](https://developers.openai.com/api/docs/models/gpt-5.4-pro)
- [GPT-5.3-Codex model page](https://developers.openai.com/api/docs/models/gpt-5.3-codex)
- [GPT-5-Codex model page](https://developers.openai.com/api/docs/models/gpt-5-codex)
- [codex-mini-latest model page](https://developers.openai.com/api/docs/models/codex-mini-latest)
- [Pricing](https://openai.com/api/pricing/)

## Status

`[provider-doc]`. OpenAI now has public GPT-5.5 system-card coverage, but GPT-5.5 and GPT-5.5 Pro should be treated as product-available/API-soon until they appear on the live API models page.
