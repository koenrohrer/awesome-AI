# GPT-5.6 Terra `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | OpenAI |
| Model ID | `gpt-5.6-terra` |
| Availability | Generally available in the OpenAI API; also available in ChatGPT Work and Codex on eligible plans |
| Context / max input / max output | 1,050,000 / 922,000 / 128,000 tokens |
| Modalities | Text input/output; image input |
| Reasoning effort | `none`, `low`, `medium` (default), `high`, `xhigh`, `max` |
| Knowledge cutoff | February 16, 2026 |
| API price per 1M tokens | $2 input, $0.20 cached input, $12 output |
| Endpoints | Chat Completions, Responses, Batch |

## What it is

GPT-5.6 Terra is the balanced capability-and-cost tier in OpenAI's GPT-5.6 family. OpenAI maps it to the mini tier used in earlier GPT-5 families.

## API and tool support

The model supports streaming, function calling, structured outputs, and the Responses API tool set. The model page lists web search, file search, image generation, code interpreter, hosted shell, apply patch, skills, computer use, MCP, and tool search.

Prompts above 272K input tokens are priced at 2x input and 1.5x output for the whole request. Cache writes cost 1.25 times the uncached input rate.

OpenAI cut the Terra price by 20 percent on July 30, 2026, so the current model page lists lower prices than the July 9 launch announcement. Verify the live page when estimating cost. [Changelog](https://developers.openai.com/api/docs/changelog).

## Links

- [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-terra)
- [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/)
- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.6 model guidance](https://developers.openai.com/api/docs/guides/latest-model)

## Status

`[provider-doc]`. Generally available.
