# Meta `[provider-doc]`

*Last reviewed: 2026-08-06. Meta now has two distinct developer stories: Llama open weights and the hosted Meta Model API public preview for Muse Spark 1.1.*

## Current hosted and product surfaces

| Surface | Role | Availability |
|---|---|---|
| Meta Model API / Muse Spark 1.1 | Hosted multimodal reasoning and agent model | Public-preview developer API |
| Muse Image | Image generation, editing, and composition | Available on named Meta product surfaces |
| Muse Video | Video generation with native audio | Preview; coming to creators and Meta AI |

## Product pages

- [Meta Model API and Muse Spark 1.1](muse-model-api.md)
- [Muse Image and Muse Video](muse-image-video.md)

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Llama 4 Maverick | Higher-capacity open-weight multimodal model | 17B active / ~400B total, 1M context |
| Llama 4 Scout | Efficient open-weight multimodal model | 17B active / ~109B total, 10M context |
| Llama Guard 4 | Multimodal safety classifier | 12B safeguard model derived from the Llama 4 stack |
| Llama Prompt Guard 2 | Prompt-attack classifier | 86M and 22M prompt-injection / jailbreak filters |

Meta's official public Llama 4 collection on Hugging Face remains centered on Scout and Maverick. If someone asks for a broader Meta model lineup, first distinguish downloadable Llama weights from Meta-hosted Muse products.

## Model pages

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

Meta does not publish Llama safety documentation under a “system card” hub comparable to Anthropic/OpenAI. The model cards and companion safeguard model cards are the operational primary sources.

## Strengths (cited)

- **Reference open-weight family.** Llama remains the default ecosystem baseline for open weights; tooling support across `llama.cpp`, `vLLM`, `Transformers`, and quantization stacks remains first-class.
- **Current Llama 4 release is natively multimodal.** Scout and Maverick both accept text and image input. [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E), [Llama 4 Maverick model card](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E).
- **Companion safeguard models are first-party.** Llama Guard 4 and Prompt Guard 2 give teams an official safety/filtering path rather than relying entirely on third parties.
- **Very long context on Scout.** The official model card lists 10M context for Scout, making it operationally distinct from Maverick. [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E).
- **First-party hosted model API.** The Meta Model API public preview gives developers hosted access to Muse Spark 1.1. [Muse Spark 1.1 announcement](https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/).

## Weaknesses (cited)

- **License is still not OSI open source.** The Llama Community License has commercial terms and threshold clauses; read it before shipping.
- **Hosting depends on the family.** Llama weights remain a self-hosted or third-party-hosted path, while Muse Spark 1.1 is available through Meta's first-party public-preview API.
- **Muse lifecycle and distribution differ from Llama.** Meta has not announced downloadable Muse Spark 1.1 weights, and the API is not yet generally available.
- **Prompt format and deployment details vary by model.** The right template and quantization path matter more than many teams expect.

## Fits

- Self-hosted or third-party-hosted multimodal inference
- Hosted Muse Spark 1.1 experiments through Meta's public-preview API
- Teams that want first-party open weights plus first-party safety models
- Cost-sensitive deployments where API vendor margin matters
- Research, adaptation, and fine-tuning on a mainstream open-weight base

## Provider-specific quirks

- **Scout and Maverick are not interchangeable.** Scout prioritizes accessibility and extreme context; Maverick is the heavier model.
- **Safety models are part of the story.** For production use, Meta increasingly expects teams to combine Llama with Llama Guard / Prompt Guard.
- **Check the exact model card.** Context, supported languages, and quantization details differ by artifact.
- **Do not merge the distribution stories.** A public Muse API does not make Muse open weight, and Llama's downloadable weights do not imply a first-party Llama API.

## Official docs and resources

- [Meta Llama on Hugging Face](https://huggingface.co/meta-llama)
- [Llama 4 collection](https://huggingface.co/collections/meta-llama/llama-4)
- [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E)
- [Llama 4 Maverick model card](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E)
- [Llama Guard 4 model card](https://huggingface.co/meta-llama/Llama-Guard-4-12B)
- [Llama Prompt Guard 2 model card](https://huggingface.co/meta-llama/Llama-Prompt-Guard-2-22M)
- [Llama Community License](https://llama.meta.com/license/)
- [Llama Cookbook (official)](https://github.com/meta-llama/llama-cookbook)
- [Muse Spark 1.1 announcement](https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/)
- [Muse Spark 1.1 Evaluation Report](https://ai.meta.com/static-resource/muse-spark-1-1-evaluation-report)
- [Muse Image and Muse Video announcement](https://ai.meta.com/blog/introducing-muse-image-muse-video-msl/)

## Status

`[provider-doc]`. This page separates Meta's open-weight Llama artifacts from its hosted Muse API and product surfaces.
