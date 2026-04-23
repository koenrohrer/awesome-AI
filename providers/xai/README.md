# xAI `[provider-doc]`

*Last reviewed: 2026-04-23. xAI's API catalog is moving quickly; verify against the live [docs overview](https://docs.x.ai/docs) and [models and pricing page](https://docs.x.ai/developers/models) before making cost or migration decisions.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Grok 4.20 | Current flagship | 2M context, reasoning, structured outputs, tool calling |
| Grok 4 Fast (reasoning) | Fast/cheap reasoning tier | 2M context, lower cost than flagship |
| Grok 4 Fast (non-reasoning) | Lower-latency general tier | 2M context without reasoning path |
| Grok Code Fast 1 | Coding tier | 256K context, code-editor and agent fit |
| Grok 3 / Grok 3 mini | Older API line | Legacy models still listed for migration contexts |

The xAI docs now treat Grok 4.20 as the newest flagship and keep Grok 3-era models around mainly as migration baselines.

## Model pages

- [Grok 4.20](models/grok-4-20.md)
- [Grok 4 Fast (reasoning)](models/grok-4-fast-reasoning.md)
- [Grok 4 Fast (non-reasoning)](models/grok-4-fast-non-reasoning.md)
- [Grok Code Fast 1](models/grok-code-fast-1.md)

## Model docs

- [xAI docs overview](https://docs.x.ai/docs)
- [Models and pricing](https://docs.x.ai/developers/models)
- [Grok 4 model page](https://docs.x.ai/developers/models/grok-4)
- [Grok 4 Fast reasoning model page](https://docs.x.ai/developers/models/grok-4-fast-reasoning)
- [Grok 3 mini model page](https://docs.x.ai/developers/models/grok-3-mini)

xAI does not currently publish a public “system card” hub in the Anthropic/OpenAI style. The model pages and news posts are the practical primary docs.

## Strengths (cited)

- **OpenAI-compatible API surface.** xAI exposes a familiar API shape, lowering integration friction for teams already wired for OpenAI-style clients. [Docs overview](https://docs.x.ai/docs).
- **Very large context windows on current top tiers.** Grok 4.20 and Grok 4 Fast publish 2M context in the current docs. [Docs overview](https://docs.x.ai/docs), [models page](https://docs.x.ai/developers/models).
- **Built-in live/search positioning.** xAI continues to push web/X search and code execution as first-party tools. [Tools overview](https://docs.x.ai/docs).
- **Clear coding-specific tier.** `grok-code-fast-1` exists as a documented coding model rather than expecting one general model to do everything.

## Weaknesses (cited)

- **Documentation depth still lags the top three incumbents.** The docs are better than before, but the ecosystem remains thinner than OpenAI/Anthropic/Google for advanced agent-framework support.
- **Consumer/API surface mismatch remains real.** Capabilities discussed for grok.com or X do not always map cleanly to API features.
- **Versioning churn.** xAI is iterating rapidly from Grok 3 to Grok 4 to Grok 4.20 and Grok 4 Fast; integration code should pin explicit model IDs.

## Best-fit tasks

- Teams that want OpenAI-compatible integration with another frontier vendor
- Workflows that benefit from first-party live/web/X search positioning
- Large-context agent tasks where 2M context is materially useful
- Coding agents that prefer a dedicated code model rather than a generalist

## Provider-specific quirks

- **Reasoning vs non-reasoning split matters.** Grok 4 Fast has separate reasoning and non-reasoning variants.
- **Grok 4 differs from Grok 3 on parameters.** xAI explicitly notes migration differences on the models page.
- **Model docs are more useful than blog posts.** For xAI, the live docs page carries more operational value than announcements.

## Official docs and resources

- [xAI docs overview](https://docs.x.ai/docs)
- [Models and pricing](https://docs.x.ai/developers/models)
- [xAI news / blog](https://x.ai/news)

## Status

`[provider-doc]`. This page now names the concrete Grok 4.20 / Grok 4 Fast / Grok Code Fast lineup reflected in xAI's public docs.
