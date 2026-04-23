# Meta `[provider-doc]`

*Last reviewed: 2026-04-23. Meta's public Llama 4 release that developers can actually use today is centered on Scout and Maverick, plus new safety-side releases like Llama Guard 4 and Prompt Guard 2. Verify against the official [meta-llama Hugging Face org](https://huggingface.co/meta-llama).*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Llama 4 Maverick | Flagship open-weight multimodal model | 17B active / ~400B total, 1M context |
| Llama 4 Scout | Efficient open-weight multimodal model | 17B active / ~109B total, 10M context |
| Llama Guard 4 | Multimodal safety classifier | 12B safeguard model derived from the Llama 4 stack |
| Llama Prompt Guard 2 | Prompt-attack classifier | 86M and 22M prompt-injection / jailbreak filters |

As of 2026-04-23, Meta's official public Llama 4 collection on Hugging Face is centered on Scout and Maverick. If someone asks for a broader “Llama 4 lineup,” verify whether they mean public weights, research references, or safety-side companion models.

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

## Weaknesses (cited)

- **License is still not OSI open source.** The Llama Community License has commercial terms and threshold clauses; read it before shipping.
- **No first-party hosted inference API.** You self-host or choose a third-party host, so pricing and reliability vary by vendor.
- **Prompt format and deployment details vary by model.** The right template and quantization path matter more than many teams expect.

## Best-fit tasks

- Self-hosted or third-party-hosted multimodal inference
- Teams that want first-party open weights plus first-party safety models
- Cost-sensitive deployments where API vendor margin matters
- Research, adaptation, and fine-tuning on a mainstream open-weight base

## Provider-specific quirks

- **Scout and Maverick are not interchangeable.** Scout prioritizes accessibility and extreme context; Maverick is the heavier flagship.
- **Safety models are part of the story.** For production use, Meta increasingly expects teams to combine Llama with Llama Guard / Prompt Guard.
- **Check the exact model card.** Context, supported languages, and quantization details differ by artifact.

## Official docs and resources

- [Meta Llama on Hugging Face](https://huggingface.co/meta-llama)
- [Llama 4 collection](https://huggingface.co/collections/meta-llama/llama-4)
- [Llama 4 Scout model card](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E)
- [Llama 4 Maverick model card](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E)
- [Llama Guard 4 model card](https://huggingface.co/meta-llama/Llama-Guard-4-12B)
- [Llama Prompt Guard 2 model card](https://huggingface.co/meta-llama/Llama-Prompt-Guard-2-22M)
- [Llama Community License](https://llama.meta.com/license/)
- [Llama Cookbook (official)](https://github.com/meta-llama/llama-cookbook)

## Status

`[provider-doc]`. This page now names the currently public Llama 4 release artifacts instead of treating “Llama 4” as a vague family label.
