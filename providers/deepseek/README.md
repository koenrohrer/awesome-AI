# DeepSeek `[provider-doc]`

*Last reviewed: 2026-04-22. Verify against [DeepSeek platform docs](https://api-docs.deepseek.com/) before building a cost model.*

## Current model lines

| Model | Role | Notable feature |
|---|---|---|
| DeepSeek V3 (and successors) | General chat | MoE architecture, large total parameters with small active parameter count |
| DeepSeek R1 (and successors) | Reasoning | Explicit reasoning/thinking model |
| DeepSeek Coder | Code | Code-specialized variant |

Most DeepSeek flagship releases are published as **open weights** on [HuggingFace](https://huggingface.co/deepseek-ai).

## Strengths (cited)

- **Reasoning model with open weights.** DeepSeek R1 was among the first broadly-accessible open-weight reasoning models; the accompanying paper described a large-scale RL-based reasoning training recipe. See the [DeepSeek-R1 release on HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-R1) and its associated paper.
- **MoE cost profile.** V3-family models use mixture-of-experts — large parameter counts but smaller *active* parameter counts per token, keeping inference cost lower than dense equivalents at similar quality.
- **Aggressive pricing** on DeepSeek's hosted API relative to Western frontier models. Always cross-check live pricing on [api-docs.deepseek.com](https://api-docs.deepseek.com/) — DeepSeek has historically adjusted pricing frequently.
- **Competitive SWE-Bench and reasoning-benchmark performance.** Model-announcement posts include benchmark tables; cross-check against the [SWE-Bench leaderboard](https://www.swebench.com/) or LMSYS arena for independent numbers.

## Weaknesses (cited)

- **Western hosting considerations.** Some organizations have policy constraints on sending data to China-hosted APIs. For those cases, running open weights locally via `vLLM` or a Western host (Together, Fireworks, Groq) is the path.
- **Documentation depth** lags Anthropic/OpenAI for advanced features (prompt caching, fine-tuning, tool-use edge cases). Community writeups on HuggingFace fill some gaps.
- **Tool-calling ergonomics** have historically varied between releases — verify the current model's function-calling schema against your agent framework.

## Best-fit tasks

- Open-weight reasoning workloads where R1-class capability on self-hosted infrastructure is valuable
- Cost-sensitive API workloads where the pricing delta over Western providers matters
- Research and fine-tuning on frontier-adjacent open weights

## Provider-specific quirks

- **OpenAI-compatible API.** Hosted endpoint mirrors OpenAI format; existing clients generally work with base-URL changes.
- **Thinking output separation.** Reasoning-variant models distinguish thinking content from the final response; handle both when parsing.

## Official docs

- [DeepSeek platform](https://platform.deepseek.com/)
- [API docs](https://api-docs.deepseek.com/)
- [DeepSeek on HuggingFace](https://huggingface.co/deepseek-ai)
- [DeepSeek on GitHub](https://github.com/deepseek-ai)

## Status

`[provider-doc]`. Model lineup and pricing rotate frequently.
