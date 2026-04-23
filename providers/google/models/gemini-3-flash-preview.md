# Gemini 3 Flash Preview `[provider-doc]`

*Last reviewed: 2026-04-23.*

## At a glance

- Provider: Google
- Model ID: `gemini-3-flash-preview`
- Tier: Gemini 3 fast preview model
- Context window: 1M input tokens / 64K output tokens
- Official docs: [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3), [Gemini models page](https://ai.google.dev/gemini-api/docs/models)

## What it is

Gemini 3 Flash Preview is Google's fast Gemini 3 model for lower-latency, lower-cost multimodal and agentic workloads.

## Integration notes

- Gemini 3 Flash supports the `minimal`, `low`, `medium`, and `high` thinking levels documented in the Gemini 3 guide.
- Thought signatures must be preserved for tool and image workflows; official SDKs handle the normal chat-history path.
- Google documents a free tier for Gemini 3 Flash in the Gemini API, but production limits and pricing should be checked on the live pricing page.

## Links

- [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3)
- [Gemini models page](https://ai.google.dev/gemini-api/docs/models)
- [Gemini pricing](https://ai.google.dev/pricing)

## Status

`[provider-doc]`.
