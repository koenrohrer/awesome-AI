# Qwen3.8-27B `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | Alibaba |
| Weights repository | `Qwen/Qwen3.8-27B` |
| Availability | Open weights |
| Context window | 262,144 tokens natively; extensible to 1,000,000 with RoPE scaling |
| Modalities | Text, image, and video input; text output |
| Reasoning | Thinking on by default, disableable per request; `reasoning_effort` of `low`, `medium`, or `xhigh` (default `xhigh`) |
| Architecture | 27B dense language model with a vision encoder |
| License | Apache 2.0 |

## What it is

Qwen3.8-27B is the small open-weight release of the Qwen3.8 generation. It is a native vision-language model: the model card documents image and video understanding alongside text, rather than a text model with a bolted-on adapter.

Unlike the Max-class [Qwen3.8-2.4T-A95B](qwen3-8-2-4t-a95b.md), this release is Apache 2.0, with no revenue or user-count thresholds attached.

## Architecture

The model card documents a hybrid layer stack rather than uniform attention:

| Field | Value |
|---|---|
| Parameters | 27B |
| Hidden dimension | 5120 |
| Layers | 64, arranged as 16 × (3 × (Gated DeltaNet → FFN) → 1 × (Gated Attention → FFN)) |
| Gated DeltaNet heads | 48 linear attention heads (V), 16 (QK), head dimension 128 |
| Gated Attention heads | 24 (Q), 4 (KV), head dimension 256 |
| Training | Multi-Token Prediction |

The three-to-one ratio of linear-attention blocks to full-attention blocks is what makes the 262K native context tractable at this parameter count. See [multi-token prediction](../../../learning/architecture/multi-token-prediction.md) for the training objective.

## Weights and serving

| Repository | Format |
|---|---|
| [`Qwen/Qwen3.8-27B`](https://huggingface.co/Qwen/Qwen3.8-27B) | BF16 safetensors |
| [`Qwen/Qwen3.8-27B-FP8`](https://huggingface.co/Qwen/Qwen3.8-27B-FP8) | FP8 |

The model card links serving recipes for [SGLang](https://docs.sglang.io/cookbook/autoregressive/Qwen/Qwen3.8-27B) and [vLLM](https://recipes.vllm.ai/Qwen/Qwen3.8-27B). Community quantizations in GGUF, MLX, AWQ, and NVFP4 exist on Hugging Face but are third-party artifacts; verify the publisher before use.

Alibaba's release post states that a hosted version of Qwen3.8-27B is planned with 1M context by default and built-in tools. As reviewed on 2026-08-16 that hosted surface is announced, not confirmed live; check Model Studio before depending on it.

## Links

- [Hugging Face model card](https://huggingface.co/Qwen/Qwen3.8-27B)
- [FP8 weights](https://huggingface.co/Qwen/Qwen3.8-27B-FP8)
- [Qwen3.8 release post](https://qwen.ai/blog?id=qwen3.8)
- [Qwen on ModelScope](https://modelscope.cn/organization/qwen)

## Status

`[provider-doc]`. Open-weight release under Apache 2.0. The hosted variant is announced but unverified.
