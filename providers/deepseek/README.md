# DeepSeek `[provider-doc]`

*Last reviewed: 2026-08-06. DeepSeek-V4-Flash-0731 is the current hosted V4-Flash API version in public beta. The `deepseek-chat` and `deepseek-reasoner` aliases passed their retirement cutoff and are no longer listed on the pricing page.*

## Current model lines

| Surface | Backing model | Role | Notable feature |
|---|---|---|---|
| `deepseek-v4-pro` | DeepSeek-V4-Pro Preview | Larger hosted + open-weight model | 1.6T total / 49B active params; 1M context |
| `deepseek-v4-flash` | DeepSeek-V4-Flash-0731 API | Public-beta hosted API | 284B total / 13B active architecture; 1M context |
| `deepseek-chat` | Final mapping was V4-Flash non-thinking | Retired historical alias | Inaccessible after July 24, 2026 at 15:59 UTC |
| `deepseek-reasoner` | Final mapping was V4-Flash thinking | Retired historical alias | Inaccessible after July 24, 2026 at 15:59 UTC |
| DeepSeek-V3.2 | Prior open-weight top tier | General + agent use | Superseded by V4 Preview |
| DeepSeek-R1 | Open-weight reasoning family | Reasoning | First major open-weight reasoning breakout |

DeepSeek's API docs list `deepseek-v4-pro` and `deepseek-v4-flash` as the current model IDs. The older `deepseek-chat` and `deepseek-reasoner` names are historical only; migrate integrations to `deepseek-v4-flash` and select thinking mode explicitly.

## Model pages

- [DeepSeek-V4-Pro](models/deepseek-v4-pro.md)
- [DeepSeek-V4-Flash](models/deepseek-v4-flash.md)
- [deepseek-chat](models/deepseek-chat.md)
- [deepseek-reasoner](models/deepseek-reasoner.md)
- [DeepSeek-V3.2](models/deepseek-v3-2.md)
- [DeepSeek-R1](models/deepseek-r1.md)

## Model docs

- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Change log](https://api-docs.deepseek.com/updates/)
- [DeepSeek V4 Preview release](https://api-docs.deepseek.com/news/news260424)
- [DeepSeek V4 open weights](https://huggingface.co/collections/deepseek-ai/deepseek-v4)
- [DeepSeek V4 technical report](https://arxiv.org/abs/2606.19348)
- [DeepSeek-V3.2 release](https://api-docs.deepseek.com/news/news251201)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)

DeepSeek does not currently publish public “system cards” in the same style as Anthropic/OpenAI. The release notes, pricing docs, papers, and Hugging Face model cards are the practical equivalents.

## Strengths (cited)

- **Large open-weight V4 release.** V4-Pro is documented at 1.6T total / 49B active parameters, while V4-Flash is documented at 284B total / 13B active parameters. [DeepSeek V4 Preview release](https://api-docs.deepseek.com/news/news260424).
- **1M-token context on current hosted IDs.** The pricing page lists 1M context length for both `deepseek-v4-pro` and `deepseek-v4-flash`. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Open-weight frontier-adjacent releases.** DeepSeek still publishes major model weights openly on [Hugging Face](https://huggingface.co/deepseek-ai).
- **Reasoning and tool-use modes on V4.** Both V4 hosted IDs support thinking and non-thinking modes, JSON output, tool calls, and OpenAI/Anthropic-compatible API surfaces. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/), [thinking mode](https://api-docs.deepseek.com/guides/thinking_mode).
- **Responses API on V4-Flash.** The 0731 hosted V4-Flash API supports DeepSeek's Responses API surface; V4-Pro was still marked unsupported on the pricing page at review time. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Aggressive pricing.** The current published API pricing remains unusually low. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

## Weaknesses (cited)

- **Legacy aliases are retired.** DeepSeek documented both aliases as inaccessible after July 24, 2026 at 15:59 UTC, and neither appears on the current pricing page. [V4 release note](https://api-docs.deepseek.com/news/news260424/), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Documentation depth still lags the Western incumbents.** Advanced agent/framework details remain thinner.
- **Policy and deployment constraints matter.** Some teams will prefer self-hosting or third-party hosting for governance reasons rather than calling DeepSeek directly.

## Fits

- Cost-sensitive hosted inference
- Open-weight reasoning and research workloads
- Long-context agent workloads that can use the 1M-token V4 context window
- Benchmarks and experiments where open release artifacts matter

## Provider-specific quirks

- **Use the V4 IDs for all active integrations.** `deepseek-chat` and `deepseek-reasoner` are retired, not fallback compatibility names.
- **Separate hosted post-training from open weights.** The July 31 update changed only the hosted V4-Flash API; DeepSeek did not announce replacement weights in that update.
- **Thinking is mode-controlled.** V4 supports thinking and non-thinking behavior through request parameters rather than separate reasoning-only model families.
- **Release notes matter.** DeepSeek quietly changes what the aliases point to; monitor the [change log](https://api-docs.deepseek.com/updates/).

## Official docs

- [Platform](https://platform.deepseek.com/)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Change log](https://api-docs.deepseek.com/updates/)
- [List models API](https://api-docs.deepseek.com/api/list-models)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)
- [DeepSeek on GitHub](https://github.com/deepseek-ai)

## Status

`[provider-doc]`. This page reflects the V4-Flash-0731 public-beta API, the unchanged V4-Pro preview lifecycle, and completed retirement of the legacy aliases.
