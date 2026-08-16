# Qwen3.8-2.4T-A95B `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | Alibaba |
| Weights repository | `Qwen/Qwen3.8-2.4T-A95B` |
| Availability | Open weights |
| Context window | 262,144 tokens natively; extensible to 1,010,000 |
| Modalities | Text and image input; text output |
| Architecture | Mixture-of-Experts; 2.4T parameters total, 95B activated |
| License | Qwen3.8-Max License (bespoke, not OSI open source) |

## What it is

Qwen3.8-2.4T-A95B is the Max-class model of the Qwen3.8 generation, published as downloadable weights. Alibaba's release post describes it as the first time a Qwen-Max-class model has been released with open weights; earlier Max tiers were hosted Model Studio services only.

The model card documents a mixed attention design across 92 layers, alternating Gated DeltaNet (linear attention) and Gated Attention blocks, each paired with a Mixture-of-Experts layer. Each MoE layer holds 512 experts and activates 11 per token: 10 routed and 1 shared.

## Weights and serving

| Repository | Format |
|---|---|
| [`Qwen/Qwen3.8-2.4T-A95B`](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B) | BF16 safetensors, Hugging Face Transformers layout |
| [`Qwen/Qwen3.8-2.4T-A95B-FP8`](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B-FP8) | Fine-grained FP8, block size 128 |

At 2.4T total parameters the checkpoint is far outside single-node commodity hardware. The FP8 release lowers memory per expert but does not change the total parameter count that must be resident or paged across the serving cluster.

## License terms

The weights ship under a bespoke "Qwen3.8-Max License", not Apache 2.0. Two thresholds in that license affect commercial deployment:

- **Attribution.** Commercial products or services with more than 100,000,000 monthly active users, or US$20,000,000 monthly revenue, must prominently display the model name.
- **Separate license.** A licensee running a Model as a Service or AI Work Assistant business whose aggregate revenue exceeds US$50,000,000 over any consecutive twelve months must obtain a separate license from Qwen before any commercial use. The license defines Model as a Service as providing third parties access to language-model inference or fine-tuning.

Read the license file before shipping. "Open weight" here means downloadable, not unrestricted.

## Relationship to the hosted `qwen3.8-max`

Model Studio serves a hosted Max tier under the ID `qwen3.8-max`. Treat the hosted service and this weights release as separate surfaces with separate terms; the repo does not have evidence that they are the same artifact or that features documented for one apply to the other.

## Links

- [Hugging Face model card](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B)
- [FP8 weights](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B-FP8)
- [Qwen3.8 release post](https://qwen.ai/blog?id=qwen3.8)
- [Model Studio text models](https://help.aliyun.com/en/model-studio/text-generation-model/)

## Status

`[provider-doc]`. Open-weight release. Benchmark numbers in the release post are Alibaba-reported and are not reproduced here.
