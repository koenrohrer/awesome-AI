# DeepSeek-V4-Flash `[provider-doc]`

*Last reviewed: 2026-05-03.*

## At a glance

- Provider: DeepSeek
- Model ID: `deepseek-v4-flash`
- Release status: V4 Preview hosted model + open-weight release
- Parameters: 284B total / 13B active
- Context window: 1M tokens
- Max output: 384K tokens
- Official docs: [V4 release note](https://api-docs.deepseek.com/news/news260424), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)

## What it is

DeepSeek-V4-Flash is the smaller and lower-cost DeepSeek V4 Preview model. DeepSeek's API docs map the deprecated `deepseek-chat` and `deepseek-reasoner` aliases to V4-Flash non-thinking and thinking modes during the compatibility window.

## Notes

The pricing page lists JSON output, tool calls, chat prefix completion, and non-thinking FIM completion for V4-Flash. New integrations should use `deepseek-v4-flash` instead of the legacy aliases.

## Public system card availability

DeepSeek does not currently publish a public system-card page for V4-Flash.

## Links

- [V4 release note](https://api-docs.deepseek.com/news/news260424)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Thinking mode](https://api-docs.deepseek.com/guides/thinking_mode)
- [Open weights collection](https://huggingface.co/collections/deepseek-ai/deepseek-v4)
- [DeepSeek-V4-Flash model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash)
- [Technical report](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro/blob/main/DeepSeek_V4.pdf)

## Status

`[provider-doc]`.
