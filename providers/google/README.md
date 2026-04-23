# Google `[provider-doc]`

*Last reviewed: 2026-04-23. Google's provider story now has two distinct tracks: hosted Gemini API models and open-weight Gemma models. Verify both against the live [Gemini models page](https://ai.google.dev/gemini-api/docs/models) and [Gemma docs](https://ai.google.dev/gemma/docs).*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Gemini 2.5 Pro | Flagship thinking model | 1M-token context, strongest reasoning/coding tier |
| Gemini 2.5 Flash | Balanced fast model | 1M context, thinking, strong price/perf |
| Gemini 2.5 Flash-Lite | Lowest-cost hosted Gemini tier | 1M context, high-throughput, cost-focused |
| Gemini 2.5 Pro TTS (preview) | Audio generation | Text-to-speech preview variant |
| Gemma 3 | Open-weight multimodal line | 128K context, text+image input |
| Gemma 3n | On-device open model line | Multimodal, audio-capable, parameter-efficient device deployment |
| Gemma 4 | Open-weight family, edge → workstation | `E2B`/`E4B` at 128K; `26B A4B` MoE and `31B` dense at 256K |

## Model pages

- [Gemini 2.5 Pro](models/gemini-2-5-pro.md)
- [Gemini 2.5 Flash](models/gemini-2-5-flash.md)
- [Gemini 2.5 Flash-Lite](models/gemini-2-5-flash-lite.md)
- [Gemma 3](models/gemma-3.md)
- [Gemma 3n](models/gemma-3n.md)
- [Gemma 4](models/gemma-4.md)

## Model cards and docs

- [Gemini models page](https://ai.google.dev/gemini-api/docs/models)
- [Gemma models overview](https://ai.google.dev/gemma/docs)
- [Gemma 3 model card](https://ai.google.dev/gemma/docs/core/model_card_3)
- [Gemma 3n model card](https://ai.google.dev/gemma/docs/gemma-3n/model_card)
- [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)

Google does not currently publish a public Gemini “system card” hub in the same vendor pattern as Anthropic/OpenAI. For Gemini, the model page and launch documentation are the practical primary sources. For Gemma, the model cards are the closest equivalent.

## Strengths (cited)

- **Very long context.** Gemini 2.5 Pro, Flash, and Flash-Lite all publish 1,048,576-token input limits on the [models page](https://ai.google.dev/gemini-api/docs/models).
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
- [Long context](https://ai.google.dev/gemini-api/docs/long-context)
- [Thinking](https://ai.google.dev/gemini-api/docs/thinking)
- [Function calling](https://ai.google.dev/gemini-api/docs/function-calling)
- [Vision and video](https://ai.google.dev/gemini-api/docs/vision)
- [Gemma overview](https://ai.google.dev/gemma/docs)
- [Gemma 3 overview](https://ai.google.dev/gemma/docs/core)
- [Gemma 3n overview](https://ai.google.dev/gemma/docs/gemma-3n)
- [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/)
- [Pricing](https://ai.google.dev/pricing)

## Status

`[provider-doc]`. Gemini and Gemma families are both current. Gemma 4 launched April 2026 alongside the continued Gemma 3 / 3n lines; see the per-model pages for deployment specifics.
