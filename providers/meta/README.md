# Meta `[provider-doc]`

*Last reviewed: 2026-08-16. Meta now has three distinct developer stories: Llama open weights, the hosted Meta Model API public preview for Muse Spark 1.2, and the Apache 2.0 open-weight release of Muse Glimmer 30B.*

## Current hosted and product surfaces

| Surface | Role | Availability |
|---|---|---|
| Meta Model API / Muse Spark 1.2 | Hosted multimodal reasoning, agent, and coding model | Public-preview developer API; 1.1 still served |
| Muse Code | Terminal coding agent running Muse Spark 1.2 | Beta |
| Muse Image | Image generation, editing, and composition | Available on named Meta product surfaces |
| Muse Video | Video generation with native audio | Preview; coming to creators and Meta AI |

## Product pages

- [Meta Model API and Muse Spark 1.2](muse-model-api.md)
- [Muse Code](muse-code.md)
- [Muse Image and Muse Video](muse-image-video.md)

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Muse Glimmer 30B | Open-weight multimodal model for local agents | ~29.6B dense with a perception encoder, 128K context, Apache 2.0 |
| Llama 4 Maverick | Higher-capacity open-weight multimodal model | 17B active / ~400B total, 1M context |
| Llama 4 Scout | Efficient open-weight multimodal model | 17B active / ~109B total, 10M context |
| Llama Guard 4 | Multimodal safety classifier | 12B safeguard model derived from the Llama 4 stack |
| Llama Prompt Guard 2 | Prompt-attack classifier | 86M and 22M prompt-injection / jailbreak filters |

Meta now publishes downloadable weights from two organizations on Hugging Face: `meta-llama` for Llama under the Llama Community License, and `meta-models` for Muse Glimmer under Apache 2.0. The official Llama 4 collection remains centered on Scout and Maverick. If someone asks for a broader Meta model lineup, first ask which distribution they need: downloadable weights, the hosted Muse API, or a Meta consumer product surface.

## Model pages

- [Muse Glimmer 30B](models/muse-glimmer-30b.md)
- [Llama 4 Scout](models/llama-4-scout.md)
- [Llama 4 Maverick](models/llama-4-maverick.md)
- [Llama Guard 4](models/llama-guard-4.md)
- [Llama Prompt Guard 2](models/llama-prompt-guard-2.md)

## Model cards

