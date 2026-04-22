# Gemini (Google) `[provider-doc]`

*Last reviewed: 2026-04-22. Verify specs against [Google's Gemini models page](https://ai.google.dev/gemini-api/docs/models) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Gemini 2.5 Pro | Flagship | 1M-token context, thinking support |
| Gemini 2.5 Flash | Fast/cheap | 1M context with lower latency |
| Gemini 2.5 Flash-Lite | Lowest-cost | Tight latency/cost budgets |

Model IDs roll forward; the [models page](https://ai.google.dev/gemini-api/docs/models) is authoritative.

## Strengths (cited)

- **Very long context.** 1M-token context windows across the 2.x series. See [long context docs](https://ai.google.dev/gemini-api/docs/long-context).
- **Native multimodality.** Text, images, audio, and video input handled by the same model family. See the [vision and video docs](https://ai.google.dev/gemini-api/docs/vision).
- **Thinking mode with explicit budget.** Configurable thinking-token budget on 2.5 series.
- **Context caching.** Explicit, managed cache objects via API — you create a cache handle, reuse it across calls, pay per-token storage while it's alive. See the caching docs linked in [integrations/ci-cd/](../integrations/ci-cd/) (note: ai.google.dev URLs excluded from our automated link-check due to their regional redirects).
- **Free-tier API access.** Google offers a generous free tier for development — see [Gemini API keys](https://ai.google.dev/gemini-api/docs/api-key).

## Weaknesses (cited)

- **Tool/function-calling ergonomics.** The schema format and tool-orchestration conventions differ from OpenAI and Anthropic in ways that complicate cross-provider agents. Provider-doc coverage: [function calling](https://ai.google.dev/gemini-api/docs/function-calling).
- **Cache is explicit, not automatic.** You manage lifecycle (create, reuse, delete) yourself — more operational overhead than automatic caches elsewhere.

## Best-fit tasks

- Very long document or code analysis (where 1M-token context genuinely matters)
- Multimodal-first workflows that combine video, audio, and text as first-class inputs
- Budget-constrained prototyping (free-tier access)
- Tasks where explicit cache control (multi-hour TTL, explicit invalidation) is preferred over automatic caching

## Provider-specific quirks

- **Two SDK surfaces.** `google-generativeai` (legacy) vs `google-genai` (new, unified with Vertex AI). For new work, use `google-genai`. Check current [SDK docs](https://ai.google.dev/gemini-api/docs) for the recommended package.
- **AI Studio vs Vertex AI.** Same models, two environments — AI Studio for prototyping, Vertex AI for production with enterprise features. [AI Studio](https://aistudio.google.com/), [Vertex AI](https://cloud.google.com/vertex-ai).

## Official docs

- [Gemini API docs](https://ai.google.dev/gemini-api/docs)
- [Models](https://ai.google.dev/gemini-api/docs/models)
- [Long context](https://ai.google.dev/gemini-api/docs/long-context)
- [Thinking](https://ai.google.dev/gemini-api/docs/thinking)
- [Function calling](https://ai.google.dev/gemini-api/docs/function-calling)
- [Vision and video](https://ai.google.dev/gemini-api/docs/vision)
- [Pricing](https://ai.google.dev/pricing)

## Status

`[provider-doc]`. Prices, benchmark rankings, and exact model IDs rotate.
