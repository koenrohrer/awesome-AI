# GPT-5.6 Sol `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Provider | OpenAI |
| Model ID | `gpt-5.6-sol` |
| Alias | `gpt-5.6` |
| Availability | Generally available in the OpenAI API; also available in ChatGPT and Codex on eligible plans |
| Context / max output | 1,050,000 / 128,000 tokens |
| Modalities | Text input/output; image input |
| Reasoning effort | `none`, `low`, `medium`, `high`, `xhigh`, `max` |
| API price per 1M tokens | $5 input, $0.50 cached input, $30 output |

## What it is

GPT-5.6 Sol is the flagship tier in OpenAI's GPT-5.6 family. The `gpt-5.6` alias routes to this model.

## API and tool support

The model supports streaming, function calling, structured outputs, and the Responses API tool set. The model page lists web search, file search, image generation, code interpreter, hosted shell, apply patch, skills, computer use, MCP, and tool search.

OpenAI applies higher long-context pricing to requests with more than 272K input tokens. Cache writes cost 1.25 times the uncached input rate. Check the live model page before estimating production cost.

## Links

- [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol)
- [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/)
- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.6 model guidance](https://developers.openai.com/api/docs/guides/latest-model)

## Status

`[provider-doc]`. Generally available.
