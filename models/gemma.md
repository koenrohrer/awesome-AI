# Gemma (Google DeepMind) `[provider-doc]`

*Last reviewed: 2026-04-23. Verify against the [Gemma 4 page on Google DeepMind](https://deepmind.google/models/gemma/gemma-4/) and the [Gemma docs](https://ai.google.dev/gemma/docs) before picking a deployment target.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Gemma 4 E2B | Smallest edge model | Audio + vision support with 128K context |
| Gemma 4 E4B | Larger edge model | More capable on-device multimodal model with 128K context |
| Gemma 4 26B A4B | Workstation MoE model | Advanced reasoning/coding with 256K context |
| Gemma 4 31B | Largest dense model | Highest-end Gemma 4 line with 256K context |

Google positions Gemma 4 as an **open-model** family for deployment from phones and Raspberry Pi-class devices up through consumer-GPU workstations. The DeepMind launch page highlights distribution through [Hugging Face](https://huggingface.co/collections/google/gemma-4-67e6e335550ef35f6e40a842), [Kaggle](https://www.kaggle.com/models/google/gemma), [Ollama](https://ollama.com/library/gemma4), [LM Studio](https://lmstudio.ai/models/gemma-4), and Docker.

## Strengths (cited)

- **Real open-weight deployment range.** The official Gemma 4 page spans edge (`E2B`, `E4B`) and workstation (`26B A4B`, `31B`) targets instead of only datacenter-class models. See the [Gemma 4 launch page](https://deepmind.google/models/gemma/gemma-4/).
- **Multimodal and agent-friendly.** DeepMind explicitly calls out multimodal reasoning and agentic workflows with native function calling support. See the [capabilities section](https://deepmind.google/models/gemma/gemma-4/).
- **Broad language support.** Google says Gemma 4 supports over 140 languages, which matters if you need one open model family for multilingual products. See the [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4).
- **Flexible tuning/deployment stack.** Google documents Gemma across JAX, Keras, Vertex AI, Google AI Edge, GKE, and Ollama rather than forcing one runtime. See the [Gemma 4 run section](https://deepmind.google/models/gemma/gemma-4/) and [Gemma docs](https://ai.google.dev/gemma/docs).

## Weaknesses (cited)

- **You own more of the serving story.** Unlike Gemini, Gemma is primarily a weights-and-runtime ecosystem. The official materials emphasize downloading, tuning, and deploying across third-party or self-managed stacks. See the [Gemma 4 page](https://deepmind.google/models/gemma/gemma-4/) and [get started guide](https://ai.google.dev/gemma/docs/get_started).
- **Capability depends heavily on the size you pick.** Google splits the family into edge-first (`E2B`, `E4B`) and workstation-first (`26B A4B`, `31B`) lines, so selecting the wrong size for your hardware materially changes quality. See the [model sizes section](https://deepmind.google/models/gemma/gemma-4/).
- **Runtime surface is less standardized.** Prompt formatting, system-instruction handling, and tool-calling details vary by the runtime you choose (`transformers`, Ollama, Vertex AI, etc.), so "Gemma support" is not one uniform API. Start with the [Gemma docs](https://ai.google.dev/gemma/docs) rather than assuming Gemini API conventions.

## Best-fit tasks

- Local-first coding assistants and agent workflows on your own hardware
- Multimodal applications where you want open weights instead of a closed hosted API
- Edge and mobile inference with audio/vision support
- Fine-tuned domain models where controlling weights and runtime matters

## Provider-specific quirks

- **Gemma is not Gemini.** Gemma comes from the same research lineage, but it is a separate open-model track with different deployment workflows and docs. Start from [ai.google.dev/gemma](https://ai.google.dev/gemma/docs), not the Gemini API docs.
- **Small and large lines optimize for different environments.** DeepMind positions `E2B`/`E4B` for phones and IoT, while `26B A4B`/`31B` target personal computers and consumer GPUs. See the [Gemma 4 page](https://deepmind.google/models/gemma/gemma-4/).
- **Distribution channel matters.** The same model family is surfaced through Hugging Face, Kaggle, Ollama, Vertex AI, and Google AI Edge; setup steps and serving ergonomics differ by channel.

## Official docs

- [Gemma 4 on Google DeepMind](https://deepmind.google/models/gemma/gemma-4/)
- [Gemma docs](https://ai.google.dev/gemma/docs)
- [Get started with Gemma](https://ai.google.dev/gemma/docs/get_started)
- [Gemma 4 model card](https://ai.google.dev/gemma/docs/core/model_card_4)
- [Gemma releases](https://ai.google.dev/gemma/docs/releases)
- [Gemma terms](https://ai.google.dev/gemma/terms)

## Status

`[provider-doc]`. Model sizes and recommended runtimes changed in April 2026 with the Gemma 4 launch; verify current distribution channels before deploying.
