# xAI `[provider-doc]`

*Last reviewed: 2026-08-06. The official documentation now uses the SpaceXAI name while retaining `x.ai` domains and API endpoints. This catalog is date-stamped, not a ranking; verify against the live [models page](https://docs.x.ai/developers/models) before making cost or migration decisions.*

## Product surfaces

- **[Grok Build](grok-build.md)** — coding agent with interactive, headless, and Agent Client Protocol interfaces.

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Grok 4.5 | Current general and coding tier | 500K context, text+image input, configurable reasoning, server tools |

The current models page directs code and chat workloads to Grok 4.5. Older pages remain below as historical and migration coverage; verify retirement status before using their IDs.

## Model pages

- [Grok 4.5](models/grok-4-5.md)

### Available previous generation

- [Grok 4.20](models/grok-4-20.md)

### Retired aliases

- [Grok 4 Fast (reasoning)](models/grok-4-fast-reasoning.md)
- [Grok 4 Fast (non-reasoning)](models/grok-4-fast-non-reasoning.md)
- [Grok Code Fast 1](models/grok-code-fast-1.md)

## Current and historical model docs

- [xAI docs overview](https://docs.x.ai/docs)
- [Models and pricing](https://docs.x.ai/developers/models)
- [Grok 4.5 model page](https://docs.x.ai/developers/models/grok-4.5)
- [Grok 4 model page](https://docs.x.ai/developers/models/grok-4)
- [Grok 4 Fast reasoning model page](https://docs.x.ai/developers/models/grok-4-fast-reasoning)
- [Grok 3 mini model page](https://docs.x.ai/developers/models/grok-3-mini)

xAI does not currently publish a public “system card” hub in the Anthropic/OpenAI style. The model pages and news posts are the practical primary docs.

## Strengths (cited)

- **OpenAI-compatible API surface.** xAI exposes a familiar API shape, lowering integration friction for teams already wired for OpenAI-style clients. [Docs overview](https://docs.x.ai/docs).
- **Large current context window.** Grok 4.5 publishes a 500K-token context window. [Models page](https://docs.x.ai/developers/models).
- **Built-in live/search positioning.** xAI continues to push web/X search and code execution as first-party tools. [Tools overview](https://docs.x.ai/docs).
- **Separate coding-agent surface.** Grok Build wraps the model with repository tools, permissions, extensions, and subagents. [Grok Build docs](https://docs.x.ai/build/overview).

## Weaknesses (cited)

- **Live information is opt-in.** The base model has a February 1, 2026 cutoff; current information requires web or X search. [Models page](https://docs.x.ai/developers/models).
- **Aliases can move.** `-latest` aliases can change; consistency-sensitive integrations should pin dated versions when available. [Models page](https://docs.x.ai/developers/models).
- **Retired slugs can still resolve.** Several Grok 4 Fast and code IDs redirect to replacements with different behavior and pricing. [Retirement guide](https://docs.x.ai/developers/migration/may-15-retirement).

## Fits

- Teams that want OpenAI-compatible integration with another frontier vendor
- Workflows that benefit from first-party live/web/X search positioning
- Large-context agent tasks where 500K context is materially useful
- Coding workflows that need a first-party terminal agent as well as a model API

## Provider-specific quirks

- **Reasoning is configurable.** Grok 4.5 exposes low, medium, and high reasoning effort.
- **Live data requires tools.** Web and X search must be enabled; the base model does not automatically receive current events.
- **Model docs are more useful than blog posts.** For xAI, the live docs page carries more operational value than announcements.

## Official docs and resources

- [xAI docs overview](https://docs.x.ai/docs)
- [Models and pricing](https://docs.x.ai/developers/models)
- [xAI news / blog](https://x.ai/news)

## Status

`[provider-doc]`. This page reflects Grok 4.5 as the current documented API model and Grok Build as its distinct coding-agent surface.
