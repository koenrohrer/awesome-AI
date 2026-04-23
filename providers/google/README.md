# Google `[provider-doc]`

*Last reviewed: 2026-04-23. Google's provider story now has three distinct tracks: hosted Gemini API models, open-weight Gemma models, and product surfaces such as Antigravity and Stitch. Verify model availability against the live [Gemini models page](https://ai.google.dev/gemini-api/docs/models), the [Gemini 3 guide](https://ai.google.dev/gemini-api/docs/gemini-3), and [Gemma docs](https://ai.google.dev/gemma/docs).*

## Product surfaces

- **[Google Antigravity](antigravity.md)** — agentic development platform with editor, terminal, browser, and multi-agent manager workflows.
- **[Google Stitch](stitch.md)** — Google Labs design-generation surface for natural-language UI design workflows.

## Product surface tracker

| Surface | Repo coverage | Evidence |
|---|---|---|
| [Google Antigravity](antigravity.md) | Full primer page | `[provider-doc]` [Google Developers Blog](https://developers.googleblog.com/en/build-with-google-antigravity-our-new-agentic-development-platform/) |
| [Google Stitch](stitch.md) | Full primer page | `[provider-doc]` [Google Labs](https://labs.google/) |
| Google AI Studio Build mode | Docs only | `[provider-doc]` [Build mode docs](https://ai.google.dev/gemini-api/docs/aistudio-build-mode) |
| Gemini CLI | Docs only | `[provider-doc]` [official repo](https://github.com/google-gemini/gemini-cli) |
| Gemini Code Assist | Docs only | `[provider-doc]` [Google Cloud docs](https://cloud.google.com/gemini/docs/codeassist/overview) |
| NotebookLM | Docs only | `[provider-doc]` [NotebookLM Help](https://support.google.com/notebooklm/answer/16164461) |

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Gemini 3.1 Pro Preview | Current preview reasoning tier | 1M-token context, Gemini 3 thinking controls, agentic coding focus |
| Gemini 3 Flash preview line | Current fast Gemini 3 tier | 1M context, lower-latency Gemini 3 path |
| Gemini 3.1 Flash-Lite preview | Lowest-cost Gemini 3 tier | Preview high-throughput path listed on the live models page |
| Nano Banana Pro / Gemini 3 Pro Image | Image generation | Gemini 3 image-generation model with high-context visual workflows |
| Gemini 2.5 Pro | Stable thinking model | 1M-token context, mature reasoning/coding tier |
| Gemini 2.5 Flash | Stable balanced fast model | 1M context, thinking, strong price/perf |
| Gemini 2.5 Flash-Lite | Stable low-cost hosted Gemini tier | 1M context, high-throughput, cost-focused |
| Gemini 2.5 Live / TTS variants | Audio generation and real-time dialogue | Preview speech/live model surfaces |
| Gemma 3 | Open-weight multimodal line | 128K context, text+image input |
| Gemma 3n | On-device open model line | Multimodal, audio-capable, parameter-efficient device deployment |
| Gemma 4 | Open-weight family, edge → workstation | `E2B`/`E4B` at 128K; `26B A4B` MoE and `31B` dense at 256K |

## Model pages

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
- [Gemma models overview](https://ai.google.dev/gemma/docs)
- [Gemma 3 model card](https://ai.google.dev/gemma/docs/core/model_card_3)
- [Gemma 3n model card](https://ai.google.dev/gemma/docs/gemma-3n/model_card)
- [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)

Google does not currently publish a public Gemini “system card” hub in the same vendor pattern as Anthropic/OpenAI. For Gemini, the models page and developer guides are the practical primary sources. For Gemma, the model cards are the closest equivalent.

## Strengths (cited)

- **Very long context.** Gemini 3 preview models and Gemini 2.5 Pro, Flash, and Flash-Lite publish roughly 1M-token input limits in Google's current docs. See the [Gemini 3 guide](https://ai.google.dev/gemini-api/docs/gemini-3) and [models page](https://ai.google.dev/gemini-api/docs/models).
- **Native multimodality.** Gemini accepts text, images, audio, video, and PDFs in the same family. See the [models page](https://ai.google.dev/gemini-api/docs/models) and [vision docs](https://ai.google.dev/gemini-api/docs/vision).
- **Explicit caching and grounding surfaces.** Gemini exposes caching, code execution, file search, search grounding, and Google Maps grounding on the hosted API models. [Models page](https://ai.google.dev/gemini-api/docs/models).
- **Strong open-weight companion family.** Gemma 3 and 3n give Google an open model path instead of forcing everything through the hosted Gemini API. [Gemma overview](https://ai.google.dev/gemma/docs).

## Weaknesses (cited)

- **Two-track product complexity.** Gemini and Gemma share branding lineage but have different deployment assumptions, APIs, and documentation hubs.
- **Cache is explicit, not automatic.** You manage lifecycle yourself, unlike OpenAI's automatic caching path. See [caching docs](https://ai.google.dev/gemini-api/docs/caching).
- **Tool/function-calling ergonomics differ from OpenAI/Anthropic.** Cross-provider agent code still needs adaptation. [Function calling docs](https://ai.google.dev/gemini-api/docs/function-calling).

## Best-fit tasks

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

`[provider-doc]`. Gemini 3 preview, Gemini 2.5 stable, and Gemma lines are all represented. Product surfaces now include Antigravity and Stitch; see the per-model and product pages for deployment specifics.
