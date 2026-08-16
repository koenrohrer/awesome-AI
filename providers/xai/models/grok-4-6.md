# Grok 4.6 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | SpaceXAI / xAI |
| Model ID | `grok-4.6` |
| Aliases | None listed on the model detail page |
| Lifecycle | Available; the models page directs code and chat workloads here |
| Input / output | Text and image / text |
| Context window | 500,000 tokens |
| Output limit | No text output limit documented |
| Knowledge cutoff | February 1, 2026 |
| Reasoning effort | `low`, `medium`, `high` (default), `xhigh` |
| Capabilities | Function calling, structured outputs, reasoning |
| Server tools | Web search, X search, code execution |
| APIs | Responses API and Chat Completions |
| Regions | `us-east-1`, `us-west-2` |
| Rate limits | 150 requests/second; 50,000,000 tokens/minute |

Pricing is tiered on prompt length. Requests whose prompt reaches 200K tokens are billed at the higher rate for every token in the request.

| Type | < 200K prompt tokens | ≥ 200K prompt tokens |
|---|---|---|
| Input | $2.00 / 1M | $4.00 / 1M |
| Cached input | $0.50 / 1M | $1.00 / 1M |
| Output | $6.00 / 1M | $12.00 / 1M |

Source for the table above: [Grok 4.6 model page](https://docs.x.ai/developers/models/grok-4.6).

## What it is

Grok 4.6 is described in the docs as SpaceXAI's frontier model for coding, agentic tasks, and knowledge work. The "which model to choose" section of the models page routes both code and chat to it. [Models page](https://docs.x.ai/developers/models).

The model has a February 1, 2026 knowledge cutoff. The models page states that Grok has no knowledge of events beyond its training data and that realtime data requires enabling the server-side web search or X search tools. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6).

## Reasoning effort

Grok 4.6 accepts `reasoning.effort` values `low`, `medium`, `high`, and `xhigh`, with `high` as the default. Reasoning cannot be disabled. `xhigh` is documented for Grok 4.6 but not for Grok 4.5, where the docs state an `xhigh` request is treated as `high`. [Reasoning parameter docs](https://docs.x.ai/developers/model-capabilities/text/reasoning).

The docs also state that `presence_penalty`, `frequency_penalty`, and `stop` cannot be used with reasoning models, and that `logprobs` and `top_logprobs` are unsupported on `grok-4.20` and newer. [Models page](https://docs.x.ai/developers/models).

## Operational notes

- The guide recommends setting `prompt_cache_key` on the Responses API, or the `x-grok-conv-id` header on Chat Completions, to route a conversation's requests to the same server so cache hits are reliable. Without it, requests can land on a cache-cold server and pay full input price. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6).
- The same guide points long agent loops at context compaction.
- The guide lists availability on the xAI API, as the default model of Grok Build, in Cursor, and through the OpenRouter, Vercel, and Cloudflare gateways.
- Benchmark figures are not published on the docs pages; the guide defers to the launch announcement. Those results are provider-reported and are not used here as a cross-provider ranking.

## Links

- [Model page](https://docs.x.ai/developers/models/grok-4.6)
- [Grok 4.6 developer guide](https://docs.x.ai/developers/grok-4-6)
- [Models and pricing](https://docs.x.ai/developers/models)
- [Reasoning effort parameter](https://docs.x.ai/developers/model-capabilities/text/reasoning)
- [Launch announcement](https://x.ai/news/grok-4-6)

## Status

`[provider-doc]`.
