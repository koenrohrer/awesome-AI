# Moonshot AI `[provider-doc]`

*Last reviewed: 2026-08-16. Kimi K3 is Moonshot's current flagship, available as hosted `kimi-k3` access and as separately licensed open weights. Verify live availability on the [Kimi API Platform](https://platform.kimi.ai/) and [official model repository](https://github.com/MoonshotAI/Kimi-K3).*

## Current model lines

Per the [model list](https://platform.kimi.ai/docs/models) as reviewed on 2026-08-16.

| Model | Role | Notable feature |
|---|---|---|
| `kimi-k3` | Current multimodal flagship | 1M context; hosted API plus open weights |
| `kimi-k2.7-code` / `kimi-k2.7-code-highspeed` | Coding-focused line | 256K context; thinking forced on; hosted API plus open weights |
| `kimi-k2.6` | Earlier multimodal generalist | Text + vision, thinking/non-thinking modes, 256K context |
| `kimi-k2.5` | Earlier multimodal generalist | Closed to newly registered accounts; docs list a full platform sunset on August 31 |
| `moonshot-v1-*` | Legacy generation line | 8K/32K/128K text and vision-preview variants; docs list a full platform sunset on August 31 |

Deprecated on the [model list](https://platform.kimi.ai/docs/models) as reviewed on 2026-08-16: the `kimi-k2` series (`kimi-k2-0711-preview`, `kimi-k2-0905-preview`, `kimi-k2-turbo-preview`, `kimi-k2-thinking`, `kimi-k2-thinking-turbo`) discontinued 2026-05-25, `kimi-latest` discontinued 2026-01-28, and `kimi-thinking-preview` discontinued 2025-11-11. Deprecation of a hosted ID does not withdraw the matching open-weight release; check Hugging Face separately.

Moonshot's hosted API and downloadable artifacts are separate surfaces. Check the platform for current API features and prices, then check the model card and license for self-hosting claims.

## Model pages

- [Kimi K3](models/kimi-k3.md)
- [Kimi K2.7 Code](models/kimi-k2-7-code.md)
- [Kimi K2.6](models/kimi-k2-6.md)
- [Kimi K2.5](models/kimi-k2-5.md)
- [Kimi K2 Thinking](models/kimi-k2-thinking.md)

## Model docs

- [Kimi API Platform](https://platform.kimi.ai/)
- [Model list](https://platform.kimi.ai/docs/models)
- [Kimi K3 pricing and features](https://platform.kimi.ai/docs/pricing/chat-k3)
- [Kimi K3 model card](https://github.com/MoonshotAI/Kimi-K3)
- [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart)
- [Kimi K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code)
- [Kimi K2.6 pricing](https://platform.kimi.ai/docs/pricing/chat-k26)
- [Docs overview](https://platform.kimi.ai/docs/overview)
- [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model)
- [Pricing](https://platform.kimi.ai/docs/pricing/chat)

Moonshot does not currently publish a public system-card hub comparable to Anthropic/OpenAI. The model quickstarts, pricing pages, and open-weight release pages are the primary sources.

## Strengths (cited)

- **Tool-oriented hosted API.** The K3 platform documentation lists tool calls, structured output, tool-choice constraints, and dynamic tool loading. [Kimi K3 pricing and features](https://platform.kimi.ai/docs/pricing/chat-k3).
- **Hosted and open-weight K3 release.** Moonshot serves `kimi-k3` through its platform and separately publishes weights, a technical report, and a model-specific license. [Kimi K3 repository](https://github.com/MoonshotAI/Kimi-K3), [Kimi API Platform](https://platform.kimi.ai/).
- **Multimodal plus thinking in one main model.** `kimi-k2.6` combines text+vision with toggleable thinking/non-thinking modes. [Model list](https://platform.kimi.ai/docs/models), [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model).
- **A separate coding tier at a lower price.** `kimi-k2.7-code` runs a 256K context at roughly a third of K3's per-token prices, with a faster `-highspeed` ID at double the K2.7 Code rate. [Kimi K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code).
- **Open-weight lineage still matters.** Moonshot publishes Kimi K3 and Kimi K2.7 Code through its [Hugging Face org](https://huggingface.co/moonshotai). Licensing differs per model: the Kimi K3 License includes commercial conditions that require review, while [Kimi K2.7 Code](https://huggingface.co/moonshotai/Kimi-K2.7-Code) is released under a Modified MIT License.
- **Published per-token pricing.** The platform lists separate cache-hit, cache-miss, and output prices per model family. [Pricing](https://platform.kimi.ai/docs/pricing/chat).

## Weaknesses (cited)

- **Documentation is fragmented.** Core facts are split across homepage cards, overview pages, pricing docs, and bilingual guides.
- **Compatibility is model-specific.** K3 documents both OpenAI- and Anthropic-compatible APIs, while older guides may describe only the OpenAI-compatible path.
- **Fast deprecation cadence.** The whole `kimi-k2` series was discontinued on 2026-05-25, and the model list marks `kimi-k2.5` and the `moonshot-v1` series for a full platform sunset on August 31. Pin model IDs and recheck the [model list](https://platform.kimi.ai/docs/models) on a schedule.

## Fits

- Agentic coding and tool-use workflows
- Cost-sensitive long-context tasks
- Chinese/English cross-lingual work
- Teams that care about both hosted API access and open-weight releases

## Provider-specific quirks

- **K3 supports two compatibility surfaces.** Moonshot documents both OpenAI- and Anthropic-compatible API access for `kimi-k3`.
- **Thinking support is model-specific.** `kimi-k2.6` can toggle thinking; `kimi-k2.7-code` forces it on and errors if thinking is disabled.
- **K3 always reasons.** Callers choose a reasoning-effort level and must preserve the complete assistant message across multi-turn tool use.
- **K2.7 Code fixes sampling parameters.** `temperature`, `top_p`, `n`, and the presence and frequency penalties are pinned; other values return an error. [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart).
- **Vision support is no longer a separate special-case model.** The current `kimi-k3`, `kimi-k2.7-code`, and `kimi-k2.6` paths all take text, image, and video input natively. [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model).

## Official docs

- [Kimi API Platform](https://platform.kimi.ai/)
- [Kimi K3 repository](https://github.com/MoonshotAI/Kimi-K3)
- [Kimi K3 weights](https://huggingface.co/moonshotai/Kimi-K3)
- [Kimi K3 pricing](https://platform.kimi.ai/docs/pricing/chat-k3)
- [Kimi K2.7 Code weights](https://huggingface.co/moonshotai/Kimi-K2.7-Code)
- [Kimi K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code)
- [Model list](https://platform.kimi.ai/docs/models)
- [Docs overview](https://platform.kimi.ai/docs/overview)
- [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model)
- [Pricing](https://platform.kimi.ai/docs/pricing/chat)
- [Moonshot on Hugging Face](https://huggingface.co/moonshotai)

## Status

`[provider-doc]`. Reviewed 2026-08-16 against the platform model list, per-model pricing pages, and Hugging Face model cards. This page keeps each model's hosted API, open weights, and report surfaces separate. The `kimi-k2` series rows were removed because the model list marks that series discontinued as of 2026-05-25; `kimi-k2.5` and `moonshot-v1` remain listed but carry a documented sunset date. Prices on the model pages carry their review date and need a recheck before production use.
