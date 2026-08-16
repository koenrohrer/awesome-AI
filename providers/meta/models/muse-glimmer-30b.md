# Muse Glimmer 30B `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | Meta (Meta Superintelligence Labs) |
| Weights repository | `meta-models/Muse-Glimmer-30B` |
| Availability | Open weights, downloadable |
| License | Apache 2.0 |
| Context window | 128K tokens by default; the model card lists 131,072+ |
| Modalities | Text and image input; text output |
| Architecture | ~29.6B dense causal LM plus a ~1.8B ViT-G/14 perception encoder |
| Distilled from | Muse Spark |
| Knowledge cutoff | 2026-01-04 |
| Languages | Trained on data from more than 100 languages |

## What it is

Muse Glimmer is Meta's open-weight model for local agent workloads. The model card describes it as "a 30-billion-parameter causal language model with a dedicated perception encoder, distilled from Muse Spark and purpose-built for autonomous agentic tasks on consumer hardware." [Muse Glimmer 30B model card](https://huggingface.co/meta-models/Muse-Glimmer-30B).

It is the first Muse model Meta has released as downloadable weights. Muse Spark, the hosted model it was distilled from, remains API-only — see [Meta Model API and Muse Spark 1.2](../muse-model-api.md). Meta's launch post calls Apache 2.0 "the most permissive license we've used for an open model," which puts Glimmer on different terms from the Llama Community License that covers Llama 4. [Muse Glimmer launch post](https://developer.meta.com/ai/resources/blog/build-with-muse-glimmer/).

Meta's launch post is dated 2026-08-12. Hugging Face's day-0 integration post is dated 2026-08-10.

## Architecture

The model card documents a hybrid attention stack rather than uniform global attention:

| Field | Value |
|---|---|
| Total parameters | ~29.6B including the vision encoder |
| Layers | 52 |
| Hidden dimension | 6656 |
| Attention pattern | `[Local, Local, Local, Global]`, repeating |
| Attention heads | Gated attention, 32 query / 2 KV heads (16:1 GQA ratio) |
| FFN | SwiGLU |
| Perception encoder | ViT-G/14, 50 layers, width 1536, patch size 14 |

The three-local-to-one-global attention ratio is what keeps a 128K context tractable at this parameter count. The perception encoder is what lets an agent read a screenshot, chart, or scanned document as part of a tool-use loop rather than through a separate OCR step. [Muse Glimmer 30B model card](https://huggingface.co/meta-models/Muse-Glimmer-30B).

## Weights and serving

| Repository | Format |
|---|---|
| [`meta-models/Muse-Glimmer-30B`](https://huggingface.co/meta-models/Muse-Glimmer-30B) | BF16 safetensors |
| [`meta-models/Muse-Glimmer-30B-GGUF`](https://huggingface.co/meta-models/Muse-Glimmer-30B-GGUF) | GGUF, Meta-calibrated quants |
| [`meta-models/Muse-Glimmer-30B-assistant`](https://huggingface.co/meta-models/Muse-Glimmer-30B-assistant) | DFlash drafter for speculative decoding |
| [`meta-models/Muse-Glimmer-30B-ExecuTorch-PTE`](https://huggingface.co/meta-models/Muse-Glimmer-30B-ExecuTorch-PTE) | ExecuTorch PTE for on-device |

Unlike most open-weight releases, the quantizations and the speculative-decoding drafter are first-party Meta artifacts rather than community uploads. [Get the model](https://dev.meta.ai/docs/muse-glimmer/get-the-model/).

Memory guidance from Meta's own docs:

| Variant | Footprint | Target |
|---|---|---|
| GGUF K-quant | ~17 GB | Fits under 24 GB VRAM |
| GGUF dynamic K-quant | ~20 GB | 32 GB VRAM, higher quality |
| BF16 full precision | — | 64 GB VRAM |

Meta documents deployment through llama.cpp, ExecuTorch, vLLM, SGLang, Ollama, LM Studio, Unsloth, and Transformers, and hosted access through Together AI, Fireworks AI, and OpenRouter. [Muse Glimmer docs](https://dev.meta.ai/docs/muse-glimmer).

## Benchmarks

The model card publishes self-reported scores on named benchmarks including MCP Atlas, DeepSearch QA, SWE-Bench Pro, CharXiv Reasoning, and AIME 2026. Meta does not publish the evaluation harness or per-benchmark methodology alongside them, so they are not reproduced here. Read them on the model card as vendor-reported numbers, and run your own harness before sizing a deployment.

## Caveats

- **Apache 2.0 covers Glimmer, not the Muse family.** Muse Spark 1.1 and 1.2 remain hosted-only. Do not generalize the license.
- **The 24 GB figure is a quantized figure.** Full-precision BF16 needs 64 GB. A 4-bit quant is a different artifact from the one the benchmarks were run on.
- **Distillation ceiling.** Glimmer is distilled from Muse Spark. Meta positions it for local agent loops, not as a replacement for the hosted model.

## Links

- [Muse Glimmer 30B model card](https://huggingface.co/meta-models/Muse-Glimmer-30B)
- [Muse Glimmer launch post](https://developer.meta.com/ai/resources/blog/build-with-muse-glimmer/)
- [Muse Glimmer product page](https://developer.meta.com/ai/models/muse-glimmer/)
- [Muse Glimmer developer docs](https://dev.meta.ai/docs/muse-glimmer)
- [Get the model](https://dev.meta.ai/docs/muse-glimmer/get-the-model/)
- [Meta Inc. org on Hugging Face](https://huggingface.co/meta-models)

## Status

`[provider-doc]`. Open-weight release under Apache 2.0, published in Meta's own `meta-models` Hugging Face organization and documented on Meta's developer site.
