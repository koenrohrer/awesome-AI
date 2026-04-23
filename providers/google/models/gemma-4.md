# Gemma 4 `[provider-doc]`

*Last reviewed: 2026-04-23.*

## At a glance

- Provider: Google (DeepMind)
- Family: Gemma 4
- Tier: Open-weight family spanning edge to workstation
- Variants: `Gemma 4 E2B`, `Gemma 4 E4B`, `Gemma 4 26B A4B` (MoE), `Gemma 4 31B` (dense)
- Context window: 128K tokens on the edge variants (`E2B`, `E4B`); 256K on the workstation variants (`26B A4B`, `31B`)
- Official docs: [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/), [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)

## What it is

Gemma 4 is Google's current open-weight model family, positioned as a deployment track from phones and Raspberry Pi-class devices up through consumer-GPU workstations. It is a separate track from the hosted Gemini API — shared research lineage, different docs, different deployment assumptions. DeepMind highlights multimodal input (text, image, audio on edge variants), native function-calling, and support for 140+ languages.

## Distribution channels

Per the [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/), Gemma 4 is distributed through Hugging Face, Kaggle, Ollama, LM Studio, Vertex AI, Google AI Edge, GKE, and Docker. Prompt formatting, system-instruction handling, and tool-calling details vary by runtime; do not assume Gemini-API conventions apply.

## Public system card availability

Google does not publish a separate Gemma system-card hub. The [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4) is the closest official equivalent.

## Links

- [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/)
- [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)
- [Gemma docs home](https://ai.google.dev/gemma/docs)
- [Get started with Gemma](https://ai.google.dev/gemma/docs/get_started)
- [Gemma on Ollama](https://ollama.com/library/gemma4)
- [Gemma releases](https://ai.google.dev/gemma/docs/releases)
- [Gemma terms](https://ai.google.dev/gemma/terms)

## Status

`[provider-doc]`. Model sizes and distribution channels reflect the April 2026 Gemma 4 launch; re-verify distribution links before committing to a deployment target.
