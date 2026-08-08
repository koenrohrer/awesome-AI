# Moonshot AI `[provider-doc]`

*Last reviewed: 2026-08-06. Kimi K3 is Moonshot's current flagship, available as hosted `kimi-k3` access and as separately licensed open weights. Verify live availability on the [Kimi API Platform](https://platform.kimi.ai/) and [official model repository](https://github.com/MoonshotAI/Kimi-K3).*

## Current model lines

| Model | Role | Notable feature |
|---|---|---|
| `kimi-k3` | Current multimodal flagship | 1M context; hosted API plus open weights |
| `kimi-k2.6` | Earlier multimodal generalist | Text + vision, thinking/non-thinking modes, 256K context |
| `kimi-k2.5` | Multimodal generalist | Text + vision, thinking/non-thinking modes, agent tasks |
| `kimi-k2` / `kimi-k2-0905-preview` | Base K2 line | Strong code and agent performance; open-weight lineage |
| `kimi-k2-thinking` / `kimi-k2-thinking-turbo` | Dedicated reasoning line | Thinking-focused variants for deeper reasoning |
| `kimi-k2-turbo-preview` | Faster preview tier | Speed-focused K2 path |

Moonshot's hosted API and downloadable artifacts are separate surfaces. Check the platform for current API features and prices, then check the model card and license for self-hosting claims.

## Model pages

- [Kimi K3](models/kimi-k3.md)
- [Kimi K2.6](models/kimi-k2-6.md)
- [Kimi K2.5](models/kimi-k2-5.md)
- [Kimi K2 Thinking](models/kimi-k2-thinking.md)

## Model docs

- [Kimi API Platform](https://platform.kimi.ai/)
- [Kimi K3 pricing and features](https://platform.kimi.ai/docs/pricing/chat-k3)
- [Kimi K3 model card](https://github.com/MoonshotAI/Kimi-K3)
- [Docs overview](https://platform.kimi.ai/docs/overview)
- [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model)
- [Pricing](https://platform.kimi.ai/docs/pricing/chat)

Moonshot does not currently publish a public system-card hub comparable to Anthropic/OpenAI. The model quickstarts, pricing pages, and open-weight release pages are the primary sources.

## Strengths (cited)

- **Tool-oriented hosted API.** The K3 platform documentation lists tool calls, structured output, tool-choice constraints, and dynamic tool loading. [Kimi K3 pricing and features](https://platform.kimi.ai/docs/pricing/chat-k3).
- **Hosted and open-weight K3 release.** Moonshot serves `kimi-k3` through its platform and separately publishes weights, a technical report, and a model-specific license. [Kimi K3 repository](https://github.com/MoonshotAI/Kimi-K3), [Kimi API Platform](https://platform.kimi.ai/).
- **Multimodal plus thinking in one main model.** `kimi-k2.5` combines text+vision with toggleable thinking/non-thinking modes. [Docs overview](https://platform.kimi.ai/docs/overview), [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model).
- **Open-weight lineage still matters.** Moonshot publishes Kimi K3 through its [Hugging Face org](https://huggingface.co/moonshotai), but the Kimi K3 License includes commercial conditions that require review.
- **Published per-token pricing.** The platform lists separate cache-hit, input, and output prices for K3 and earlier hosted models. [Pricing](https://platform.kimi.ai/docs/pricing/chat).

## Weaknesses (cited)

- **Documentation is fragmented.** Core facts are split across homepage cards, overview pages, pricing docs, and bilingual guides.
- **Compatibility is model-specific.** K3 documents both OpenAI- and Anthropic-compatible APIs, while older guides may describe only the OpenAI-compatible path.
- **Preview-heavy naming.** Moonshot keeps several preview and turbo names in circulation, which makes production pinning more important.

## Fits

- Agentic coding and tool-use workflows
- Cost-sensitive long-context tasks
- Chinese/English cross-lingual work
- Teams that care about both hosted API access and open-weight releases

## Provider-specific quirks

- **K3 supports two compatibility surfaces.** Moonshot documents both OpenAI- and Anthropic-compatible API access for `kimi-k3`.
- **Thinking support is model-specific.** `kimi-k2.5` can toggle thinking; `kimi-k2-thinking` forces it on.
- **K3 always reasons.** Callers choose a reasoning-effort level and must preserve the complete assistant message across multi-turn tool use.
- **Vision support is no longer a separate special-case model.** The latest general-purpose K2.5 path handles text and visual input natively.

## Official docs

- [Kimi API Platform](https://platform.kimi.ai/)
- [Kimi K3 repository](https://github.com/MoonshotAI/Kimi-K3)
- [Kimi K3 weights](https://huggingface.co/moonshotai/Kimi-K3)
- [Kimi K3 pricing](https://platform.kimi.ai/docs/pricing/chat-k3)
- [Docs overview](https://platform.kimi.ai/docs/overview)
- [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model)
- [Pricing](https://platform.kimi.ai/docs/pricing/chat)
- [Moonshot on Hugging Face](https://huggingface.co/moonshotai)

## Status

`[provider-doc]`. This page distinguishes Kimi K3's hosted API, open weights, and technical-report surfaces from the older K2 model lines.
