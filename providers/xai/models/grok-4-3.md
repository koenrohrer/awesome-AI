# Grok 4.3 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | SpaceXAI / xAI |
| Model ID | `grok-4.3` |
| Aliases | `grok-4.3-latest` |
| Lifecycle | Available; also the redirect target for several retired Grok 4 and Grok 3 IDs |
| Input / output | Text and image / text |
| Context window | 1,000,000 tokens |
| Capabilities | Function calling, structured outputs, reasoning |
| Regions | `us-east-1`, `eu-west-1`, `us-west-2` |
| Rate limits | 37 requests/second; 10,000,000 tokens/minute |

Pricing is tiered on prompt length. Requests whose prompt reaches 200K tokens are billed at the higher rate for every token in the request. Batch API requests receive a 20% discount to standard rates.

| Type | < 200K prompt tokens | ≥ 200K prompt tokens |
|---|---|---|
| Input | $1.25 / 1M | $2.50 / 1M |
| Cached input | $0.20 / 1M | $0.40 / 1M |
| Output | $2.50 / 1M | $5.00 / 1M |

Source for the table above: [Grok 4.3 model page](https://docs.x.ai/developers/models/grok-4.3).

## What it is

The model page describes Grok 4.3 as a "Fast, reliable model with strong tool calling and instruction following capabilities." It publishes a 1,000,000-token context window, twice that of Grok 4.5 and Grok 4.6, at roughly half their per-token input price. [Models page](https://docs.x.ai/developers/models).

Grok 4.3 is also the documented landing point for retired IDs. The May 15, 2026 retirement guide redirects `grok-4-fast-reasoning`, `grok-4-1-fast-reasoning`, and `grok-4-0709` to `grok-4.3` with `low` reasoning effort, and `grok-4-fast-non-reasoning`, `grok-4-1-fast-non-reasoning`, and `grok-3` to `grok-4.3` with `none` reasoning effort. Old slugs therefore bill at Grok 4.3 rates. [Retirement guide](https://docs.x.ai/developers/migration/may-15-retirement).

## Unverified for this model

- No knowledge cutoff date is published on the Grok 4.3 model page. The models page states a cutoff only for Grok 4.6.
- Grok 4.3 does not appear in the `reasoning_effort` support table, which covers `grok-4.6`, `grok-4.5`, and `grok-4.20-multi-agent`. The model page marks reasoning as supported, but the accepted effort values are not documented there. [Reasoning parameter docs](https://docs.x.ai/developers/model-capabilities/text/reasoning).
- The model page lists function calling and structured outputs. It does not list the server-side web search, X search, or code execution tools that the Grok 4.6 guide names.

## Links

- [Model page](https://docs.x.ai/developers/models/grok-4.3)
- [Models and pricing](https://docs.x.ai/developers/models)
- [May 15, 2026 retirement guide](https://docs.x.ai/developers/migration/may-15-retirement)

## Status

`[provider-doc]`.
