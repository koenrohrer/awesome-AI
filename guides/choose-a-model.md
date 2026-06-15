# How to choose a model or provider

## The Short Version

Start by naming the job before naming the model. A model choice is usually a bundle of tradeoffs: task shape, latency, cost, context length, tool support, structured-output reliability, deployment control, safety review, and vendor churn.

Use the provider pages as a map, not a ranking. They collect official docs and model pages, but provider catalogs move quickly.

Before committing to pricing, context windows, regional availability, deprecation dates, or feature support, verify the live provider docs linked from the relevant provider page.

Choose the smallest surface that can carry the workflow. A chat-only assistant, a schema-constrained extraction service, a retrieval-backed knowledge app, a coding agent, and a self-hosted model all need different evidence.

## Use This Guide When

Use this when you need to compare model options for a product or workflow and want a checklist of what to evaluate. It is not a benchmark leaderboard and does not rank providers.

## Fast Path

- **[Provider model directory](../providers/models/README.md)** `[provider-doc]` — start here for the repo's cross-provider map of seeded model pages and official docs.
- **[Providers](../providers/README.md)** `[provider-doc]` — use the provider overview pages to understand product surfaces, docs, and vendor-specific caveats.
- **[Structured output](../prompting/structured-output.md)** `[provider-doc]` — check whether the workflow needs schema-constrained responses rather than free text.
- **[Tool use with OpenAI](../agents/tool-use-openai.md)** `[provider-doc]` — read a concrete tool-calling protocol before choosing a model for agent loops or function calling.
- **[Extended thinking / reasoning modes](../prompting/extended-thinking.md)** `[provider-doc]` — use for hard reasoning paths where added latency and cost may be justified.
- **[Prompt caching](../prompting/prompt-caching.md)** `[provider-doc]` — read before designing high-volume workflows with repeated long prefixes.
- **[Retrieval-augmented generation](../learning/architecture/rag.md)** `[paper]` — use this to decide when missing knowledge belongs outside the model.

## Decision Points

**Task type.** Separate open-ended writing, structured extraction, code work, tool-using agents, multimodal analysis, and retrieval-backed QA. A model that is convenient for chat may not expose the right schema, tool, or multimodal surface.

**Provider surface.** Decide whether you need an API model, a product surface, an agent runtime, open weights, or local deployment. The provider overviews distinguish these where the repo has coverage.

**Context strategy.** Long context can simplify prototypes, but it is not a substitute for retrieval, summarization, or cache-aware design. Use the RAG, KV cache, tokenization, and prompt-caching entries to decide what belongs in the prompt.

**Output contract.** If downstream software consumes the answer, evaluate structured output and tool-use support before prose quality. JSON-shaped prompting is not the same as provider-enforced schema output.

**Tool loop.** Agent workflows depend on schema design, tool descriptions, parallel calls, permissions, and result handling. Pick the provider surface whose tool protocol matches the control you need.

**Latency and cost.** Reasoning modes, long context, large outputs, hosted tools, cache writes, and multimodal inputs change cost and latency. Do not reuse old pricing notes; verify live provider docs before shipping.

**Operational control.** Open-weight models can help with deployment control, adaptation, and third-party hosting choices, but they shift responsibility for serving, safety, evaluation, and updates onto the team.

**Evaluation.** Use a task-specific eval or pilot. Avoid choosing from generic leaderboard impressions unless the benchmark methodology matches the work you will run.

## Field Notes

Provider docs are the source of record for current availability. This repo can organize the evidence, but it should not be treated as a live pricing or deprecation feed.

Model families are not interchangeable. Feature support can differ across aliases, sizes, reasoning variants, product surfaces, and open-weight releases. Check the exact model page before assuming context length, tools, structured output, or multimodal support.

Reasoning modes are a workflow choice, not a universal upgrade. They are most relevant when the task needs multi-step reasoning and can tolerate extra latency and token use.

Prompt caching matters most when the static prefix is large and repeated. It is less useful for one-off prompts or constantly changing context.

RAG and fine-tuning solve different problems. Retrieval is the usual first move for changing private knowledge; fine-tuning is a behavior-adaptation lever.

## What To Avoid

- Do not rank providers without a dated benchmark, named methodology, and task match.
- Do not quote current prices, context windows, or availability from memory.
- Do not choose a model only because a provider markets it as the top tier.
- Do not treat a product-only model, API model, and open-weight artifact as the same deployment option.
- Do not rely on "return JSON" prompting where provider-enforced structured output is available.
- Do not use long context to hide missing retrieval, citation, or source-quality decisions.
- Do not assume tool-calling schemas port cleanly across providers without adaptation.

## Evidence Library

- **[Provider model directory](../providers/models/README.md)** `[provider-doc]` — cross-provider index of seeded model pages and official model docs.
- **[Anthropic](../providers/anthropic/README.md)** `[provider-doc]` — Claude model families, product surfaces, tool use, prompt caching, and deprecation caveats.
- **[OpenAI](../providers/openai/README.md)** `[provider-doc]` — GPT model lines, Codex surfaces, hosted tools, structured output, and catalog caveats.
- **[Google](../providers/google/README.md)** `[provider-doc]` — Gemini API models, Gemma open weights, multimodal surfaces, and Google-specific product tracks.
- **[DeepSeek](../providers/deepseek/README.md)** `[provider-doc]` — hosted and open-weight model lines, reasoning modes, and alias/deprecation notes.
- **[Meta](../providers/meta/README.md)** `[provider-doc]` — Llama open-weight pages, model cards, and safeguard-model links.
- **[Mistral](../providers/mistral/README.md)** `[provider-doc]` — proprietary and open-weight tracks, MoE notes, and licensing caveats.
- **[Structured output](../prompting/structured-output.md)** `[provider-doc]` — schema-constrained generation for software-facing responses.
- **[Tool use with OpenAI](../agents/tool-use-openai.md)** `[provider-doc]` — OpenAI tool and function-calling loop.
- **[Tool use with Anthropic](../agents/tool-use-anthropic.md)** `[provider-doc]` — Claude tool-use protocol and schema contract.
- **[Extended thinking / reasoning modes](../prompting/extended-thinking.md)** `[provider-doc]` — provider-native reasoning-budget controls.
- **[Prompt caching](../prompting/prompt-caching.md)** `[provider-doc]` — repeated-prefix caching and cache-hit measurement.
- **[Retrieval-augmented generation](../learning/architecture/rag.md)** `[paper]` — retrieval as updateable external memory.
- **[Fine-tuning and LoRA](../learning/architecture/fine-tuning-lora.md)** `[paper]` — weight adaptation for stable behavior changes.
- **[KV cache and PagedAttention](../learning/architecture/kv-cache.md)** `[paper]` — serving bottlenecks behind long-context inference.
- **[Tokenization](../learning/architecture/tokenization.md)** `[paper]` — token counts, context budgeting, and multilingual/code-heavy edge cases.
