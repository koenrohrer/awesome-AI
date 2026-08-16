# Gemini 3.7 Flash `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Model ID | `gemini-3.7-flash` |
| Lifecycle | Stable; August 2026 update |
| Input / output | Text, image, video, audio, and PDF / text |
| Token limits | 1,048,576 input / 65,536 output |
| Standard paid API price | $0.75 input / $3.75 output per 1M tokens through 2026-12-31; $1.50 / $7.50 from 2027-01-01 |
| Tools | Function calling, code execution, Search and Maps grounding, URL context, file search, structured outputs, and Computer Use (preview) |
| Not supported | Live API, image generation, audio generation |

## What it is

Gemini 3.7 Flash is the newest stable model in the Gemini 3 Flash line. The [model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.7-flash) describes it as "the next iteration in the Gemini 3 series of highly-capable, natively multimodal, reasoning models" and lists caching, Batch, Flex, and Priority inference alongside the tools above.

Thinking is supported at `low`, `medium`, and `high`. The `minimal` level available on some smaller Gemini 3 models is not supported here, so a request that assumes `minimal` needs a different model or a changed setting. See the [thinking docs](https://ai.google.dev/gemini-api/docs/thinking).

Computer Use is a preview capability on this model. Google recommends supervision and a sandbox for UI-control tasks. See the [Computer Use guide](https://ai.google.dev/gemini-api/docs/computer-use).

The two-part price above is what the pricing page publishes: an introductory rate that ends 2026-12-31 and a higher rate after it. Cost models built on the introductory rate will roughly double at that date. Grounding requests and cache storage are billed separately.

## Relation to Gemini 3.6 Flash

Both are stable, take the same modalities, and publish the same 1,048,576 / 65,536 token limits and the same standard token prices. The visible difference in the docs is the update date: August 2026 for 3.7 Flash, July 2026 for [3.6 Flash](gemini-3-6-flash.md). No head-to-head benchmark for the pair was found on the models page as of the review date, so pick between them with your own eval rather than by version number.

## Links

- [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.7-flash)
- [Gemini models](https://ai.google.dev/gemini-api/docs/models)
- [Computer Use](https://ai.google.dev/gemini-api/docs/computer-use)
- [Thinking](https://ai.google.dev/gemini-api/docs/thinking)
- [Pricing](https://ai.google.dev/gemini-api/docs/pricing)

## Status

`[provider-doc]`.
