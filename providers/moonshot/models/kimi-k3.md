# Kimi K3 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | Moonshot AI |
| Hosted model ID | `kimi-k3` |
| Availability | Hosted API and open weights |
| Context window | 1,048,576 tokens |
| Modalities | Text and image input; the model card also documents video understanding |
| Reasoning | Always enabled; `low`, `high`, or `max` effort |
| Architecture | 2.8T-parameter Mixture-of-Experts model; 104B parameters activated |

## What it is

Kimi K3 is Moonshot's native multimodal, long-context model for coding, knowledge work, reasoning, and tool-using workflows. The official model card documents Kimi Delta Attention, Gated Multi-head Latent Attention, Attention Residuals, and a Stable LatentMoE that selects 16 of 896 experts.

## Hosted API

Moonshot serves Kimi K3 as `kimi-k3` through the Kimi API Platform. The platform lists automatic context caching, tool calls, JSON mode, structured output, partial mode, tool-choice constraints, and dynamic tool loading.

As reviewed on 2026-08-16, the platform lists $3.00 per 1M cache-miss input tokens, $0.30 per 1M cache-hit input tokens, and $15.00 per 1M output tokens. Pricing and platform features are date-sensitive; recheck the live pricing page before production use.

For coding work that fits a 256K context, [Kimi K2.7 Code](kimi-k2-7-code.md) is the cheaper documented path on the same platform.

## Open weights and report

Moonshot separately publishes model weights on Hugging Face and source material on GitHub under the Kimi K3 License. That license includes additional conditions for some model-as-a-service businesses and large commercial products, so "open weight" should not be read as an OSI open-source claim.

The repository includes the Kimi K3 technical report. Benchmark results in the model card and report are Moonshot-reported and depend on named harnesses, reasoning settings, and evaluation dates; they are not a repository ranking.

## Operational notes

Kimi K3 always returns reasoning content. For multi-turn conversations and tool calls, Moonshot requires callers to preserve and resend the complete assistant message, including `reasoning_content` and `tool_calls`.

## Links

- [Official Kimi K3 repository and model card](https://github.com/MoonshotAI/Kimi-K3)
- [Official Hugging Face weights](https://huggingface.co/moonshotai/Kimi-K3)
- [Kimi K3 technical report](https://github.com/MoonshotAI/Kimi-K3/blob/main/k3_tech_report.pdf)
- [Kimi API Platform](https://platform.kimi.ai/)
- [Kimi K3 pricing and feature documentation](https://platform.kimi.ai/docs/pricing/chat-k3)
- [Kimi K3 License](https://github.com/MoonshotAI/Kimi-K3/blob/main/LICENSE)

## Status

`[provider-doc]`. Hosted API access and open-weight artifacts are separate release surfaces.