- [Meta Llama org on Hugging Face](https://huggingface.co/meta-llama)
- [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E)
- [Llama 4 Maverick model card](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E)
- [Llama Guard 4 model card](https://huggingface.co/meta-llama/Llama-Guard-4-12B)
- [Llama Prompt Guard 2 (22M) model card](https://huggingface.co/meta-llama/Llama-Prompt-Guard-2-22M)
- [Meta Inc. org on Hugging Face](https://huggingface.co/meta-models)
- [Muse Glimmer 30B model card](https://huggingface.co/meta-models/Muse-Glimmer-30B)

Meta does not publish Llama safety documentation under a “system card” hub comparable to Anthropic/OpenAI. The model cards and companion safeguard model cards are the operational primary sources.

## Strengths (cited)

- **Reference open-weight family.** Llama remains the default ecosystem baseline for open weights; tooling support across `llama.cpp`, `vLLM`, `Transformers`, and quantization stacks remains first-class.
- **Current Llama 4 release is natively multimodal.** Scout and Maverick both accept text and image input. [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E), [Llama 4 Maverick model card](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E).
- **Companion safeguard models are first-party.** Llama Guard 4 and Prompt Guard 2 give teams an official safety/filtering path rather than relying entirely on third parties.
- **Very long context on Scout.** The official model card lists 10M context for Scout, making it operationally distinct from Maverick. [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E).
- **First-party hosted model API.** The Meta Model API public preview gives developers hosted access to Muse Spark 1.2 and 1.1. [Meta Model API](https://developer.meta.com/ai/products/meta-model-api/).
- **An Apache 2.0 model in the Muse line.** Muse Glimmer 30B ships downloadable weights under Apache 2.0, with no revenue or user-count thresholds, alongside first-party GGUF, ExecuTorch, and speculative-decoding-drafter artifacts. [Muse Glimmer 30B model card](https://huggingface.co/meta-models/Muse-Glimmer-30B).

## Weaknesses (cited)

- **The Llama license is still not OSI open source.** The Llama Community License has commercial terms and threshold clauses; read it before shipping. Apache 2.0 covers Muse Glimmer, not Llama.
- **Hosting depends on the artifact.** Llama and Muse Glimmer weights are a self-hosted or third-party-hosted path; Muse Spark is only reachable through Meta's first-party public-preview API.
- **Muse open weights are one model, not the family.** Muse Glimmer 30B is downloadable under Apache 2.0, but Meta has not announced downloadable Muse Spark 1.1 or 1.2 weights, and the Meta Model API is still labelled public preview. [Muse Glimmer 30B model card](https://huggingface.co/meta-models/Muse-Glimmer-30B), [Meta Model API](https://developer.meta.com/ai/products/meta-model-api/).
- **Safety evidence lags the current release.** Meta's published evaluation report is stamped to Muse Spark 1.1 and its Safety & Preparedness Report covers Muse Spark as the model underlying Meta AI; as reviewed on 2026-08-16 neither is version-stamped to 1.2.
- **Prompt format and deployment details vary by model.** The right template and quantization path matter more than many teams expect.

## Fits

- Self-hosted or third-party-hosted multimodal inference
- Offline or always-on local agent loops on a single consumer GPU, via Muse Glimmer 30B
- Hosted Muse Spark 1.2 experiments through Meta's public-preview API
- Teams that want first-party open weights plus first-party safety models
- Cost-sensitive deployments where API vendor margin matters
- Research, adaptation, and fine-tuning on a mainstream open-weight base

## Provider-specific quirks

- **Scout and Maverick are not interchangeable.** Scout prioritizes accessibility and extreme context; Maverick is the heavier model.
- **Safety models are part of the story.** For production use, Meta increasingly expects teams to combine Llama with Llama Guard / Prompt Guard.
- **Check the exact model card.** Context, supported languages, and quantization details differ by artifact.
- **Two Hugging Face orgs.** Llama lives under `meta-llama`; Muse Glimmer lives under `meta-models`. The license differs with the org.
- **Do not merge the distribution stories.** Distribution is per artifact, not per family. A public Muse API does not make Muse Spark open weight; Muse Glimmer's Apache 2.0 weights do not extend to Muse Spark; Llama's downloadable weights do not imply a first-party Llama API; and Llama's community license does not apply to Muse Glimmer.

## Official docs and resources

- [Meta Llama on Hugging Face](https://huggingface.co/meta-llama)
- [Llama 4 collection](https://huggingface.co/collections/meta-llama/llama-4)
- [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E)
- [Llama 4 Maverick model card](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E)
- [Llama Guard 4 model card](https://huggingface.co/meta-llama/Llama-Guard-4-12B)
- [Llama Prompt Guard 2 model card](https://huggingface.co/meta-llama/Llama-Prompt-Guard-2-22M)
- [Llama Community License](https://llama.meta.com/license/)
- [Llama Cookbook (official)](https://github.com/meta-llama/llama-cookbook)
- [Meta AI developer products](https://developer.meta.com/ai/)
- [Meta Model API](https://developer.meta.com/ai/products/meta-model-api/)
- [Muse Spark model page and pricing](https://developer.meta.com/ai/models/muse-spark/)
- [Meet Muse Spark 1.2 and Muse Code](https://developer.meta.com/ai/resources/blog/build-with-muse-code/)
- [Muse Glimmer launch post](https://developer.meta.com/ai/resources/blog/build-with-muse-glimmer/)
- [Muse Glimmer developer docs](https://dev.meta.ai/docs/muse-glimmer)
- [Muse Spark 1.1 announcement](https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/)
- [Muse Spark 1.1 Evaluation Report](https://ai.meta.com/static-resource/muse-spark-1-1-evaluation-report)
- [Muse Spark Safety & Preparedness Report](https://ai.meta.com/static-resource/muse-spark-safety-and-preparedness-report/)
- [Muse Image and Muse Video announcement](https://ai.meta.com/blog/introducing-muse-image-muse-video-msl/)

## Status

`[provider-doc]`. This page separates three Meta distribution paths: Llama weights under the Llama Community License, Muse Glimmer weights under Apache 2.0, and the hosted Muse Spark API plus Meta product surfaces.
