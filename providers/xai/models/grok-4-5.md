# Grok 4.5 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Model ID | `grok-4.5` |
| Aliases | `grok-4.5-latest`, `grok-build-latest` |
| Lifecycle | Available through the API and Grok Build |
| Input / output | Text and image / text |
| Context window | 500,000 tokens |
| Standard price | $2 input / $6 output per 1M tokens; $0.30 cached input |
| Capabilities | Configurable reasoning, function calling, structured outputs |
| Server tools | Web search, X search, and code execution |

## What it is

Grok 4.5 is SpaceXAI's current general model for coding, agentic workflows, and knowledge work. It is available through the Responses and Chat Completions APIs and is the default model in Grok Build.

The model has a February 1, 2026 knowledge cutoff. Current information requires an enabled web or X search tool; the base model does not receive live data automatically.

## Availability notes

- The API model page lists `us-east-1` and `us-west-2` regions.
- Requests beyond 200,000 context tokens use separate long-context pricing; consult the live pricing page.
- The launch post's benchmark comparisons are provider-reported. They are not used here as a cross-provider ranking.

## Links

- [Model page](https://docs.x.ai/developers/models/grok-4.5)
- [Developer guide](https://docs.x.ai/developers/grok-4-5)
- [Models and pricing](https://docs.x.ai/developers/models)
- [Launch announcement](https://x.ai/news/grok-4-5)

## Status

`[provider-doc]`.
