# DeepSeek `[provider-doc]`

*Last reviewed: 2026-04-23. DeepSeek's hosted API has converged on a simpler two-alias model surface even while the open-weight release story keeps moving. Verify against the live [models and pricing page](https://api-docs.deepseek.com/quick_start/pricing/) and [change log](https://api-docs.deepseek.com/updates/).*

## Current model lines

| Surface | Backing model | Role | Notable feature |
|---|---|---|---|
| `deepseek-chat` | DeepSeek-V3.2 (non-thinking) | General chat | Tool calls, JSON output, lower-cost path |
| `deepseek-reasoner` | DeepSeek-V3.2 (thinking) | Reasoning | Thinking mode with much larger output ceiling |
| DeepSeek-V3.2 | Open-weight flagship | General + agent use | Official open-weight release |
| DeepSeek-R1 | Open-weight reasoning family | Reasoning | First major open-weight reasoning breakout |

The public API docs now explicitly state that `deepseek-chat` and `deepseek-reasoner` both map to DeepSeek-V3.2, rather than separate branded API models.

## Model pages

- [deepseek-chat](models/deepseek-chat.md)
- [deepseek-reasoner](models/deepseek-reasoner.md)
- [DeepSeek-V3.2](models/deepseek-v3-2.md)
- [DeepSeek-R1](models/deepseek-r1.md)

## Model docs

- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Change log](https://api-docs.deepseek.com/updates/)
- [DeepSeek-V3.2 release](https://api-docs.deepseek.com/news/news251201)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)

DeepSeek does not currently publish public “system cards” in the same style as Anthropic/OpenAI. The release notes, pricing docs, papers, and Hugging Face model cards are the practical equivalents.

## Strengths (cited)

- **Simple hosted API surface.** Two aliases cover the main hosted paths: chat and reasoner. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Open-weight frontier-adjacent releases.** DeepSeek still publishes major flagship weights openly on [Hugging Face](https://huggingface.co/deepseek-ai).
- **Reasoning baked into tool use.** DeepSeek's V3.2 release notes call out thinking integrated with tool-use. [DeepSeek-V3.2 release](https://api-docs.deepseek.com/news/news251201).
- **Aggressive pricing.** The current published API pricing remains unusually low. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

## Weaknesses (cited)

- **Hosted surface is narrower than the open-weight brand story suggests.** The public API is effectively two aliases, not a broad branded family menu.
- **Documentation depth still lags the Western incumbents.** Advanced agent/framework details remain thinner.
- **Policy and deployment constraints matter.** Some teams will prefer self-hosting or third-party hosting for governance reasons rather than calling DeepSeek directly.

## Best-fit tasks

- Cost-sensitive hosted inference
- Open-weight reasoning and research workloads
- Agent systems that want separate chat vs reasoner routing with minimal model-selection complexity
- Benchmarks and experiments where open release artifacts matter

## Provider-specific quirks

- **Do not assume the app/web naming maps to the API.** The pricing page explicitly says the API surface differs from app/web branding.
- **Thinking is routed via `deepseek-reasoner`.** You are not selecting a separate branded “R1” API model for the main hosted path.
- **Release notes matter.** DeepSeek quietly changes what the aliases point to; monitor the [change log](https://api-docs.deepseek.com/updates/).

## Official docs

- [Platform](https://platform.deepseek.com/)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Change log](https://api-docs.deepseek.com/updates/)
- [List models API](https://api-docs.deepseek.com/api/list-models)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)
- [DeepSeek on GitHub](https://github.com/deepseek-ai)

## Status

`[provider-doc]`. This page now reflects the current hosted aliases (`deepseek-chat`, `deepseek-reasoner`) and the underlying DeepSeek-V3.2 mapping documented by DeepSeek itself.
