# Provider Model Directory `[provider-doc]`

*Last reviewed: 2026-08-16. This date-stamped catalog is a non-ranking map of documented model surfaces. Provider pages and their linked live docs remain the source of record.*

## Scope

- **Full page** means the repo has a dedicated `providers/<provider>/models/*.md` page.
- **Docs only** means the provider documents the model, but the repo has not expanded it into a dedicated page yet.
- Lifecycle and delivery labels distinguish generally available, preview, limited-access, product-only, API, hosted, open-weight, deprecated, and retired releases.
- Every row uses official provider docs or official provider release posts as evidence.
- Model comparisons should use tables by default. Benchmark rows belong here only when they name the benchmark, source/date, and methodology; avoid flattening incompatible benchmark runs into a ranking.

## Anthropic

| Model line | Repo coverage | Evidence |
|---|---|---|
| [Claude Fable 5](../anthropic/models/claude-fable-5.md) | Full page; generally available | `[provider-doc]` [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Mythos 5](../anthropic/models/claude-mythos-5.md) | Full page; limited Project Glasswing access | `[provider-doc]` [Fable and Mythos API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5) |
| [Claude Opus 5](../anthropic/models/claude-opus-5.md) | Full page; generally available | `[provider-doc]` [What's new in Claude Opus 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-opus-5) |
| [Claude Sonnet 5](../anthropic/models/claude-sonnet-5.md) | Full page; generally available | `[provider-doc]` [What's new in Claude Sonnet 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-sonnet-5) |
| Claude Opus 4.8 | Docs only; active | `[provider-doc]` [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Opus 4.7](../anthropic/models/claude-opus-4-7.md) | Full page | `[provider-doc]` [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Opus 4.6](../anthropic/models/claude-opus-4-6.md) | Full page | `[provider-doc]` [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Opus 4.5](../anthropic/models/claude-opus-4-5.md) | Full page | `[provider-doc]` [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Sonnet 4.6](../anthropic/models/claude-sonnet-4-6.md) | Full page | `[provider-doc]` [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Sonnet 4.5](../anthropic/models/claude-sonnet-4-5.md) | Full page | `[provider-doc]` [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |
| [Claude Haiku 4.5](../anthropic/models/claude-haiku-4-5.md) | Full page | `[provider-doc]` [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) |

## OpenAI

| Model line | Repo coverage | Evidence |
|---|---|---|
| [GPT-5.6 Sol](../openai/models/gpt-5-6-sol.md) | Full page; generally available | `[provider-doc]` [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol) |
| [GPT-5.6 Terra](../openai/models/gpt-5-6-terra.md) | Full page; generally available | `[provider-doc]` [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-terra) |
| [GPT-5.6 Luna](../openai/models/gpt-5-6-luna.md) | Full page; generally available | `[provider-doc]` [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-luna) |
| [GPT-5.5](../openai/models/gpt-5-5.md) | Full page; active API model | `[provider-doc]` [Model page](https://developers.openai.com/api/docs/models/gpt-5.5) |
| [GPT-5.5 Pro](../openai/models/gpt-5-5-pro.md) | Full page; active API model | `[provider-doc]` [Model page](https://developers.openai.com/api/docs/models/gpt-5.5-pro) |
| [GPT-5.4](../openai/models/gpt-5-4.md) | Full page | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| [GPT-5.4 Pro](../openai/models/gpt-5-4-pro.md) | Full page | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| [GPT-5.4 mini](../openai/models/gpt-5-4-mini.md) | Full page | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| [GPT-5.4 nano](../openai/models/gpt-5-4-nano.md) | Full page | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| [GPT-5.6 Cyber](../openai/models/gpt-5-6-cyber.md) | Full page; access-gated cybersecurity tier | `[provider-doc]` [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-cyber) |
| `daybreak-red-latest`, `daybreak-blue-latest` | Docs only; aliases, not distinct models | `[provider-doc]` [Daybreak Red](https://developers.openai.com/api/docs/models/daybreak-red-latest), [Daybreak Blue](https://developers.openai.com/api/docs/models/daybreak-blue-latest) |
| [GPT-5.3 Instant](../openai/models/gpt-5-3-instant.md) | Full page; corrected — not an API model ID. The `gpt-5.3-chat-latest` surface shut down 2026-08-10 | `[provider-doc]` [Deprecations](https://developers.openai.com/api/docs/deprecations) |
| [GPT-5.3-Codex](../openai/models/gpt-5-3-codex.md) | Full page | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| [GPT-5-Codex](../openai/models/gpt-5-codex.md) | Full page; **retired 2026-07-23** | `[provider-doc]` [Deprecations](https://developers.openai.com/api/docs/deprecations) |
| [codex-mini-latest](../openai/models/codex-mini-latest.md) | Full page; **retired 2026-02-12** | `[provider-doc]` [Deprecations](https://developers.openai.com/api/docs/deprecations) |
| `gpt-realtime-2.1`, `gpt-realtime-2.1-mini`, `gpt-realtime-2`, `gpt-realtime-translate`, `gpt-realtime-1.5` | Docs only | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| `gpt-transcribe`, `gpt-live-transcribe`, `gpt-realtime-whisper`, `gpt-4o-transcribe`, `gpt-4o-mini-transcribe` | Docs only | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |
| `gpt-realtime-mini` | Docs only; deprecated | `[provider-doc]` [Deprecations](https://developers.openai.com/api/docs/deprecations) |
| GPT Image 2, `gpt-4o-mini-tts`, embeddings, moderation | Docs only | `[provider-doc]` [OpenAI models](https://developers.openai.com/api/docs/models) |

## Google

| Model line | Repo coverage | Evidence |
|---|---|---|
| [Gemini 3.7 Flash](../google/models/gemini-3-7-flash.md) | Full page; stable, current top Flash tier | `[provider-doc]` [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.7-flash) |
| [Gemini 3.6 Flash](../google/models/gemini-3-6-flash.md) | Full page; stable | `[provider-doc]` [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.6-flash) |
| Gemini 3.5 Flash, Gemini 3.1 Flash-Lite | Docs only; stable | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| [Gemini 3.5 Flash-Lite](../google/models/gemini-3-5-flash-lite.md) | Full page; stable | `[provider-doc]` [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.5-flash-lite) |
| [Gemini Omni Flash](../google/models/gemini-omni-flash.md) | Full page; preview | `[provider-doc]` [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-omni-flash) |
| [Gemini Computer Use](../google/gemini-computer-use.md) | Full capability page; preview tool, not a model ID | `[provider-doc]` [Computer Use docs](https://ai.google.dev/gemini-api/docs/computer-use) |
| [Gemini 3.1 Pro Preview](../google/models/gemini-3-1-pro-preview.md) | Full page | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models), [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3) |
| [Gemini 3 Flash Preview](../google/models/gemini-3-flash-preview.md) | Full page | `[provider-doc]` [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3), [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| [Nano Banana Pro / Gemini 3 Pro Image](../google/models/nano-banana-pro.md) | Full page | `[provider-doc]` [Nano Banana docs](https://ai.google.dev/gemini-api/docs/nanobanana), [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| Nano Banana 2, Nano Banana 2 Lite, Gemini 3.1 Flash Live, Gemini 3.1 Flash TTS, Gemini 3.5 Live Translate | Docs only | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| [Gemini 2.5 Pro](../google/models/gemini-2-5-pro.md) | Full page | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| [Gemini 2.5 Flash](../google/models/gemini-2-5-flash.md) | Full page | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| [Gemini 2.5 Flash-Lite](../google/models/gemini-2-5-flash-lite.md) | Full page | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| Gemini 2.5 Flash Live, Gemini 2.5 Flash TTS, Gemini 2.5 Pro TTS | Docs only | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| Veo 3.1, Veo 3.1 Lite, Lyria 3, Lyria RealTime | Docs only | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| Imagen 4 | Docs only; deprecated upstream | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| Gemini Embedding 2, Gemini Embedding, Gemini Robotics-ER | Docs only | `[provider-doc]` [Gemini models](https://ai.google.dev/gemini-api/docs/models) |
| [Gemma 4](../google/models/gemma-4.md), [Gemma 3](../google/models/gemma-3.md), [Gemma 3n](../google/models/gemma-3n.md) | Full pages | `[provider-doc]` [Gemma docs](https://ai.google.dev/gemma/docs) |

## DeepSeek

| Model line | Repo coverage | Evidence |
|---|---|---|
| [DeepSeek-V4-Pro](../deepseek/models/deepseek-v4-pro.md) | Full page; generally available 2026-08-13 as `DeepSeek-V4-Pro-0813` | `[provider-doc]` [GA release note](https://api-docs.deepseek.com/news/news260813), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/) |
| [DeepSeek-V4-Flash-0731](../deepseek/models/deepseek-v4-flash.md) | Full page; hosted public beta | `[provider-doc]` [DeepSeek updates](https://api-docs.deepseek.com/updates/), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/) |
| [deepseek-chat](../deepseek/models/deepseek-chat.md) | Full page; retired alias | `[provider-doc]` [DeepSeek V4 release](https://api-docs.deepseek.com/news/news260424/) |
| [deepseek-reasoner](../deepseek/models/deepseek-reasoner.md) | Full page; retired alias | `[provider-doc]` [DeepSeek V4 release](https://api-docs.deepseek.com/news/news260424/) |
| [DeepSeek-V3.2](../deepseek/models/deepseek-v3-2.md) | Full page | `[provider-doc]` [DeepSeek change log](https://api-docs.deepseek.com/updates/) |
| [DeepSeek-R1](../deepseek/models/deepseek-r1.md) | Full page | `[provider-doc]` [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai) |

## Moonshot AI / Kimi

| Model line | Repo coverage | Evidence |
|---|---|---|
| [Kimi K3](../moonshot/models/kimi-k3.md) | Full page; hosted API and open weights | `[provider-doc]` [Kimi K3 repository](https://github.com/MoonshotAI/Kimi-K3), [Kimi API Platform](https://platform.kimi.ai/) |
| [Kimi K2.7 Code](../moonshot/models/kimi-k2-7-code.md) | Full page; hosted API and open weights | `[provider-doc]` [K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code), [weights](https://huggingface.co/moonshotai/Kimi-K2.7-Code) |
| [Kimi K2.6](../moonshot/models/kimi-k2-6.md) | Full page | `[provider-doc]` [Kimi API docs](https://platform.kimi.ai/docs/overview) |
| [Kimi K2.5](../moonshot/models/kimi-k2-5.md) | Full page; closed to new registrations, platform sunset documented | `[provider-doc]` [Kimi models](https://platform.kimi.ai/docs/models) |
| [Kimi K2 Thinking](../moonshot/models/kimi-k2-thinking.md) | Full page; deprecation record | `[provider-doc]` [Kimi models](https://platform.kimi.ai/docs/models) |
| `kimi-k2`, `kimi-k2-turbo-preview`, `kimi-k2-thinking-turbo`, `kimi-latest`, `moonshot-v1-*` | Docs only; **the `kimi-k2` series was discontinued 2026-05-25** | `[provider-doc]` [Kimi models](https://platform.kimi.ai/docs/models) |

## MiniMax

| Model line | Repo coverage | Evidence |
|---|---|---|
| [MiniMax M3](../minimax/models/minimax-m3.md) | Full page; hosted API and open weights | `[provider-doc]` [Model page](https://www.minimax.io/models/text/m3), [repository](https://github.com/MiniMax-AI/MiniMax-M3) |
| [MiniMax M2.7](../minimax/models/minimax-m2-7.md) | Full page | `[provider-doc]` [MiniMax API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| MiniMax M2.7-highspeed | Docs only | `[provider-doc]` [MiniMax API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| [MiniMax M2.5](../minimax/models/minimax-m2-5.md) | Full page | `[provider-doc]` [MiniMax API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| [MiniMax M2.5-highspeed](../minimax/models/minimax-m2-5-highspeed.md) | Full page | `[provider-doc]` [MiniMax API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| [MiniMax M2.1](../minimax/models/minimax-m2-1.md) | Full page | `[provider-doc]` [MiniMax API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| MiniMax M2.1-highspeed, MiniMax M2 | Docs only | `[provider-doc]` [MiniMax API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| [MiniMax M1](../minimax/models/minimax-m1.md) | Full page | `[provider-doc]` [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1) |
| [MiniMax H3](../minimax/models/minimax-h3.md) | Full page; multimodal video generation | `[provider-doc]` [Video generation API](https://platform.minimax.io/docs/api-reference/video-generation-v2-create) |
| `speech-2.8-hd`, `speech-2.8-turbo`, `speech-2.6-hd`, `speech-2.6-turbo` | Docs only | `[provider-doc]` [HTTP T2A API](https://platform.minimax.io/docs/api-reference/speech-t2a-http) |
| `music-3.0`, `music-2.6`, `music-cover` | Docs only | `[provider-doc]` [Music Generation API](https://platform.minimax.io/docs/api-reference/music-generation) |
| `image-01` | Docs only | `[provider-doc]` [Text to Image](https://platform.minimax.io/docs/api-reference/image-generation-t2i) |

## Other seeded providers

| Provider | Repo coverage | Evidence |
|---|---|---|
| [Grok 4.6](../xai/models/grok-4-6.md) | Full page; current model for code and chat | `[provider-doc]` [Model page](https://docs.x.ai/developers/models/grok-4.6) |
| [Grok 4.5](../xai/models/grok-4-5.md) | Full page | `[provider-doc]` [Model page](https://docs.x.ai/developers/models/grok-4.5) |
| [Grok 4.3](../xai/models/grok-4-3.md) | Full page; 1M context | `[provider-doc]` [Model page](https://docs.x.ai/developers/models/grok-4.3) |
| [Grok 4.20 line](../xai/models/grok-4-20.md) | Full page covering the reasoning, non-reasoning, and multi-agent variants | `[provider-doc]` [xAI models](https://docs.x.ai/developers/models) |
| [grok-build-0.1](../xai/models/grok-build-0-1.md) | Full page; model behind the Grok Build agent | `[provider-doc]` [Model page](https://docs.x.ai/developers/models/grok-build-0.1) |
| Grok Imagine image and video, Grok voice models | Docs only | `[provider-doc]` [xAI models](https://docs.x.ai/developers/models) |
| [xAI Grok models and products](../xai/) | Grok Build product surface and retained migration pages | `[provider-doc]` [xAI models](https://docs.x.ai/developers/models), [Grok Build](https://docs.x.ai/build/overview) |
| [Muse Glimmer 30B](../meta/models/muse-glimmer-30b.md) | Full page; open weights under Apache 2.0 | `[provider-doc]` [Model card](https://huggingface.co/meta-models/Muse-Glimmer-30B), [launch post](https://developer.meta.com/ai/resources/blog/build-with-muse-glimmer/) |
| [Muse Code](../meta/muse-code.md) | Full product page; terminal coding agent, beta | `[provider-doc]` [Muse Code](https://developer.meta.com/ai/products/muse-code/) |
| [Meta models and products](../meta/) | Full pages for Llama 4, guard models, Muse Spark 1.2 API, and Muse media products | `[provider-doc]` [Meta Llama](https://huggingface.co/meta-llama), [Muse Spark](https://developer.meta.com/ai/models/muse-spark/) |
| [Qwen3.8-2.4T-A95B](../alibaba/models/qwen3-8-2-4t-a95b.md) | Full page; open weights, Max-class | `[provider-doc]` [Model card](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B), [release post](https://qwen.ai/blog?id=qwen3.8) |
| [Qwen3.8-27B](../alibaba/models/qwen3-8-27b.md) | Full page; open weights, Apache 2.0 | `[provider-doc]` [Model card](https://huggingface.co/Qwen/Qwen3.8-27B), [release post](https://qwen.ai/blog?id=qwen3.8) |
| Qwen 3.8 Max | Docs only; hosted production model | `[provider-doc]` [Model Studio catalog](https://help.aliyun.com/en/model-studio/text-generation-model/) |
| Qwen 3.7 Plus | Docs only; current hosted model | `[provider-doc]` [Model Studio catalog](https://help.aliyun.com/en/model-studio/text-generation-model/) |
| Qwen 3.7 Max | Docs only; supported legacy model | `[provider-doc]` [Model Studio catalog](https://help.aliyun.com/en/model-studio/text-generation-model/) |
| Mistral OCR 4.1 | Docs only; current hosted document service. `mistral-ocr-latest` and `mistral-ocr-4` both repointed here on 2026-07-16 | `[provider-doc]` [Model card](https://docs.mistral.ai/models/model-cards/ocr-4-1), [changelog](https://docs.mistral.ai/resources/changelogs) |
| Mistral OCR 4 | Docs only; superseded, still callable by pinned ID | `[provider-doc]` [Model card](https://docs.mistral.ai/models/model-cards/ocr-4-0) |
| Leanstral 1.5 | Docs only; Labs API and open weights | `[provider-doc]` [Model card](https://docs.mistral.ai/models/model-cards/leanstral-1-5) |
| Robostral Navigate | Docs only; research release | `[provider-doc]` [Release post](https://mistral.ai/news/robostral-navigate/) |
| GLM-5.2 | Docs only; hosted API model | `[provider-doc]` [Z.ai model page](https://docs.z.ai/guides/llm/glm-5.2) |
