# Gemini 3.6 Flash `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Model ID | `gemini-3.6-flash` |
| Lifecycle | Stable; July 2026 update |
| Input / output | Text, image, video, audio, and PDF / text |
| Token limits | 1,048,576 input / 65,536 output |
| Standard paid API price | $0.75 input / $3.75 output per 1M tokens through 2026-12-31; $1.50 / $7.50 from 2027-01-01 |
| Tools | Function calling, code execution, Search and Maps grounding, URL context, file search, structured outputs, and Computer Use (preview) |

## What it is

Gemini 3.6 Flash is a stable Gemini 3 Flash model for multimodal and agentic workloads. The model page lists thinking, caching, Batch, Flex, and Priority inference support in addition to the tools above, and marks Live API, image generation, and audio generation as unsupported.

As of the review date it is no longer the newest stable Flash model; [Gemini 3.7 Flash](gemini-3-7-flash.md) carries an August 2026 update with the same token limits and the same published token prices.

Computer Use remains a preview capability even though the underlying model is stable. Google recommends supervision and a sandbox for UI-control tasks.

The price above is the published token rate: an introductory figure that ends 2026-12-31 and a higher figure after it. Grounding requests and cache storage are billed separately.

## Links

- [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.6-flash)
- [Gemini models](https://ai.google.dev/gemini-api/docs/models)
- [Computer Use](https://ai.google.dev/gemini-api/docs/computer-use)
- [Pricing](https://ai.google.dev/gemini-api/docs/pricing)

## Status

`[provider-doc]`.
