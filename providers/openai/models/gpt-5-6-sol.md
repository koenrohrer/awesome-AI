# GPT-5.6 Sol `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | OpenAI |
| Model ID | `gpt-5.6-sol` |
| Alias | `gpt-5.6` |
| Availability | Generally available in the OpenAI API; also available in ChatGPT and Codex on eligible plans |
| Context / max input / max output | 1,050,000 / 922,000 / 128,000 tokens |
| Modalities | Text input/output; image input |
| Reasoning effort | `none`, `low`, `medium` (default), `high`, `xhigh`, `max` |
| Knowledge cutoff | February 16, 2026 |
| API price per 1M tokens | $5 input, $0.50 cached input, $30 output |
| Endpoints | Chat Completions, Responses, Batch |

## What it is

GPT-5.6 Sol is the flagship tier in OpenAI's GPT-5.6 family. The `gpt-5.6` alias routes to this model.

## API and tool support

The model supports streaming, function calling, structured outputs, and the Responses API tool set. The model page lists web search, file search, image generation, code interpreter, hosted shell, apply patch, skills, computer use, MCP, and tool search.

Prompts above 272K input tokens are priced at 2x input and 1.5x output for the whole request. Cache writes cost 1.25 times the uncached input rate. Check the live model page before estimating production cost.

## Service tiers

OpenAI replaced Priority Processing with Fast mode on July 30, 2026, extended Fast mode to prompts above 272K tokens on August 5, 2026, and announced Ultrafast mode for GPT-5.6 Sol on August 13, 2026 as a limited preview for selected customers. Ultrafast is not self-serve. [Changelog](https://developers.openai.com/api/docs/changelog).

## Links

- [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol)
- [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/)
- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.6 model guidance](https://developers.openai.com/api/docs/guides/latest-model)

## Status

`[provider-doc]`. Generally available.
