# xAI `[provider-doc]`

*Last reviewed: 2026-08-16. The official documentation uses the SpaceXAI name while retaining `x.ai` domains and API endpoints. This catalog is date-stamped, not a ranking; verify against the live [models page](https://docs.x.ai/developers/models) before making cost or migration decisions.*

## Product surfaces

- **[Grok Build](grok-build.md)** — coding agent with interactive, headless, and Agent Client Protocol interfaces. The Grok 4.6 guide names Grok 4.6 as its default model.

## Current recommendation

The models page's "which model to choose" section routes code and chat to Grok 4.6, images to Grok Imagine Image 2.0, videos to Grok Imagine Video 1.5, and voice to the Grok Voice API. [Models page](https://docs.x.ai/developers/models).

Grok 4.5 remains available and priced, but it is no longer the recommended text model. Earlier revisions of this page called Grok 4.5 the current documented API model; that is no longer accurate.

## Text models

All rows below come from the [models page](https://docs.x.ai/developers/models) and the linked per-model pages. Input and output prices are the `< 200K prompt tokens` tier; requests whose prompt reaches 200K tokens are billed at a higher rate for every token in the request.

| Model ID | Context | Reasoning | Input / output per 1M | Cached input per 1M | Page |
|---|---|---|---|---|---|
| `grok-4.6` | 500K | Yes | $2.00 / $6.00 | $0.50 | [Grok 4.6](models/grok-4-6.md) |
| `grok-4.5` | 500K | Yes | $2.00 / $6.00 | $0.30 | [Grok 4.5](models/grok-4-5.md) |
| `grok-4.3` | 1M | Yes | $1.25 / $2.50 | $0.20 | [Grok 4.3](models/grok-4-3.md) |
| `grok-4.20-0309-reasoning` | 1M | Yes | $1.25 / $2.50 | $0.20 | [Grok 4.20](models/grok-4-20.md) |
| `grok-4.20-0309-non-reasoning` | 1M | No | $1.25 / $2.50 | $0.20 | [Grok 4.20](models/grok-4-20.md) |
| `grok-4.20-multi-agent-0309` | 1M | Yes | $1.25 / $2.50 | $0.20 | [Grok 4.20](models/grok-4-20.md) |
| `grok-build-0.1` | 256K | Yes | $1.00 / $2.00 | $0.20 | [Grok Build 0.1](models/grok-build-0-1.md) |

## Image, video, and voice models

These are covered as index rows only, from the docs. This repository does not keep dedicated pages for media and voice model IDs.

| Model ID | Modalities | Listed price | Notes |
|---|---|---|---|
| `grok-imagine-image-2.0` | text, image → image | $0.04 / image | The models page recommends this one for images |
| `grok-imagine-image` | text, image → image | $0.02 / image | Alias `grok-imagine-image-2026-03-02` |
| `grok-imagine-image-quality` | text, image → image | $0.05 / image | Aliases include `grok-imagine-image-quality-latest` and `grok-imagine-image-pro`; the retirement guide redirects `grok-imagine-image-pro` here |
| `grok-imagine-video-1.5` | text, image → video | $0.080 / second | The models page recommends this one for video; aliases `grok-imagine-video-1.5-preview`, `grok-imagine-video-1.5-2026-05-30` |
| `grok-imagine-video` | text, image, video → video | $0.050 / second | Accepts video input as well as text and image |
| `grok-voice-think-fast-2.0` | speech to speech | $0.08 / minute audio; $0.004 text input | Alias `grok-voice-latest` |
| `grok-voice-think-fast-1.0` | speech to speech | $0.05 / minute audio; $0.004 text input | Marked deprecated on the models page |

The models page also prices speech-to-text at $0.10/hour REST and $0.20/hour streaming, and text-to-speech at $15.00 per 1M characters, without naming model IDs for those modes.

## Model pages

- [Grok 4.6](models/grok-4-6.md)
- [Grok 4.5](models/grok-4-5.md)
- [Grok 4.3](models/grok-4-3.md)
- [Grok 4.20](models/grok-4-20.md)
- [Grok Build 0.1](models/grok-build-0-1.md)

### Retired aliases

These IDs still resolve. The [May 15, 2026 retirement guide](https://docs.x.ai/developers/migration/may-15-retirement) redirects them to a replacement with different behavior and pricing.

- [Grok 4 Fast (reasoning)](models/grok-4-fast-reasoning.md) — redirects to `grok-4.3` with `low` reasoning effort
- [Grok 4 Fast (non-reasoning)](models/grok-4-fast-non-reasoning.md) — redirects to `grok-4.3` with `none` reasoning effort
- [Grok Code Fast 1](models/grok-code-fast-1.md) — redirects to `grok-build-0.1`

The same guide also redirects `grok-4-1-fast-reasoning`, `grok-4-1-fast-non-reasoning`, `grok-4-0709`, and `grok-3` to `grok-4.3`, and `grok-imagine-image-pro` to `grok-imagine-image-quality`. This repository does not keep pages for those IDs.

## Official docs

- [xAI docs overview](https://docs.x.ai/docs)
- [Models and pricing](https://docs.x.ai/developers/models)
- [Grok 4.6 developer guide](https://docs.x.ai/developers/grok-4-6)
- [Grok 4.6 model page](https://docs.x.ai/developers/models/grok-4.6)
- [Grok 4.3 model page](https://docs.x.ai/developers/models/grok-4.3)
- [Reasoning effort parameter](https://docs.x.ai/developers/model-capabilities/text/reasoning)
- [May 15, 2026 retirement guide](https://docs.x.ai/developers/migration/may-15-retirement)
- [xAI news / blog](https://x.ai/news)

xAI does not publish a public "system card" hub in the Anthropic/OpenAI style. The model pages, the per-model developer guides, and news posts are the practical primary docs.

## Strengths (cited)

- **OpenAI-compatible API surface.** xAI exposes a familiar API shape, lowering integration friction for teams already wired for OpenAI-style clients. The Grok 4.6 guide shows the OpenAI SDK pointed at `https://api.x.ai/v1`. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6).
- **A 1M-context tier at a lower price than the flagship.** Grok 4.3 and the three Grok 4.20 variants publish 1,000,000-token context windows at $1.25 input / $2.50 output per 1M tokens, against 500K and $2.00 / $6.00 for Grok 4.6. [Models page](https://docs.x.ai/developers/models).
- **First-party server-side tools on the flagship.** The Grok 4.6 guide lists function calling, web search, X search, and code execution. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6).
- **Separate coding-agent surface.** Grok Build wraps the model with repository tools, permissions, extensions, and subagents. [Grok Build docs](https://docs.x.ai/build/overview).
- **Batch discount on the mid tier.** Grok 4.3 and the Grok 4.20 variants document a 20% discount on Batch API requests. [Grok 4.3 model page](https://docs.x.ai/developers/models/grok-4.3).

## Weaknesses (cited)

- **Live information is opt-in.** The models page states Grok has no knowledge of events beyond its training data and that realtime data requires enabling the web search or X search server tools. [Models page](https://docs.x.ai/developers/models).
- **Only one model publishes a knowledge cutoff.** February 1, 2026 is documented for Grok 4.6. The Grok 4.5, 4.3, 4.20, and `grok-build-0.1` model pages publish no cutoff date. [Models page](https://docs.x.ai/developers/models).
- **Reasoning-effort support is not uniform, and mismatches fail silently.** `xhigh` works on Grok 4.6; on Grok 4.5 the docs state it is treated as `high`. Grok 4.3 and `grok-4.20-0309-reasoning` do not appear in the support table at all. [Reasoning parameter docs](https://docs.x.ai/developers/model-capabilities/text/reasoning).
- **A 200K prompt is a price cliff, not a ramp.** Crossing 200K prompt tokens doubles the rate for every token in the request, on every text model. [Models page](https://docs.x.ai/developers/models).
- **Aliases can move, and there are a lot of them.** The Grok 4.20 variants each list a long set of beta and experimental-beta aliases; `grok-code-fast-1` is an alias of `grok-build-0.1`. Consistency-sensitive integrations should pin dated IDs. [Models page](https://docs.x.ai/developers/models).
- **Retired slugs still resolve.** Several Grok 4 Fast, Grok 3, and code IDs redirect to replacements with different context windows and pricing rather than erroring. [Retirement guide](https://docs.x.ai/developers/migration/may-15-retirement).
- **`logprobs` is gone on newer models.** The models page states `logprobs` and `top_logprobs` are unsupported by `grok-4.20` and newer.

## Fits

- Teams that want OpenAI-compatible integration with another frontier vendor
- Workflows that benefit from first-party web and X search as server-side tools
- Large-context agent tasks, where the 1M-token Grok 4.3 and 4.20 tiers cost less per token than the 500K flagship
- Parallel deep-research workloads, which `grok-4.20-multi-agent-0309` targets with an effort parameter that sets agent count
- Coding workflows that need a first-party terminal agent as well as a model API

## Provider-specific quirks

- **Reasoning is configurable but cannot be disabled** on the models that document it, and the accepted effort values differ per model.
- **`reasoning.effort` means something different on the multi-agent model.** There it selects agent count, 4 or 16, not reasoning depth.
- **Prompt-cache routing is explicit.** The Grok 4.6 guide recommends setting `prompt_cache_key` (Responses API) or the `x-grok-conv-id` header (Chat Completions) so a conversation reaches the same server; without it, requests can land cache-cold and pay full input price.
- **The name "Grok Build" covers two things.** The coding agent and the `grok-build-0.1` model ID are separate surfaces, and the agent's default model is Grok 4.6.
- **Model docs are more useful than blog posts.** For xAI, the live docs pages carry more operational value than announcements.

## Status

`[provider-doc]`. This page reflects Grok 4.6 as the model the docs recommend for code and chat, Grok 4.5 / 4.3 / 4.20 / `grok-build-0.1` as the other available text models, and Grok Build as a distinct coding-agent surface.
