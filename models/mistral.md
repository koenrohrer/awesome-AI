# Mistral `[provider-doc]`

*Last reviewed: 2026-04-22. Verify against [mistral.ai](https://mistral.ai/) and the [Mistral platform docs](https://docs.mistral.ai/) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Mistral Large | Flagship proprietary | Closed API; chat + reasoning |
| Mistral Small / Medium | Balanced | Lower cost, widely available |
| Mixtral-family (MoE) | Open weights | Sparse mixture-of-experts |
| Codestral | Code | Code-specialized variant |
| Pixtral | Vision-language | Multimodal |

Mistral runs a **dual-track** strategy: proprietary hosted models behind `la Plateforme`, plus open-weight releases on [HuggingFace](https://huggingface.co/mistralai). The split varies — check which track a given release belongs to before planning.

## Strengths (cited)

- **Open-weight mixture-of-experts.** Mixtral 8x7B and 8x22B (and successors) were among the first broadly-accessible open-weight MoE models — large total capacity, small *active* parameter count per token. See the [Mistral blog](https://mistral.ai/news/) for release-specific architecture details.
- **European jurisdiction.** For organizations requiring EU data residency or preferring European providers, Mistral's Paris-based hosting is a meaningful distinction.
- **Strong open-weight performance per active parameter.** MoE variants often beat dense models of similar active-parameter counts on public benchmarks — verify on the specific eval you care about.
- **Clear licensing on open releases** — Apache 2.0 on most open-weight releases, making commercial use straightforward. Verify the specific model's license.

## Weaknesses (cited)

- **Smaller ecosystem than Llama.** Fine-tunes and tooling lag Llama's, though MoE-capable open-source inference (vLLM, llama.cpp for GGUF variants) supports them well.
- **Track ambiguity.** Not every Mistral announcement is open-weight; some are closed. Read the release post carefully — the distinction isn't always prominent.
- **Tool-calling conventions** differ from OpenAI's format on some variants; check the specific model's docs.

## Best-fit tasks

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

`[provider-doc]`. Track (open vs proprietary) and pricing rotate per release.
