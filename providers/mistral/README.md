# Mistral `[provider-doc]`

*Last reviewed: 2026-08-06. Mistral publishes hosted services, open-weight models, and research-only releases. This catalog is date-stamped, not a ranking; verify each release against the [Mistral model docs](https://docs.mistral.ai/models/model-selection-guide) before building a cost or deployment model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Mistral Medium 3.5 | General multimodal tier | Hosted and open weights under a Modified MIT license |
| Mistral Small 4 | Hybrid general model | Hosted and open weights; instruct, reasoning, and coding modes |
| Mistral OCR 4 | Document AI service | `mistral-ocr-4-0`; block labels and paragraph bounding boxes |
| Leanstral 1.5 | Lean 4 proof engineering | `labs-leanstral-1-5`; 256K context, open weights, Labs API until September 30, 2026 |
| Robostral Navigate | Embodied-navigation research release | 8B vision-language model using a single RGB camera; no public API ID documented |

Mistral runs a **dual-track** strategy: proprietary hosted models behind `la Plateforme`, plus open-weight releases on [HuggingFace](https://huggingface.co/mistralai). The split varies — check which track a given release belongs to before planning.

## Docs-only specialist releases

| Release | Availability | Operational notes | Evidence |
|---|---|---|---|
| Mistral OCR 4 | Hosted OCR API | `mistral-ocr-4-0`; $4/1,000 pages or $5/1,000 annotated pages; `mistral-ocr-latest` points to OCR 4 | `[provider-doc]` [model card](https://docs.mistral.ai/models/model-cards/ocr-4-0), [OCR guide](https://docs.mistral.ai/studio-api/document-processing/basic_ocr) |
| Leanstral 1.5 | Labs API and open weights | `labs-leanstral-1-5`; 119B total / 6.5B active, 256K context, 128K output; scheduled retirement September 30, 2026 | `[provider-doc]` [model card](https://docs.mistral.ai/models/model-cards/leanstral-1-5), [changelog](https://docs.mistral.ai/resources/changelogs) |
| Robostral Navigate | Research announcement | 8B single-camera navigation model; Mistral reports 76.6% success on R2R-CE validation unseen | `[provider-doc]` [release post](https://mistral.ai/news/robostral-navigate/) |

## Strengths (cited)

- **Hosted and open-weight paths.** Current general models such as Mistral Medium 3.5 and Small 4 expose both routes. Verify the release-specific license and hardware requirements.
- **Specialist services.** OCR 4, Leanstral, and Robostral target document extraction, formal proofs, and robot navigation instead of broad chat.
- **Document structure output.** OCR 4 can return paragraph bounding boxes and structural labels in reading order. [OCR guide](https://docs.mistral.ai/studio-api/document-processing/basic_ocr).

## Weaknesses (cited)

- **Availability varies by release.** A Mistral name can refer to hosted-only, open-weight, or research-only access; check the model card or release post.
- **Labs models retire quickly.** Leanstral 1.5 is scheduled to retire from the Labs API on September 30, 2026. [Changelog](https://docs.mistral.ai/resources/changelogs).
- **MoE memory remains tied to total weights.** Small 4 activates 6.5B of 119B parameters, but local deployment must still store the full model or a quantization. [Model selection guide](https://docs.mistral.ai/models/model-selection-guide).

## Fits

- Open-weight inference where MoE cost characteristics matter (high active capacity, lower per-token compute than dense equivalents)
- EU-residency-sensitive workloads using `la Plateforme`
- Fine-tuning on permissively-licensed open weights (Apache 2.0)
- Code tasks targeting Codestral

## Provider-specific quirks

- **Instruction template.** Each Mistral release has a specific chat template; the correct format matters for quality. Always use the template from the model card.
- **MoE memory footprint.** MoE models have large *total* memory requirements even though active compute is smaller. Plan VRAM accordingly for self-hosting.

## Official docs and resources

- [mistral.ai](https://mistral.ai/)
- [Mistral platform docs](https://docs.mistral.ai/)
- [Mistral on HuggingFace](https://huggingface.co/mistralai)
- [Mistral news (release announcements)](https://mistral.ai/news/)

## Status

`[provider-doc]`. OCR 4, Leanstral 1.5, and Robostral Navigate remain docs-only entries; their hosted, open-weight, and research-only availability is stated separately.
