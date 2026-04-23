# Alibaba `[provider-doc]`

*Last reviewed: 2026-04-22. Alibaba's primary open-weight family is Qwen. Verify against [Qwen docs on DashScope](https://help.aliyun.com/zh/dashscope/) and [qwen.ai](https://qwen.ai/) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Qwen3 series | General flagship | Instruct + base variants, open weights on HuggingFace |
| Qwen-VL | Vision-language | Multimodal input |
| Qwen-Code / Qwen-Coder | Code | Code-tuned variants |
| Qwen-Audio | Audio | Audio input |
| Qwen-Math | Math/reasoning | Reasoning-tuned |

Alibaba publishes most Qwen releases as **open weights** on [HuggingFace](https://huggingface.co/Qwen) and [ModelScope](https://modelscope.cn/organization/qwen).

## Strengths (cited)

- **Open weights at scale.** Qwen is the most consistently open-weight among frontier-adjacent Chinese model families. Most major releases land on HuggingFace with permissive licensing for many variants — always verify the specific model card's license.
- **Broad specialist lineup.** Dedicated code (Qwen-Coder), math (Qwen-Math), vision (Qwen-VL), and audio (Qwen-Audio) variants. Useful when a specialist model beats a generalist for a narrow task.
- **Strong community tooling.** Because weights are open, `llama.cpp`, `vLLM`, `ollama`, and others support Qwen models well — often from release day.
- **Competitive benchmark performance.** Qwen3-235B and successors place competitively on public leaderboards (LMSYS arena, OpenLLM, HuggingFace leaderboards) — cross-check the specific variant on your target benchmark.

## Weaknesses (cited)

- **Hosted API friction.** Alibaba's DashScope is the primary hosted API — documentation is primarily in Chinese, though English versions exist. Many Western users access Qwen via third-party hosts (Together, Fireworks, DeepInfra) instead.
- **License variability.** Each Qwen release has its own license file. Some allow commercial use, others restrict it. Read the specific model card before shipping commercially.

## Best-fit tasks

- Self-hosted or cost-controlled inference where open weights are a requirement
- Specialist workloads (code, math, vision, audio) where a dedicated variant beats a generalist
- Chinese-language tasks — Qwen is trained Chinese-first and outperforms Western models on Chinese benchmarks

## Provider-specific quirks

- **Tool-calling schema.** Qwen models have their own tool-calling format; third-party hosts often adapt it to OpenAI-compatible schemas. Check the host's docs.
- **Thinking variants.** Some Qwen3 releases have explicit thinking/reasoning modes — check the model card.

## Official docs

- [qwen.ai](https://qwen.ai/)
- [Qwen on HuggingFace](https://huggingface.co/Qwen)
- [Qwen on ModelScope](https://modelscope.cn/organization/qwen)
- [Qwen on GitHub](https://github.com/QwenLM)

## Status

`[provider-doc]`. Model lineup rotates rapidly; the [QwenLM GitHub org](https://github.com/QwenLM) is the most reliable tracking point.
