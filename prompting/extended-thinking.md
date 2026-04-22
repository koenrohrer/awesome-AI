# Extended thinking / reasoning modes `[provider-doc]`

## One-sentence pitch

Let the model spend more tokens "thinking" before answering — providers expose this as a dedicated mode (Claude extended thinking, OpenAI reasoning models, Gemini thinking) that improves performance on hard reasoning tasks at higher latency and cost.

## Evidence

- **Anthropic:** [Extended thinking — Claude docs](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking) — gates a dedicated reasoning phase before the final response; token budget is controllable.
- **OpenAI:** [Reasoning models — OpenAI docs](https://platform.openai.com/docs/guides/reasoning) — o-series models use reasoning tokens internally; controllable via `reasoning_effort`.
- **Google:** [Thinking — Gemini docs](https://ai.google.dev/gemini-api/docs/thinking) — Gemini 2.5 series exposes thinking as a configurable budget.

## What the provider docs establish

Each provider ships a mode where the model is trained (via RL and/or long-context reasoning traces) to produce extended intermediate reasoning before emitting a user-facing response. The reasoning is typically billed as output tokens; some providers let you inspect it, others hide it.

Reported gains are concentrated on:
- Competition math (AIME, MATH)
- Code generation with multi-step reasoning (LiveCodeBench, SWE-Bench)
- Scientific QA (GPQA)
- Complex multi-step agent tasks

## Practical rules

- **Don't use it for everything.** Latency and cost both rise meaningfully. Simple extractions, summaries, or classifications rarely benefit.
- **Set a budget.** Each provider lets you cap the reasoning-token count. Use it. Otherwise a single prompt can burn thousands of tokens on navel-gazing.
- **Don't pair with client-side self-consistency** or external chain-of-thought orchestration. The model's internal reasoning already does this; wrapping it in more sampling usually regresses quality and always regresses cost.
- **Reasoning content is usually not user-facing.** If you need the chain-of-thought visible to the user, either ask for it in the final answer or use classic CoT prompting on a non-reasoning model.

## When classic prompting still wins

- **Latency-critical paths.** Reasoning tokens add seconds, sometimes minutes.
- **Formatting-heavy tasks.** Reasoning models can over-reason simple JSON schemas; a schema-constrained non-reasoning model is faster and equally reliable.
- **Transparent audits.** If an audit trail of reasoning is required, classic CoT in the visible output is more reliable than provider-hidden reasoning tokens.

## Related entries

- `prompting/chain-of-thought.md` — the client-side precursor to this mode.
- `prompting/self-consistency.md` — largely supplanted by reasoning-mode internals.

## Status

`[provider-doc]`. Quantitative gains are provider-reported; upgrade path would be an external eval (e.g., GPQA or SWE-Bench-Lite) comparing reasoning-on vs reasoning-off on the same model family.
