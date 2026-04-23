# Moonshot AI `[provider-doc]`

*Last reviewed: 2026-04-23. Moonshot's public platform now exposes multiple K2-era generations at once; verify exact model availability on the live [platform homepage](https://platform.moonshot.ai/) and [docs overview](https://platform.moonshot.ai/docs/overview).*

## Current model lines

| Model | Role | Notable feature |
|---|---|---|
| `kimi-k2.6` | Current flagship | Latest Kimi text model, stronger long-horizon coding and agent execution |
| `kimi-k2.5` | Multimodal generalist | Text + vision, thinking/non-thinking modes, agent tasks |
| `kimi-k2` / `kimi-k2-0905-preview` | Base K2 line | Strong code and agent performance; open-weight lineage |
| `kimi-k2-thinking` / `kimi-k2-thinking-turbo` | Dedicated reasoning line | Thinking-focused variants for deeper reasoning |
| `kimi-k2-turbo-preview` | Faster preview tier | Speed-focused K2 path |

Moonshot's docs split the story between the platform homepage, the docs overview, pricing, and a smaller set of stable guide pages, so you usually need more than one tab open at once.

## Model pages

- [Kimi K2.6](models/kimi-k2-6.md)
- [Kimi K2.5](models/kimi-k2-5.md)
- [Kimi K2 Thinking](models/kimi-k2-thinking.md)

## Model docs

- [Moonshot platform](https://platform.moonshot.ai/)
- [Docs overview](https://platform.moonshot.ai/docs/overview)
- [Use the Kimi vision model](https://platform.moonshot.ai/docs/guide/use-kimi-vision-model)
- [Pricing](https://platform.moonshot.ai/docs/pricing/chat)

Moonshot does not currently publish a public system-card hub comparable to Anthropic/OpenAI. The model quickstarts, pricing pages, and open-weight release pages are the primary sources.

## Strengths (cited)

- **Strong current coding/agent focus.** The platform homepage and docs overview position Kimi explicitly for code generation, agent tasks, and tool use. [Platform homepage](https://platform.moonshot.ai/), [Docs overview](https://platform.moonshot.ai/docs/overview).
- **Multimodal plus thinking in one main model.** `kimi-k2.5` combines text+vision with toggleable thinking/non-thinking modes. [Docs overview](https://platform.moonshot.ai/docs/overview), [Use the Kimi vision model](https://platform.moonshot.ai/docs/guide/use-kimi-vision-model).
- **Open-weight lineage still matters.** Moonshot continues to publish major Kimi releases through its [Hugging Face org](https://huggingface.co/moonshotai).
- **Competitive cost profile.** The current platform pricing remains aggressive relative to Western frontier APIs. [Pricing](https://platform.moonshot.ai/docs/pricing/chat).

## Weaknesses (cited)

- **Documentation is fragmented.** Core facts are split across homepage cards, overview pages, pricing docs, and bilingual guides.
- **Western tooling support still lags.** OpenAI-compatible endpoints help, but ecosystem defaults still skew toward OpenAI/Anthropic/Google.
- **Preview-heavy naming.** Moonshot keeps several preview and turbo names in circulation, which makes production pinning more important.

## Best-fit tasks

- Agentic coding and tool-use workflows
- Cost-sensitive long-context tasks
- Chinese/English cross-lingual work
- Teams that care about both hosted API access and open-weight releases

## Provider-specific quirks

- **OpenAI-compatible API path is still the default integration story.**
- **Thinking support is model-specific.** `kimi-k2.5` can toggle thinking; `kimi-k2-thinking` forces it on.
- **Vision support is no longer a separate special-case model.** The latest general-purpose K2.5 path handles text and visual input natively.

## Official docs

- [Moonshot AI platform](https://platform.moonshot.ai/)
- [Docs overview](https://platform.moonshot.ai/docs/overview)
- [Use the Kimi vision model](https://platform.moonshot.ai/docs/guide/use-kimi-vision-model)
- [Pricing](https://platform.moonshot.ai/docs/pricing/chat)
- [Moonshot on Hugging Face](https://huggingface.co/moonshotai)

## Status

`[provider-doc]`. This page now reflects Moonshot's current K2.6 / K2.5 / K2-thinking-era lineup rather than the older K2-only summary.
