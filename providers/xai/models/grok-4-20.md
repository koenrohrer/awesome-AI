# Grok 4.20 `[provider-doc]`

*Last reviewed: 2026-08-16.*

Grok 4.20 ships as three separate model IDs on the models page: a reasoning variant, a non-reasoning variant, and a multi-agent variant. They share a 1,000,000-token context window and the same token pricing, and differ in reasoning support, rate limits, and what `reasoning.effort` controls.

## Variants

| Field | Reasoning | Non-reasoning | Multi-agent |
|---|---|---|---|
| Model ID | `grok-4.20-0309-reasoning` | `grok-4.20-0309-non-reasoning` | `grok-4.20-multi-agent-0309` |
| Short aliases | `grok-4.20`, `grok-4.20-reasoning`, `grok-4.20-reasoning-latest` | `grok-4.20-non-reasoning`, `grok-4.20-non-reasoning-latest` | `grok-4.20-multi-agent`, `grok-4.20-multi-agent-latest` |
| Input / output | Text and image / text | Text and image / text | Text and image / text |
| Context window | 1,000,000 tokens | 1,000,000 tokens | 1,000,000 tokens |
| Function calling | Yes | Yes | Yes |
| Structured outputs | Yes | Yes | Yes |
| Reasoning | Yes | No | Yes |
| Requests / second | 37 | 37 | 9 |
| Tokens / minute | 10,000,000 | 10,000,000 | 2,500,000 |
| Regions | `us-east-1`, `us-west-2` | `us-east-1`, `us-west-2` | `us-east-1`, `us-west-2` |

Each model page also lists a longer set of beta and experimental-beta aliases; check the page before pinning one.

## Pricing

All three variants publish the same tiered rates. Requests whose prompt reaches 200K tokens are billed at the higher rate for every token in the request. Batch API requests receive a 20% discount to standard rates.

| Type | < 200K prompt tokens | ≥ 200K prompt tokens |
|---|---|---|
| Input | $1.25 / 1M | $2.50 / 1M |
| Cached input | $0.20 / 1M | $0.40 / 1M |
| Output | $2.50 / 1M | $5.00 / 1M |

Source for the tables above: the three model pages linked below.

## What the multi-agent variant does

The multi-agent model page describes it as one where multiple agents collaborate in parallel to perform deep research tasks. Its `reasoning.effort` parameter does not control reasoning depth: the reasoning docs state that for `grok-4.20-multi-agent` the parameter controls agent count, 4 or 16, across `low`, `medium`, `high`, and `xhigh`. Its published rate limits are roughly a quarter of the other two variants. [Reasoning parameter docs](https://docs.x.ai/developers/model-capabilities/text/reasoning).

Budget for a fan-out: an effort setting that runs 16 agents in parallel consumes tokens accordingly, and the per-token price is the same as the single-agent variants.

## Operational notes

- `logprobs` and `top_logprobs` are not supported by `grok-4.20` and newer models. [Models page](https://docs.x.ai/developers/models).
- The models page directs code and chat workloads to [Grok 4.6](grok-4-6.md), not to Grok 4.20.
- No knowledge cutoff date is published on the Grok 4.20 model pages. The models page states a cutoff only for Grok 4.6.
- The reasoning and non-reasoning model pages do not list server-side web search, X search, or code execution.

## Links

- [Grok 4.20 reasoning model page](https://docs.x.ai/developers/models/grok-4.20-0309-reasoning)
- [Grok 4.20 non-reasoning model page](https://docs.x.ai/developers/models/grok-4.20-0309-non-reasoning)
- [Grok 4.20 multi-agent model page](https://docs.x.ai/developers/models/grok-4.20-multi-agent-0309)
- [Models and pricing](https://docs.x.ai/developers/models)

## Status

`[provider-doc]`.
