# DeepSeek `[provider-doc]`

*Last reviewed: 2026-05-03. DeepSeek V4 Preview launched on April 24, 2026 with new hosted model IDs and open weights. Verify against the live [models and pricing page](https://api-docs.deepseek.com/quick_start/pricing/), [change log](https://api-docs.deepseek.com/updates/), and [V4 release note](https://api-docs.deepseek.com/news/news260424).*

## Current model lines

| Surface | Backing model | Role | Notable feature |
|---|---|---|---|
| `deepseek-v4-pro` | DeepSeek-V4-Pro | Flagship hosted + open-weight model | 1.6T total / 49B active params; 1M context |
| `deepseek-v4-flash` | DeepSeek-V4-Flash | Faster hosted + open-weight model | 284B total / 13B active params; 1M context |
| `deepseek-chat` | `deepseek-v4-flash` non-thinking mode | Legacy compatibility alias | Deprecated; retires July 24, 2026 |
| `deepseek-reasoner` | `deepseek-v4-flash` thinking mode | Legacy compatibility alias | Deprecated; retires July 24, 2026 |
| DeepSeek-V3.2 | Prior open-weight flagship | General + agent use | Superseded by V4 Preview |
| DeepSeek-R1 | Open-weight reasoning family | Reasoning | First major open-weight reasoning breakout |

DeepSeek's API docs now list `deepseek-v4-pro` and `deepseek-v4-flash` as the current model IDs. The older `deepseek-chat` and `deepseek-reasoner` names remain compatibility aliases for V4-Flash non-thinking and thinking modes until July 24, 2026.

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
- [DeepSeek V4 technical report](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro/blob/main/DeepSeek_V4.pdf)
- [DeepSeek-V3.2 release](https://api-docs.deepseek.com/news/news251201)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)

DeepSeek does not currently publish public “system cards” in the same style as Anthropic/OpenAI. The release notes, pricing docs, papers, and Hugging Face model cards are the practical equivalents.

## Strengths (cited)

- **Large open-weight V4 release.** V4-Pro is documented at 1.6T total / 49B active parameters, while V4-Flash is documented at 284B total / 13B active parameters. [DeepSeek V4 Preview release](https://api-docs.deepseek.com/news/news260424).
- **1M-token context on current hosted IDs.** The pricing page lists 1M context length for both `deepseek-v4-pro` and `deepseek-v4-flash`. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Open-weight frontier-adjacent releases.** DeepSeek still publishes major flagship weights openly on [Hugging Face](https://huggingface.co/deepseek-ai).
- **Reasoning and tool-use modes on V4.** Both V4 hosted IDs support thinking and non-thinking modes, JSON output, tool calls, and OpenAI/Anthropic-compatible API surfaces. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/), [thinking mode](https://api-docs.deepseek.com/guides/thinking_mode).
- **Aggressive pricing.** The current published API pricing remains unusually low. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

## Weaknesses (cited)

- **Legacy aliases are now migration paths.** `deepseek-chat` and `deepseek-reasoner` are compatibility names for V4-Flash modes and are scheduled to retire on July 24, 2026. [Change log](https://api-docs.deepseek.com/updates/).
- **Documentation depth still lags the Western incumbents.** Advanced agent/framework details remain thinner.
- **Policy and deployment constraints matter.** Some teams will prefer self-hosting or third-party hosting for governance reasons rather than calling DeepSeek directly.

## Best-fit tasks

- Cost-sensitive hosted inference
- Open-weight reasoning and research workloads
- Long-context agent workloads that can use the 1M-token V4 context window
- Benchmarks and experiments where open release artifacts matter

## Provider-specific quirks

- **Use the V4 IDs for new integrations.** `deepseek-chat` and `deepseek-reasoner` are deprecated compatibility aliases, not the current primary IDs.
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

`[provider-doc]`. This page now reflects the DeepSeek V4 Preview hosted IDs, open-weight release, 1M context claim, and deprecation path for `deepseek-chat` / `deepseek-reasoner` documented by DeepSeek itself.
