# Kimi K2.7 Code `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | Moonshot AI |
| Hosted model IDs | `kimi-k2.7-code`, `kimi-k2.7-code-highspeed` |
| Availability | Hosted API and open weights |
| Context window | 262,144 tokens (documented as 256K) |
| Modalities | Text, image, and video input |
| Reasoning | Thinking mode forced on; disabling it returns an error |
| Architecture | 1T-parameter Mixture-of-Experts; 32B parameters activated |
| Weights license | Modified MIT License |

## What it is

Kimi K2.7 Code is Moonshot's coding-focused model, built on Kimi K2.6. The platform model list scopes it to "text, image, and video input, thinking mode, dialogue, and agent tasks". Kimi K3 remains the documented flagship; K2.7 Code is a narrower coding path with a smaller context window and lower per-token prices. [Model list](https://platform.kimi.ai/docs/models), [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart).

The model card lists a Mixture-of-Experts stack: 61 layers including 1 dense layer, 384 experts with 8 selected per token plus 1 shared expert, MLA attention with 64 heads, a 160K vocabulary, and a 400M-parameter MoonViT vision encoder. [Hugging Face model card](https://huggingface.co/moonshotai/Kimi-K2.7-Code).

## Hosted API

Moonshot serves two IDs. `kimi-k2.7-code-highspeed` is the faster tier at double the price; the docs list roughly 180 tokens/s, and up to 260 tokens/s in short-context scenarios. [Model list](https://platform.kimi.ai/docs/models).

The quickstart documents an OpenAI-compatible surface at `https://api.moonshot.ai/v1`. The pricing page lists automatic context caching, tool calls, JSON mode, and partial mode. `tool_choice` accepts only `auto` or `none`. [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart), [Kimi K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code).

Several sampling parameters are fixed and return an error for other values: `temperature` 1.0, `top_p` 0.95, `n` 1, and presence and frequency penalties 0.0. `max_tokens` defaults to 32,768. [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart).

### Pricing

As reviewed on 2026-08-16, the platform lists the following per 1M tokens. Prices exclude applicable taxes. Pricing is date-sensitive; recheck the live pricing page before production use. [Kimi K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code).

| Model | Cache-hit input | Cache-miss input | Output |
|---|---|---|---|
| `kimi-k2.7-code` | $0.19 | $0.95 | $4.00 |
| `kimi-k2.7-code-highspeed` | $0.38 | $1.90 | $8.00 |

## Open weights

Moonshot publishes K2.7 Code weights on Hugging Face. The card states that both the code repository and the model weights are released under the Modified MIT License. As reviewed on 2026-08-16 there is no `MoonshotAI/Kimi-K2.7-Code` GitHub repository, and no technical report is linked from the card; the Hugging Face card is the open-weight source. [Hugging Face model card](https://huggingface.co/moonshotai/Kimi-K2.7-Code).

The card names vLLM, SGLang, and KTransformers as deployment paths and pins `transformers>=4.57.1,<5.0.0`. It also marks video chat as experimental and supported only in Moonshot's official API, so that capability does not transfer to a self-hosted deployment.

Hosted API access and the open-weight release are separate surfaces. Confirm features and limits on the platform docs for hosted use, and on the model card and license for self-hosting.

## Operational notes

Thinking cannot be turned off. The platform docs state that the model returns an error if thinking mode is disabled, and the model card states that K2.7 Code forces `thinking` and `preserve_thinking` to true. Callers that carry a shared code path with toggleable-thinking models such as `kimi-k2.6` need a per-model branch. [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart), [Hugging Face model card](https://huggingface.co/moonshotai/Kimi-K2.7-Code).

Moonshot reports better instruction compliance and long-horizon coding performance than K2.6, and about 30% lower thinking-token use. These are vendor claims in the quickstart and model card with no named harness, settings, or evaluation date; treat them as unverified.

## Links

- [Kimi K2.7 Code quickstart](https://platform.kimi.ai/docs/guide/kimi-k2-7-code-quickstart)
- [Kimi K2.7 Code pricing](https://platform.kimi.ai/docs/pricing/chat-k27-code)
- [Model list](https://platform.kimi.ai/docs/models)
- [Official Hugging Face weights and model card](https://huggingface.co/moonshotai/Kimi-K2.7-Code)
- [Use the Kimi vision model](https://platform.kimi.ai/docs/guide/use-kimi-vision-model)
- [Kimi API Platform](https://platform.kimi.ai/)

## Status

`[provider-doc]`. Hosted API access and open-weight artifacts are separate release surfaces.
