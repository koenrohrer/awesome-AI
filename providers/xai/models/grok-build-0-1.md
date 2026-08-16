# Grok Build 0.1 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | SpaceXAI / xAI |
| Model ID | `grok-build-0.1` |
| Aliases | `grok-code-fast-1`, `grok-code-fast`, `grok-code-fast-1-0825` |
| Lifecycle | Available; also the redirect target for the retired `grok-code-fast-1` |
| Input / output | Text and image / text |
| Context window | 256,000 tokens |
| Capabilities | Function calling, structured outputs, reasoning |
| Regions | `us-east-1`, `us-west-2` |
| Rate limits | 37 requests/second; 10,000,000 tokens/minute |

Pricing is tiered on prompt length.

| Type | < 200K prompt tokens | ≥ 200K prompt tokens |
|---|---|---|
| Input | $1.00 / 1M | $2.00 / 1M |
| Cached input | $0.20 / 1M | $0.40 / 1M |
| Output | $2.00 / 1M | $4.00 / 1M |

Source for the table above: [Grok Build 0.1 model page](https://docs.x.ai/developers/models/grok-build-0.1).

## What it is

The model page describes `grok-build-0.1` as a coding model for agentic software, engineering, and workflow tasks. It carries the lowest published input price of the text models on the models page and the smallest context window of them, at 256K tokens. [Models page](https://docs.x.ai/developers/models).

The retired `grok-code-fast-1` slug is an alias of this model. The May 15, 2026 retirement guide redirects `grok-code-fast-1` to `grok-build-0.1`, so callers still sending the old ID reach this model and its pricing. [Retirement guide](https://docs.x.ai/developers/migration/may-15-retirement).

## Not the same thing as the Grok Build product

The `grok-build-0.1` model ID and the [Grok Build](../grok-build.md) coding agent are separate surfaces that share a name. The Grok 4.6 developer guide names Grok 4.6 as the default model of the Grok Build agent, not `grok-build-0.1`. Separately, the `grok-build-latest` alias is listed on the Grok 4.5 model page. Pin an explicit model ID rather than reasoning from the name. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6), [Grok 4.5 model page](https://docs.x.ai/developers/models/grok-4.5).

## Unverified for this model

- No knowledge cutoff date is published on the model page.
- Accepted `reasoning_effort` values are not documented; the model does not appear in the reasoning support table.
- Server-side web search, X search, and code execution are not listed on the model page.

## Links

- [Model page](https://docs.x.ai/developers/models/grok-build-0.1)
- [Models and pricing](https://docs.x.ai/developers/models)
- [May 15, 2026 retirement guide](https://docs.x.ai/developers/migration/may-15-retirement)

## Status

`[provider-doc]`.
