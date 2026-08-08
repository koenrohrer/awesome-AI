# GPT-5.5 Pro `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

- Provider: OpenAI
- Model ID: `gpt-5.5-pro`
- Pinned snapshot: `gpt-5.5-pro-2026-04-23`
- Tier: Previous-generation higher-compute GPT-5.5 model; active in the API
- Context window: 1,050,000 tokens
- Max output: 128,000 tokens
- Modalities: text input/output; image input
- API price per 1M tokens: $30 input, $180 output; no cached-input discount
- Official docs: [model page](https://developers.openai.com/api/docs/models/gpt-5.5-pro), [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)

## What it is

GPT-5.5 Pro is OpenAI's higher-compute GPT-5.5 variant. OpenAI describes it as the path for harder questions and higher-accuracy work, and says GPT-5.5 safety results are generally treated as strong proxies for GPT-5.5 Pro except where the Pro setting could materially affect risk.

## Availability notes

- `gpt-5.5-pro` is available through the Responses and Batch APIs. OpenAI recommends background mode because requests can take several minutes.
- It supports function calling and structured outputs, but not streaming. Its hosted-tool support is narrower than the base GPT-5.5 model: the model page lists web search, file search, image generation, code interpreter, hosted shell, and MCP.
- OpenAI now recommends the GPT-5.6 family for new work. Keep GPT-5.5 Pro where its pinned behavior is part of an evaluated production contract.

## Links

- [Introducing GPT-5.5](https://openai.com/index/introducing-gpt-5-5/)
- [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)
- [GPT-5.5 Pro model page](https://developers.openai.com/api/docs/models/gpt-5.5-pro)
- [Current model guidance](https://developers.openai.com/api/docs/guides/latest-model)

## Status

`[provider-doc]`. Active API model; previous generation.
