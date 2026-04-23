# Llama (Meta) `[provider-doc]`

*Last reviewed: 2026-04-22. Verify against [llama.com](https://www.llama.com/) and [Meta's Llama HuggingFace org](https://huggingface.co/meta-llama) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Llama 4 series | Flagship | Open weights, multiple sizes |
| Llama Guard | Safety | Input/output classifier trained for content moderation |
| Code Llama (legacy) | Code | Superseded by general Llama variants for most code tasks |

Meta publishes Llama as **open weights** (under the Llama Community License) on [HuggingFace](https://huggingface.co/meta-llama) and [llama.com](https://www.llama.com/). The license is not OSI-approved — it has specific terms around use at scale — read it before shipping commercially.

## Strengths (cited)

- **Reference open-weight family.** Llama is the de facto baseline for "what can open weights do?" — the first open model to reach frontier-adjacent quality. Most open-source inference tooling (`llama.cpp`, `vLLM`, `ollama`) has first-class Llama support from release day.
- **Ecosystem momentum.** Fine-tunes, quantizations, and specialized variants (Nous Hermes, WizardLM, Code Llama, Alpaca, Vicuna, etc.) concentrate on Llama bases. "Open weights" in production is frequently code for "Llama-family."
- **Multiple sizes** per release — small (deployable on consumer hardware after quantization), medium, and large variants.
- **Llama Guard** is a dedicated safety classifier Meta publishes alongside the main models; usable as an input/output filter in agent pipelines. See the [Llama Guard model card](https://huggingface.co/meta-llama).

## Weaknesses (cited)

- **License ambiguity at scale.** The Llama Community License has a "700M monthly active users" threshold clause — above it, you need a separate license from Meta. Startups often don't hit it; enterprises sometimes do. Read the license, not the vibe.
- **No first-party hosted API.** Meta doesn't run a user-facing inference API the way Anthropic/OpenAI do; you run it yourself or use a third-party host (Together, Fireworks, Groq, DeepInfra, Replicate, etc.).
- **Pricing varies by host.** With no first-party pricing, cost comparisons require picking a specific host and checking their rates.

## Best-fit tasks

- Self-hosted or offline inference
- Cost-sensitive workloads where third-party-hosted Llama beats closed-model API pricing
- Fine-tuning for specialist domains
- Research and experimentation where open weights matter

## Provider-specific quirks

- **Prompt format varies by version.** Each Llama release has its own instruction template (e.g., special tokens around system/user/assistant turns). Always check the model card's recommended template — the wrong format quietly degrades quality.
- **Tool-calling support matters by version.** Later Llama releases have trained-in tool use; earlier ones need prompting tricks. Check the card.

## Official docs and resources

- [llama.com](https://www.llama.com/)
- [Llama on HuggingFace](https://huggingface.co/meta-llama)
- [Llama Community License](https://llama.meta.com/license/)
- [llama.cpp](https://github.com/ggerganov/llama.cpp) — primary local inference engine
- [Llama Cookbook (official)](https://github.com/meta-llama/llama-cookbook) — recipes from Meta

## Status

`[provider-doc]`. Exact version, license, and hosted-inference pricing rotate.
