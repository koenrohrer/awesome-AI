# Gemini 3.1 Pro Preview `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

- Provider: Google
- Model ID: `gemini-3.1-pro-preview`
- Tier: Current Gemini 3-series preview reasoning model
- Context window: 1,048,576 input / 65,536 output tokens
- Official docs: [model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-pro-preview), [Gemini models page](https://ai.google.dev/gemini-api/docs/models)

## What it is

Gemini 3.1 Pro Preview is the current Pro-class Gemini 3-series preview model listed on Google's live Gemini models page. It supersedes the earlier Gemini 3 Pro Preview entry, which Google's models page says was deprecated and shut down on March 9, 2026.

## Integration notes

- The model remains preview; preview endpoints can change and receive at least two weeks' deprecation notice under Google's documented lifecycle policy.
- Gemini 3-series models use `thinking_level` controls rather than the older `thinking_budget` path.
- Google's Gemini 3 guide documents 1M input context, 64K output, thought signatures, and tool-support differences versus Gemini 2.5.

## Links

- [Gemini models page](https://ai.google.dev/gemini-api/docs/models)
- [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-pro-preview)
- [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3)
- [Gemini deprecations](https://ai.google.dev/gemini-api/docs/deprecations)

## Status

`[provider-doc]`.
