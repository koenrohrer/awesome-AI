# GPT (OpenAI) `[provider-doc]`

*Last reviewed: 2026-04-22. Verify specs against [OpenAI's models page](https://platform.openai.com/docs/models) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| GPT-5 / GPT-4.1 series | General flagship | Multimodal input, long context |
| o-series (o3, o4-mini, etc.) | Reasoning | Internal extended reasoning; `reasoning_effort` control |
| GPT-4o-mini / mini-series | Low-cost general | Cheap, fast, wide context |
| Realtime (voice) | Audio | Low-latency speech-to-speech |

Model IDs and pricing change frequently — the [pricing page](https://openai.com/api/pricing/) is authoritative.

## Strengths (cited)

- **Broad multimodal coverage.** Vision, audio input, realtime voice, and image generation (DALL-E family, image models) exposed in a single provider API. See [capabilities overview](https://platform.openai.com/docs/overview).
- **Hosted tools.** `web_search`, `file_search`, `code_interpreter`, and computer-use are provider-hosted — no infrastructure to run for common agent needs. [Tools docs](https://platform.openai.com/docs/guides/tools).
- **Reasoning models.** o-series exposes `reasoning_effort` (minimal/low/medium/high) for controllable compute-vs-accuracy. [Reasoning docs](https://platform.openai.com/docs/guides/reasoning).
- **Batch API.** 50% discount for async jobs returning within 24 hours. [Batch API](https://platform.openai.com/docs/guides/batch).
- **Prompt caching is automatic** on eligible prompts with ~50% discount on cached input tokens. [Prompt caching](https://platform.openai.com/docs/guides/prompt-caching).

## Weaknesses (cited)

- **Context window asymmetry.** Some model variants have large input windows but much smaller output limits. Check the [model capabilities table](https://platform.openai.com/docs/models) before assuming you can generate long outputs.
- **Rate-limit complexity.** Tier-based quotas differ across model families; production deployments often need to manage multiple tiers. [Rate limits](https://platform.openai.com/docs/guides/rate-limits).

## Best-fit tasks

- Multimodal workflows (especially audio input/output and image generation in the same pipeline)
- Agent workflows that benefit from hosted `web_search` / `code_interpreter` without self-hosting
- Reasoning-heavy tasks where `reasoning_effort` tuning is useful
- Cost-sensitive async workloads (Batch API)

## Provider-specific quirks

- **Responses API vs Chat Completions.** The Responses API is the newer unified surface; older integrations still use Chat Completions. For new work, prefer Responses. [API overview](https://platform.openai.com/docs/overview).
- **`strict: true` on functions** forces schema conformance at decoding time. Use it for tool-use reliability.
- **Structured Outputs** via `response_format: { type: "json_schema", ... }` is a separate path from function calling. [Structured Outputs docs](https://platform.openai.com/docs/guides/structured-outputs).

## Official docs

- [Models](https://platform.openai.com/docs/models)
- [Reasoning](https://platform.openai.com/docs/guides/reasoning)
- [Function calling](https://platform.openai.com/docs/guides/function-calling)
- [Tools (hosted)](https://platform.openai.com/docs/guides/tools)
- [Structured Outputs](https://platform.openai.com/docs/guides/structured-outputs)
- [Prompt caching](https://platform.openai.com/docs/guides/prompt-caching)
- [Pricing](https://openai.com/api/pricing/)

## Status

`[provider-doc]`.
