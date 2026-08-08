# DeepSeek-V4-Flash `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

- Provider: DeepSeek
- Model ID: `deepseek-v4-flash`
- Hosted API version: DeepSeek-V4-Flash-0731 public beta
- Open-weight artifact: DeepSeek-V4-Flash preview release
- Parameters: 284B total / 13B active
- Context window: 1M tokens
- Max output: 384K tokens
- Official docs: [V4 release note](https://api-docs.deepseek.com/news/news260424), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)

## What it is

DeepSeek-V4-Flash is the smaller DeepSeek V4 model. On July 31, 2026, DeepSeek updated the hosted `deepseek-v4-flash` API to DeepSeek-V4-Flash-0731 and labeled it public beta.

## Notes

DeepSeek says the 0731 API version keeps the preview model's architecture and size but uses new post-training. The July update applies only to the hosted V4-Flash API; it does not announce replacement open weights or changes to V4-Pro or the app/web models.

The pricing page lists JSON output, tool calls, the Responses API, the Anthropic API, chat prefix completion, and non-thinking FIM completion for V4-Flash. The retired `deepseek-chat` and `deepseek-reasoner` aliases are no longer listed.

## Public system card availability

DeepSeek does not currently publish a public system-card page for V4-Flash.

## Links

- [V4 release note](https://api-docs.deepseek.com/news/news260424)
- [July 31 V4-Flash update](https://api-docs.deepseek.com/updates/)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Thinking mode](https://api-docs.deepseek.com/guides/thinking_mode)
- [Open weights collection](https://huggingface.co/collections/deepseek-ai/deepseek-v4)
- [DeepSeek-V4-Flash model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash)
- [Technical report](https://arxiv.org/abs/2606.19348)

## Status

`[provider-doc]`.
