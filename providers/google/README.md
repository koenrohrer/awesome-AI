# Google `[provider-doc]`

*Last reviewed: 2026-08-16. Google's provider story has three tracks: hosted Gemini API models, open-weight Gemma models, and product surfaces such as Antigravity and Stitch. The catalog below is date-stamped, not a ranking; verify availability against the live [Gemini models page](https://ai.google.dev/gemini-api/docs/models).*

## Product surfaces

- **[Google Antigravity](antigravity.md)** — agentic development platform with editor, terminal, browser, and multi-agent manager workflows.
- **[Google Stitch](stitch.md)** — Google Labs design-generation surface for natural-language UI design workflows.
- **[Gemini Computer Use](gemini-computer-use.md)** — preview browser, mobile, and desktop action-loop capability.

## Product surface tracker

| Surface | Repo coverage | Evidence |
|---|---|---|
| [Google Antigravity](antigravity.md) | Full primer page | `[provider-doc]` [Google Developers Blog](https://developers.googleblog.com/en/build-with-google-antigravity-our-new-agentic-development-platform/) |
| [Google Stitch](stitch.md) | Full primer page | `[provider-doc]` [Google Labs](https://labs.google/) |
| [Gemini Computer Use](gemini-computer-use.md) | Full capability page; preview | `[provider-doc]` [Computer Use guide](https://ai.google.dev/gemini-api/docs/computer-use) |
| Google AI Studio Build mode | Docs only | `[provider-doc]` [Build mode docs](https://ai.google.dev/gemini-api/docs/aistudio-build-mode) |
| Gemini CLI | Docs only | `[provider-doc]` [official repo](https://github.com/google-gemini/gemini-cli) |
| Gemini Code Assist | Docs only | `[provider-doc]` [Google Cloud docs](https://cloud.google.com/gemini/docs/codeassist/overview) |
| NotebookLM | Docs only | `[provider-doc]` [NotebookLM Help](https://support.google.com/notebooklm/answer/16164461) |

## Current model lines

Status and model IDs below come from the [Gemini models page](https://ai.google.dev/gemini-api/docs/models) and the linked per-model pages, read on the review date. "Docs only" means the repo tracks the model here and points at Google's docs instead of carrying a dedicated page.

### Gemini 3 text models

| Model | Model ID | Status | Repo coverage | Documented facts |
|---|---|---|---|---|
| [Gemini 3.7 Flash](models/gemini-3-7-flash.md) | `gemini-3.7-flash` | Stable | Full page | 1,048,576 in / 65,536 out; text, image, video, audio, PDF in; August 2026 update |
| [Gemini 3.6 Flash](models/gemini-3-6-flash.md) | `gemini-3.6-flash` | Stable | Full page | Same limits and modalities; July 2026 update; recommended model in the Computer Use guide |
| Gemini 3.5 Flash | `gemini-3.5-flash` | Stable | Docs only | 1,048,576 in / 65,536 out; $1.50 in / $9.00 out per 1M tokens. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.5-flash) |
| [Gemini 3.5 Flash-Lite](models/gemini-3-5-flash-lite.md) | `gemini-3.5-flash-lite` | Stable | Full page | 1,048,576 in / 65,536 out; $0.30 in / $2.50 out per 1M tokens |
| Gemini 3.1 Flash-Lite | `gemini-3.1-flash-lite` | Stable | Docs only | 1,048,576 in / 65,536 out; $0.25 in text/image/video, $0.50 in audio, $1.50 out per 1M tokens; supports the `minimal` thinking level. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-flash-lite) |
| [Gemini 3.1 Pro Preview](models/gemini-3-1-pro-preview.md) | `gemini-3.1-pro-preview` | Preview | Full page | Gemini 3 thinking controls, agentic coding focus |
| [Gemini 3 Flash Preview](models/gemini-3-flash-preview.md) | `gemini-3-flash-preview` | Preview | Full page | Lower-latency Gemini 3 path; Computer Use capable |

### Gemini 3 image, audio, and video models

| Model | Model ID | Status | Repo coverage | Documented facts |
|---|---|---|---|---|
| [Nano Banana Pro / Gemini 3 Pro Image](models/nano-banana-pro.md) | `gemini-3-pro-image` | Stable | Full page | Gemini 3 image generation with high-context visual workflows |
| Nano Banana 2 | `gemini-3.1-flash-image` | Stable | Docs only | Text and image/PDF in, image and text out; 131,072 in / 32,768 out. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-flash-image) |
| Nano Banana 2 Lite | `gemini-3.1-flash-lite-image` | Stable | Docs only | Text and image in, image and text out; 65,536 in / 4,096 out. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-flash-lite-image) |
| Gemini 3.5 Live Translate | `gemini-3.5-live-translate-preview` | Preview | Docs only | Speech in, translated speech plus transcript out; 131,072 in / 65,536 out. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.5-live-translate-preview) |
| Gemini 3.1 Flash Live | `gemini-3.1-flash-live-preview` | Preview | Docs only | Text, image, audio, video in; text and audio out; 131,072 in / 65,536 out. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-flash-live-preview) |
| Gemini 3.1 Flash TTS | `gemini-3.1-flash-tts-preview` | Preview | Docs only | Text in, audio out; 8,192 in / 16,384 out. [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.1-flash-tts-preview) |
| [Gemini Omni Flash](models/gemini-omni-flash.md) | `gemini-omni-flash` | Preview | Full page | Conversational 3–10 second 720p video workflows |

### Gemini 2.5 and tool models

| Model | Model ID | Status | Repo coverage | Documented facts |
|---|---|---|---|---|
| [Gemini 2.5 Pro](models/gemini-2-5-pro.md) | `gemini-2.5-pro` | Stable | Full page | 1M-token context, mature reasoning/coding tier |
| [Gemini 2.5 Flash](models/gemini-2-5-flash.md) | `gemini-2.5-flash` | Stable | Full page | 1M context, thinking |
| [Gemini 2.5 Flash-Lite](models/gemini-2-5-flash-lite.md) | `gemini-2.5-flash-lite` | Stable | Full page | 1M context, high-throughput, cost-focused |
| Gemini 2.5 Live and TTS variants | `gemini-2.5-flash-native-audio-preview-12-2025`, `gemini-2.5-flash-preview-tts`, `gemini-2.5-pro-preview-tts` | Stable | Docs only | Real-time dialogue and speech generation surfaces |
| [Gemini Computer Use](gemini-computer-use.md) | Tool on Gemini 3.x models, plus legacy `gemini-2.5-computer-use-preview-10-2025` | Preview | Full capability page | Browser, mobile, and desktop action loops |
| Gemini Embedding | `gemini-embedding-001`, `gemini-embedding-2-preview` | Stable and preview | Docs only | Embedding models listed on the models page |

### Gemma open-weight models

| Model | Status | Repo coverage | Documented facts |
|---|---|---|---|
| [Gemma 3](models/gemma-3.md) | Released | Full page | 128K context, text+image input |
| [Gemma 3n](models/gemma-3n.md) | Released | Full page | Multimodal, audio-capable, parameter-efficient device deployment |
| [Gemma 4](models/gemma-4.md) | Released | Full page | `E2B`/`E4B` at 128K; `26B A4B` MoE and `31B` dense at 256K |

## Model pages

- [Gemini 3.7 Flash](models/gemini-3-7-flash.md)
- [Gemini 3.6 Flash](models/gemini-3-6-flash.md)
- [Gemini 3.5 Flash-Lite](models/gemini-3-5-flash-lite.md)
- [Gemini Omni Flash](models/gemini-omni-flash.md)
- [Gemini 3.1 Pro Preview](models/gemini-3-1-pro-preview.md)
- [Gemini 3 Flash Preview](models/gemini-3-flash-preview.md)
- [Nano Banana Pro / Gemini 3 Pro Image](models/nano-banana-pro.md)
- [Gemini 2.5 Pro](models/gemini-2-5-pro.md)
- [Gemini 2.5 Flash](models/gemini-2-5-flash.md)
- [Gemini 2.5 Flash-Lite](models/gemini-2-5-flash-lite.md)
- [Gemma 3](models/gemma-3.md)
- [Gemma 3n](models/gemma-3n.md)
- [Gemma 4](models/gemma-4.md)

## Model cards and docs

- [Gemini models page](https://ai.google.dev/gemini-api/docs/models)
- [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3)
- [Computer Use](https://ai.google.dev/gemini-api/docs/computer-use)
- [Gemma models overview](https://ai.google.dev/gemma/docs)
- [Gemma 3 model card](https://ai.google.dev/gemma/docs/core/model_card_3)
- [Gemma 3n model card](https://ai.google.dev/gemma/docs/gemma-3n/model_card)
- [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)

Google does not currently publish a public Gemini “system card” hub in the same vendor pattern as Anthropic/OpenAI. For Gemini, the models page and developer guides are the practical primary sources. For Gemma, the model cards are the closest equivalent.

## Strengths (cited)

- **Very long context.** Gemini 3.7 Flash, 3.6 Flash, 3.5 Flash, 3.5 Flash-Lite, and 3.1 Flash-Lite each publish a 1,048,576-token input limit on their model pages, as do the Gemini 2.5 text models. See the [models page](https://ai.google.dev/gemini-api/docs/models). The image, live, and TTS variants do not: those publish 8,192 to 131,072 input tokens.
- **Native multimodality.** Gemini accepts text, images, audio, video, and PDFs in the same family. See the [models page](https://ai.google.dev/gemini-api/docs/models) and [vision docs](https://ai.google.dev/gemini-api/docs/vision).
- **Explicit caching and grounding surfaces.** Gemini exposes caching, code execution, file search, search grounding, and Google Maps grounding on the hosted API models. [Models page](https://ai.google.dev/gemini-api/docs/models).
- **Strong open-weight companion family.** Gemma 3 and 3n give Google an open model path instead of forcing everything through the hosted Gemini API. [Gemma overview](https://ai.google.dev/gemma/docs).

## Weaknesses (cited)

- **Two-track product complexity.** Gemini and Gemma share branding lineage but have different deployment assumptions, APIs, and documentation hubs.
- **Cache is explicit, not automatic.** You manage lifecycle yourself, unlike OpenAI's automatic caching path. See [caching docs](https://ai.google.dev/gemini-api/docs/caching).
- **Tool/function-calling ergonomics differ from OpenAI/Anthropic.** Cross-provider agent code still needs adaptation. [Function calling docs](https://ai.google.dev/gemini-api/docs/function-calling).

## Fits

- Very long document or code analysis where 1M context genuinely matters
- Multimodal-first workflows combining audio, video, and text
- Teams that want a hosted frontier API plus a first-party open-weight line
- On-device and edge deployment via Gemma 3n

## Provider-specific quirks

- **AI Studio vs Vertex AI.** Same underlying Gemini family, different operational surface. [AI Studio](https://aistudio.google.com/), [Vertex AI](https://cloud.google.com/vertex-ai).
- **Gemma is not Gemini.** Gemma docs live separately and describe open weights, local deployment, and model-card style safety notes.
- **Gemma 3 and Gemma 4 coexist.** Gemma 4 launched in April 2026 as a separate open-weight line; Gemma 3 and 3n remain documented and deployable. Pick the version that matches the runtime/device you're targeting.

## Official docs

- [Gemini API docs](https://ai.google.dev/gemini-api/docs)
- [Gemini models](https://ai.google.dev/gemini-api/docs/models)
- [Gemini 3 guide](https://ai.google.dev/gemini-api/docs/gemini-3)
- [Long context](https://ai.google.dev/gemini-api/docs/long-context)
- [Thinking](https://ai.google.dev/gemini-api/docs/thinking)
- [Function calling](https://ai.google.dev/gemini-api/docs/function-calling)
- [Vision and video](https://ai.google.dev/gemini-api/docs/vision)
- [Gemma overview](https://ai.google.dev/gemma/docs)
- [Gemma 3 overview](https://ai.google.dev/gemma/docs/core)
- [Gemma 3n overview](https://ai.google.dev/gemma/docs/gemma-3n)
- [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/)
- [Google Antigravity](https://antigravity.google/)
- [Google Labs](https://labs.google/)
- [Pricing](https://ai.google.dev/pricing)

## Status

`[provider-doc]`. Every Gemini model ID listed on the [models page](https://ai.google.dev/gemini-api/docs/models) on 2026-08-16 is tracked above as either a full page or a docs-only row, except the Deep Research, Antigravity Agent, and Robotics ER preview models, which are agent and robotics surfaces rather than general API models and are not covered yet.

Coverage rule used here: general-purpose text tiers earn a dedicated page; image, live, translate, TTS, and embedding variants get a docs-only row, matching how the repo already handles the Gemini 2.5 live and TTS models.

Two upstream inconsistencies are worth noting. The [Computer Use guide](https://ai.google.dev/gemini-api/docs/computer-use) still recommends `gemini-3.6-flash` and does not list `gemini-3.7-flash`, although the 3.7 Flash model page marks computer use as a supported preview capability. The [Gemini 3 developer guide](https://ai.google.dev/gemini-api/docs/gemini-3) does not mention Gemini 3.7 Flash at all, so its thinking-level table covers 3.1 Pro, 3 Flash, and 3.1 Flash-Lite only.

“Gemini 3.5 Cyber” is omitted because no current official Google model or product source was found as of the review date.
