# Alibaba `[provider-doc]`

*Last reviewed: 2026-08-16. Alibaba's Qwen catalog spans hosted commercial Model Studio services and open-weight releases, including the Qwen 3.8 open-weight pair. This catalog is date-stamped, not a ranking; verify against the live [Model Studio text-model docs](https://help.aliyun.com/en/model-studio/text-generation-model/) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Qwen 3.8 Max | Current hosted Max tier | `qwen3.8-max`; 1M context, vision input, hybrid thinking, function calling |
| [Qwen3.8-2.4T-A95B](models/qwen3-8-2-4t-a95b.md) | Open-weight Max-class release | 2.4T MoE, 95B activated; 262K context; bespoke Qwen3.8-Max License |
| [Qwen3.8-27B](models/qwen3-8-27b.md) | Open-weight small release | 27B dense vision-language; 262K context; Apache 2.0 |
| Qwen 3.7 Max | Supported legacy Max tier | `qwen3.7-max`; 1M context, hybrid thinking, function calling; not recommended for new integrations |
| Qwen 3.7 Plus | Hosted balanced tier | `qwen3.7-plus`; 1M context, vision input, hybrid thinking, function calling |
| Qwen3 open-weight series | Open deployment family | Model-specific weights and licenses on Hugging Face and ModelScope |
| Qwen-VL | Vision-language | Multimodal input |
| Qwen-Code / Qwen-Coder | Code | Code-tuned variants |
| Qwen-Audio | Audio | Audio input |
| Qwen-Math | Math/reasoning | Reasoning-tuned |

Hosted Model Studio IDs and open-weight repositories are separate surfaces; one does not imply the other. Qwen 3.7 Max/Plus and the hosted `qwen3.8-max` are documented Model Studio services. Qwen 3.8 is separately published as **open weights** in two sizes — the Max-class `Qwen3.8-2.4T-A95B` and the Apache 2.0 `Qwen3.8-27B` — alongside earlier open-weight families on [Hugging Face](https://huggingface.co/Qwen) and [ModelScope](https://modelscope.cn/organization/qwen). Licenses differ per release; check each model card.

## Docs-only current commercial models

| Model | Availability | Operational notes | Evidence |
|---|---|---|---|
| `qwen3.8-max` | Hosted production model | 1M context; vision and text input; hybrid thinking, function calling, built-in tools, and structured output | `[provider-doc]` [text models](https://help.aliyun.com/en/model-studio/text-generation-model/), [thinking models](https://help.aliyun.com/en/model-studio/deep-thinking) |
| `qwen3.7-max` | Supported legacy hosted model | 1M context; hybrid thinking is enabled by default; function calling and built-in tools; Alibaba recommends newer models for new integrations | `[provider-doc]` [text models](https://help.aliyun.com/en/model-studio/text-generation-model/), [thinking models](https://help.aliyun.com/en/model-studio/deep-thinking) |
| `qwen3.7-plus` | Hosted API and Token Plan | 1M context; text and vision input; hybrid thinking, function calling, and built-in tools | `[provider-doc]` [text models](https://help.aliyun.com/en/model-studio/text-generation-model/), [Token Plan](https://help.aliyun.com/en/model-studio/token-plan-personal-overview) |

## Open-weight releases

| Model | Size | Context | License | Evidence |
|---|---|---|---|---|
| [Qwen3.8-2.4T-A95B](models/qwen3-8-2-4t-a95b.md) | 2.4T MoE, 95B activated | 262,144; extensible to 1,010,000 | Qwen3.8-Max License (bespoke; thresholds for attribution and for MaaS resale) | `[provider-doc]` [model card](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B), [release post](https://qwen.ai/blog?id=qwen3.8) |
| [Qwen3.8-27B](models/qwen3-8-27b.md) | 27B dense, vision-language | 262,144; extensible to 1,000,000 | Apache 2.0 | `[provider-doc]` [model card](https://huggingface.co/Qwen/Qwen3.8-27B), [release post](https://qwen.ai/blog?id=qwen3.8) |

Official FP8 variants exist for both (`Qwen/Qwen3.8-2.4T-A95B-FP8`, `Qwen/Qwen3.8-27B-FP8`). Community GGUF, MLX, AWQ, and NVFP4 quantizations are third-party; verify the publisher.

## Strengths (cited)

- **Open-weight deployment path.** Qwen 3.8 and earlier Qwen families have official weights on Hugging Face and ModelScope, including a Max-class release. Always verify the specific model card's license.
- **Broad specialist lineup.** Alibaba documents code, math, vision, audio, and general Qwen families. [Model Studio docs](https://help.aliyun.com/en/model-studio/text-generation-model/).
- **Hosted tool surface.** Model Studio documents thinking, function calling, built-in tools, and structured-output support by model. [Text-model docs](https://help.aliyun.com/en/model-studio/text-generation-model/).

## Weaknesses (cited)

- **Hosted and open-weight releases differ.** A Model Studio ID does not establish weight availability, and a weights repository does not establish that the hosted service is the same artifact; confirm the deployment route for each release.
- **Token Plan has additional constraints.** The Personal Edition is Beijing-region only, restricts keys to interactive coding and agent tools, and authorizes submitted data for service improvement. [Token Plan terms](https://help.aliyun.com/en/model-studio/token-plan-personal-overview).
- **License variability.** Each Qwen release has its own license file. Some allow commercial use, others restrict it. Read the specific model card before shipping commercially.

## Fits

- Self-hosted or cost-controlled inference where open weights are a requirement
- Specialist workloads (code, math, vision, audio) where a dedicated variant fits better than a generalist
- Chinese-language and multilingual tasks that require first-party hosted or open-weight options

## Provider-specific quirks

- **Tool-calling schema.** Qwen models have their own tool-calling format; third-party hosts often adapt it to OpenAI-compatible schemas. Check the host's docs.
- **Thinking variants.** Some Qwen3 releases have explicit thinking/reasoning modes — check the model card.

## Official docs

- [qwen.ai](https://qwen.ai/)
- [Qwen on HuggingFace](https://huggingface.co/Qwen)
- [Qwen on ModelScope](https://modelscope.cn/organization/qwen)
- [Qwen on GitHub](https://github.com/QwenLM)
- [Model Studio text models](https://help.aliyun.com/en/model-studio/text-generation-model/)
- [Thinking models](https://help.aliyun.com/en/model-studio/deep-thinking)

## Status

`[provider-doc]`. Qwen3.8-2.4T-A95B and Qwen3.8-27B have full pages as open-weight releases. Hosted `qwen3.8-max` and Qwen 3.7 Plus are current docs-only hosted entries; Qwen 3.7 Max is retained as supported legacy coverage. The `qwen3.8-max-preview` preview is offline; its old ID redirects to `qwen3.8-max`, so no preview row or dedicated page was added.
