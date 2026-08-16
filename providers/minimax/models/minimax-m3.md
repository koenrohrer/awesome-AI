# MiniMax M3 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| API model ID | `MiniMax-M3` |
| Lifecycle | Available in the MiniMax API and Token Plan |
| Deployment | Hosted API and open weights |
| Modalities | Text, image, and video input; text output |
| Context window | 1,000,000 total input and output tokens |
| Architecture | About 428B total / 23B active parameters; MiniMax Sparse Attention |
| Reasoning | `enabled`, `adaptive`, or `disabled` through the `thinking` parameter |
| Weight license | MiniMax Community License |

## What it is

MiniMax M3 is MiniMax's current M-series model for coding, tool use, multimodal analysis, and long-context agent workflows. The hosted API supports the Anthropic-compatible and OpenAI-compatible surfaces documented by MiniMax.

The official model repository provides weights and deployment guidance for SGLang, vLLM, Transformers, and KTransformers. Review the MiniMax Community License before redistribution or commercial deployment.

## Pricing and limits

As reviewed, MiniMax lists separate standard rates by input length:

| Input length | Input | Cached input | Output |
|---|---:|---:|---:|
| Up to 512K tokens | $0.30 / 1M | $0.06 / 1M | $1.20 / 1M |
| Above 512K tokens | $0.60 / 1M | $0.12 / 1M | $2.40 / 1M |

These are the discounted rates displayed on the live pricing page on the review date. Priority service costs 1.5 times the standard rate. Check the live page before budgeting.

## Links

- [Model page](https://www.minimax.io/models/text/m3)
- [Release post](https://www.minimax.io/blog/minimax-m3)
- [API overview](https://platform.minimax.io/docs/api-reference/api-overview)
- [Pricing](https://platform.minimax.io/docs/guides/pricing-paygo)
- [Official model repository](https://github.com/MiniMax-AI/MiniMax-M3)
- [Official model card](https://huggingface.co/MiniMaxAI/MiniMax-M3)

## Status

`[provider-doc]`.
