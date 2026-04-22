# Structured output `[provider-doc]`

## One-sentence pitch

Constraining the model's output to a JSON schema eliminates parsing errors and materially reduces hallucinated or missing fields compared to "please return JSON" instructions alone.

## Evidence

- **OpenAI:** [Structured Outputs — OpenAI docs](https://platform.openai.com/docs/guides/structured-outputs) — guarantees the model's response conforms to a provided JSON schema; OpenAI reports 100% schema-compliance on supported models in their announcement.
- **Anthropic:** [Tool use — Claude docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use) — the primary structured-output path on Claude is tool use: define a tool with a JSON input schema, and Claude's `tool_use` block conforms to it.
- **Google:** [Structured output — Gemini docs](https://ai.google.dev/gemini-api/docs/structured-output) — schema-constrained JSON response mode.
- **Open source:** [Outlines](https://github.com/dottxt-ai/outlines) and [Instructor](https://github.com/jxnl/instructor) implement the same constraint for open models via logit masking or retries.

## Why it works

Unconstrained "return JSON" prompting relies on the model *remembering* to emit valid JSON. Any single bad token (a trailing comma, a stray newline) breaks downstream parsing. Structured-output mode masks logits so only tokens that advance toward a valid schema are sampled — there's no path for the model to emit invalid structure.

## Practical rules

- **Keep schemas narrow.** A 40-field schema with deep nesting is harder to get right than five small schemas composed.
- **Use enums for categorical fields.** If a field has 4 valid values, make them an enum — don't rely on free-text validation.
- **Always handle the "don't know" case.** Add a nullable field or a confidence score so the model has a legal way to say "insufficient information" rather than inventing one.
- **Don't put reasoning inside the schema** unless you want it. Schema constraints shrink the model's space — if you also want chain-of-thought, provide a separate reasoning field explicitly.

## When it's the wrong tool

- **Free-form tasks** (essays, summaries, code) — schemas don't help and can hurt.
- **Schemas with very high cardinality enums** — providers have limits on how large an enum can be while remaining performant.

## Related entries

- `prompting/few-shot.md` — for rigid schemas, structured output often replaces the need for examples.

## Status

`[provider-doc]`. Comparative accuracy claims (how much better than "please return JSON" prompting) are not precisely quantified here — upgrade path is a `[tested]` evaluation comparing unconstrained vs constrained on the same task.
