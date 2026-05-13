# Gemma 4 `[provider-doc]`

*Last reviewed: 2026-05-13.*

## At a glance

- Provider: Google (DeepMind)
- Family: Gemma 4
- Tier: Open-weight family spanning edge to workstation
- Variants: `Gemma 4 E2B`, `Gemma 4 E4B`, `Gemma 4 26B A4B` (MoE), `Gemma 4 31B` (dense)
- Context window: 128K tokens on the edge variants (`E2B`, `E4B`); 256K on the workstation variants (`26B A4B`, `31B`)
- Official docs: [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/), [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4), [Gemma 4 MTP docs](https://ai.google.dev/gemma/docs/mtp/overview)

## What it is

Gemma 4 is Google's current open-weight model family, positioned as a deployment track from phones and Raspberry Pi-class devices up through consumer-GPU workstations. It is a separate track from the hosted Gemini API — shared research lineage, different docs, different deployment assumptions. DeepMind highlights multimodal input (text, image, audio on edge variants), native function-calling, and support for 140+ languages.

## Distribution channels

Per the [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/), Gemma 4 is distributed through Hugging Face, Kaggle, Ollama, LM Studio, Vertex AI, Google AI Edge, GKE, and Docker. Prompt formatting, system-instruction handling, and tool-calling details vary by runtime; do not assume Gemini-API conventions apply.

## Multi-token prediction drafters

Google released Multi-Token Prediction (MTP) drafters for Gemma 4 in May 2026. The [Gemma MTP docs](https://ai.google.dev/gemma/docs/mtp/overview) describe MTP as Gemma 4's speculative-decoding architecture: a smaller drafter predicts several future tokens, and the target Gemma 4 model verifies those tokens in parallel.

The drafters share the target model's input embeddings, use target-model activations, and share KV cache. Google's release post reports up to a 3x inference speedup, while noting hardware and batch-size caveats; the `26B A4B` MoE variant can need higher batch sizes to offset expert-routing overhead. See [multi-token prediction](../../../learning/architecture/multi-token-prediction.md) for the architecture primer.

## Public system card availability

Google does not publish a separate Gemma system-card hub. The [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4) is the closest official equivalent.

## Links

- [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/)
- [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)
- [Gemma 4 MTP docs](https://ai.google.dev/gemma/docs/mtp/overview)
- [Gemma 4 MTP release post](https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/)
- [Gemma docs home](https://ai.google.dev/gemma/docs)
- [Get started with Gemma](https://ai.google.dev/gemma/docs/get_started)
- [Gemma on Ollama](https://ollama.com/library/gemma4)
- [Gemma releases](https://ai.google.dev/gemma/docs/releases)
- [Gemma terms](https://ai.google.dev/gemma/terms)

## Status

`[provider-doc]`. Model sizes, distribution channels, and MTP drafter notes reflect Google's April-May 2026 Gemma 4 documentation; re-verify runtime support before committing to a deployment target.
