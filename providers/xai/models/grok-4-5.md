# Grok 4.5 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | SpaceXAI / xAI |
| Model ID | `grok-4.5` |
| Aliases | `grok-4.5-latest`, `grok-build-latest` |
| Lifecycle | Available; the models page now directs code and chat to [Grok 4.6](grok-4-6.md) |
| Input / output | Text and image / text |
| Context window | 500,000 tokens |
| Reasoning effort | `low`, `medium`, `high` (default); an `xhigh` request is treated as `high` |
| Capabilities | Function calling, structured outputs, reasoning |
| Regions | `us-east-1`, `us-west-2` |
| Rate limits | 150 requests/second; 50,000,000 tokens/minute |

Pricing is tiered on prompt length. Requests whose prompt reaches 200K tokens are billed at the higher rate for every token in the request.

| Type | < 200K prompt tokens | ≥ 200K prompt tokens |
|---|---|---|
| Input | $2.00 / 1M | $4.00 / 1M |
| Cached input | $0.30 / 1M | $0.60 / 1M |
| Output | $6.00 / 1M | $12.00 / 1M |

Source for the table above: [Grok 4.5 model page](https://docs.x.ai/developers/models/grok-4.5).

## What it is

Grok 4.5 is a coding and agentic-workflow model available through the Responses and Chat Completions APIs. As of this review it is no longer the model the docs recommend: the models page routes both code and chat to Grok 4.6, which publishes the same 500K context window and the same headline input and output prices but a higher cached-input price. [Models page](https://docs.x.ai/developers/models).

The `grok-build-latest` alias is listed on this model page. Separately, the Grok 4.6 developer guide names Grok 4.6 as the default model of the Grok Build agent. Those are two different surfaces; pin an explicit model ID rather than relying on the alias to track the agent's default. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6).

## Reasoning effort

Grok 4.5 accepts `reasoning.effort` values `low`, `medium`, and `high`, with `high` as the default. Reasoning cannot be disabled. Sending `xhigh` does not raise effort on this model; the docs state it is treated as `high`. Code written against Grok 4.6's `xhigh` therefore degrades silently if the model is switched back to Grok 4.5. [Reasoning parameter docs](https://docs.x.ai/developers/model-capabilities/text/reasoning).

## Unverified for this model

- No knowledge cutoff date is published on the Grok 4.5 model page. The models page states a cutoff only for Grok 4.6. An earlier revision of this page attributed the February 1, 2026 cutoff to Grok 4.5; that attribution is not supported by the current docs.
- The model page lists function calling and structured outputs. It does not list the server-side web search, X search, or code execution tools, and the web search tool documentation uses `grok-4.6` in its examples without publishing a supported-model list.
- The launch post's benchmark comparisons are provider-reported. They are not used here as a cross-provider ranking.

## Links

- [Model page](https://docs.x.ai/developers/models/grok-4.5)
- [Models and pricing](https://docs.x.ai/developers/models)
- [Reasoning effort parameter](https://docs.x.ai/developers/model-capabilities/text/reasoning)
- [Launch announcement](https://x.ai/news/grok-4-5)

## Status

`[provider-doc]`. The `https://docs.x.ai/developers/grok-4-5` guide URL previously cited here now serves Grok 4.6 content and has been dropped.
