# DeepSeek-V4-Flash `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

- Provider: DeepSeek
- Model ID: `deepseek-v4-flash`
- Hosted API version: DeepSeek-V4-Flash-0731, announced as public beta
- Open-weight artifact: [DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731), MIT license
- Parameters: 284B total / 13B active
- Context window: 1M tokens
- Max output: 384K tokens
- Official docs: [V4 release note](https://api-docs.deepseek.com/news/news260424), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)

## What it is

DeepSeek-V4-Flash is the smaller DeepSeek V4 model. On July 31, 2026, DeepSeek updated the hosted `deepseek-v4-flash` API to DeepSeek-V4-Flash-0731 and labeled it public beta.

## Notes

DeepSeek says the 0731 API version keeps the preview model's architecture and size but uses new post-training. The change-log entry covers only the hosted V4-Flash API and states that V4-Pro and the app/web models were unchanged at that time; it does not mention weights, but the `DeepSeek-V4-Flash-0731` weights were published on Hugging Face the same day under the MIT license. [Change log](https://api-docs.deepseek.com/updates/), [model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731).

The pricing page lists JSON output, tool calls, the Responses API, the Anthropic API, chat prefix completion, and non-thinking FIM completion for V4-Flash. The retired `deepseek-chat` and `deepseek-reasoner` aliases are no longer listed.

The 2026-08-13 update added three thinking effort levels — `low`, `high`, `max`, default `high` — to V4-Flash as well as V4-Pro. [Change log](https://api-docs.deepseek.com/updates/), [thinking mode](https://api-docs.deepseek.com/guides/thinking_mode).

Peak/off-peak pricing took effect at 16:00 UTC on 2026-08-16 and applies to this model. As listed on 2026-08-16, per 1M tokens: input cache hit $0.007 off-peak / $0.014 peak, input cache miss $0.22 / $0.44, output $0.66 / $1.32, with a 2,500 concurrent-request limit. Peak hours are 01:00-04:00 and 06:00-10:00 UTC. Recheck before relying on these figures. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

## Public system card availability

DeepSeek does not currently publish a public system-card page for V4-Flash.

## Links

- [V4 release note](https://api-docs.deepseek.com/news/news260424)
- [July 31 V4-Flash update](https://api-docs.deepseek.com/updates/)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Thinking mode](https://api-docs.deepseek.com/guides/thinking_mode)
- [Codex integration](https://api-docs.deepseek.com/quick_start/agent_integrations/codex)
- [Open weights collection](https://huggingface.co/collections/deepseek-ai/deepseek-v4)
- [DeepSeek-V4-Flash-0731 model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731)
- [DeepSeek-V4-Flash preview model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash)
- [Technical report](https://arxiv.org/abs/2606.19348)

## Status

`[provider-doc]`.
