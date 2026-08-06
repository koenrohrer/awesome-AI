# GPT-5.5 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

- Provider: OpenAI
- Model ID: `gpt-5.5`
- Pinned snapshot: `gpt-5.5-2026-04-23`
- Tier: Previous-generation frontier model; active in the API
- Context window: 1,050,000 tokens
- Max output: 128,000 tokens
- Modalities: text input/output; image input
- API price per 1M tokens: $5 input, $0.50 cached input, $30 output
- Official docs: [model page](https://developers.openai.com/api/docs/models/gpt-5.5), [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)

## What it is

GPT-5.5 is the April 2026 frontier model that preceded GPT-5.6. It remains available for pinned deployments and migration comparisons.

## Availability notes

- `gpt-5.5` is callable through Chat Completions, Responses, and Batch.
- The model supports streaming, function calling, structured outputs, and the hosted Responses API tool set listed on its model page.
- OpenAI now recommends the GPT-5.6 family for new work. Keep GPT-5.5 where its pinned behavior is part of an evaluated production contract.

## Links

- [Introducing GPT-5.5](https://openai.com/index/introducing-gpt-5-5/)
- [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)
- [GPT-5.5 model page](https://developers.openai.com/api/docs/models/gpt-5.5)
- [Current model guidance](https://developers.openai.com/api/docs/guides/latest-model)

## Status

`[provider-doc]`. Active API model; previous generation.
