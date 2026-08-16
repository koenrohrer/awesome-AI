# Mistral `[provider-doc]`

*Last reviewed: 2026-08-16. Mistral publishes hosted services, open-weight models, third-party models it hosts, and research-only releases. This catalog is date-stamped, not a ranking; verify each release against the [Mistral model docs](https://docs.mistral.ai/models/model-selection-guide) before building a cost or deployment model. Every price below was read on 2026-08-16 and must be rechecked against [Mistral API pricing](https://mistral.ai/pricing/api) before use.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Mistral Medium 3.5 | General multimodal tier | GA; 256K context; hosted and open weights under a Modified MIT license |
| Mistral Small 4 | Hybrid general model | Apache 2.0; 119B total / 6.5B active, 256K context; instruct, reasoning, and coding modes |
| Z.ai GLM 5.2 | Third-party generalist hosted by Mistral | `zai-glm-5-2`; 1M context, 128K output; served without Mistral modifications |
| Mistral OCR 4.1 | Document AI service | `mistral-ocr-4-1`; paragraph bounding boxes, structural block labels, block-level confidence scores |
| Leanstral 1.5 | Lean 4 proof engineering | `labs-leanstral-1-5`; 256K context, open weights, Labs API until September 30, 2026 |
| Robostral Navigate | Embodied-navigation research release | 8B vision-language model using a single RGB camera; no public API ID documented |

Mistral runs a **dual-track** strategy: proprietary hosted models behind `la Plateforme`, plus open-weight releases on [HuggingFace](https://huggingface.co/mistralai). `la Plateforme` also serves at least one third-party model, Z.ai GLM 5.2, which Mistral documents as "hosted by Mistral" and "served without Mistral modifications". `[provider-doc]` [model card](https://docs.mistral.ai/models/model-cards/zai-glm-5-2). The split varies — check which track a given release belongs to before planning.

## Docs-only specialist releases

| Release | Availability | Operational notes | Evidence |
|---|---|---|---|
| Mistral OCR 4.1 | Hosted OCR API, Public Preview | `mistral-ocr-4-1`, released July 16, 2026; adds block-level confidence scores over OCR 4.0; $4/1,000 pages or $5/1,000 annotated pages (prices read 2026-08-16; recheck before budgeting). Since July 16, 2026 both `mistral-ocr-latest` and `mistral-ocr-4` resolve to OCR 4.1, not OCR 4.0 — pin an explicit version if you need stable output. | `[provider-doc]` [model card](https://docs.mistral.ai/models/model-cards/ocr-4-1), [changelog](https://docs.mistral.ai/resources/changelogs), [API pricing](https://mistral.ai/pricing/api), [OCR guide](https://docs.mistral.ai/studio-api/document-processing/basic_ocr) |
| Mistral OCR 4.0 | Hosted OCR API, still callable by pinned ID | `mistral-ocr-4-0`; paragraph bounding boxes and structural block labels, no block-level confidence scores; no retirement date documented as of 2026-08-16 | `[provider-doc]` [model card](https://docs.mistral.ai/models/model-cards/ocr-4-0) |
| Leanstral 1.5 | Labs API (Public Preview) and open weights, Apache 2.0 | `labs-leanstral-1-5`; 119B total / 6.5B active, 256K context, 128K output; retirement on September 30, 2026 still stated in the changelog as of 2026-08-16 | `[provider-doc]` [model card](https://docs.mistral.ai/models/model-cards/leanstral-1-5), [changelog](https://docs.mistral.ai/resources/changelogs) |
| Robostral Navigate | Research announcement | 8B vision-language navigation model running "from a single RGB camera, with no LiDAR or depth sensors"; Mistral reports 76.6% success on R2R-CE validation unseen. The release post names no API ID and does not state whether weights are published; it points to a technical report and a contact form. | `[provider-doc]` [release post](https://mistral.ai/news/robostral-navigate/) |

## Strengths (cited)

- **Hosted and open-weight paths.** Current general models such as Mistral Medium 3.5 and Small 4 expose both routes. Verify the release-specific license and hardware requirements.
- **Specialist services.** OCR 4.1, Leanstral, and Robostral target document extraction, formal proofs, and robot navigation instead of broad chat.
- **Document structure output.** OCR 4.1 returns paragraph bounding boxes and structural block labels in reading order, with documented block types including `table`, `equation`, `code`, and `signature`. [OCR guide](https://docs.mistral.ai/studio-api/document-processing/basic_ocr).
- **Per-block OCR confidence.** OCR 4.1 adds `"block"` to the `confidence_scores_granularity` parameter, alongside the existing `"page"` and `"word"` values, so downstream code can route low-confidence regions to review. [Changelog](https://docs.mistral.ai/resources/changelogs), [OCR guide](https://docs.mistral.ai/studio-api/document-processing/basic_ocr).

## Weaknesses (cited)

- **Availability varies by release.** A Mistral name can refer to hosted-only, open-weight, third-party-hosted, or research-only access; check the model card or release post.
- **`-latest` aliases move under you.** On July 16, 2026 Mistral repointed both `mistral-ocr-latest` and `mistral-ocr-4` from OCR 4.0 to OCR 4.1. Pin `mistral-ocr-4-0` or `mistral-ocr-4-1` if extraction output must stay stable. [Changelog](https://docs.mistral.ai/resources/changelogs).
- **Preview status on current surfaces.** OCR 4.1, Leanstral 1.5, and Z.ai GLM 5.2 are each documented as Public Preview, so behavior and availability can change without a deprecation window. Model cards: [OCR 4.1](https://docs.mistral.ai/models/model-cards/ocr-4-1), [Leanstral 1.5](https://docs.mistral.ai/models/model-cards/leanstral-1-5), [Z.ai GLM 5.2](https://docs.mistral.ai/models/model-cards/zai-glm-5-2).
- **Labs models retire quickly.** Leanstral 1.5 is scheduled to retire from the Labs API on September 30, 2026, about three months after its June 30, 2026 release. [Changelog](https://docs.mistral.ai/resources/changelogs).
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

`[provider-doc]`. Reviewed 2026-08-16 against the [model selection guide](https://docs.mistral.ai/models/model-selection-guide), the [model cards index](https://docs.mistral.ai/models/model-cards/), and the [changelog](https://docs.mistral.ai/resources/changelogs).

OCR 4.1, OCR 4.0, Leanstral 1.5, and Robostral Navigate remain docs-only entries; their hosted, open-weight, and research-only availability is stated separately. Two claims carried from the 2026-08-06 review were corrected: OCR 4.1 (`mistral-ocr-4-1`) superseded OCR 4.0 as the current OCR service, and `mistral-ocr-latest` no longer points to OCR 4.0. OCR pricing was rechecked and is unchanged at $4/1,000 pages and $5/1,000 annotated pages as of 2026-08-16.

Not covered here because the official docs do not state it: whether Robostral Navigate has published weights or a callable API ID, and any retirement date for OCR 4.0.
