# Prompt chaining `[provider-doc]`

## One-sentence pitch

Break a complex task into multiple sequential prompts — each one focused, each output feeding the next — instead of cramming everything into one mega-prompt. Provider docs consistently recommend this as a default pattern for non-trivial workflows.

## Evidence

- **Anthropic:** [Chain complex prompts — Claude docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/chain-prompts) — official guide with examples.
- **OpenAI:** [Prompting strategies — OpenAI docs](https://platform.openai.com/docs/guides/prompt-engineering) — recommends breaking complex tasks into simpler subtasks.
- **LangChain, LlamaIndex, and related frameworks** are largely prompt-chaining abstractions by a different name — the pattern is the underlying primitive.

## Why it works

One-shot prompts that try to extract, analyze, synthesize, *and* format all at once tend to fail in predictable ways:
- Format requirements leak into the content.
- Middle-of-haystack context gets ignored.
- The model commits to an answer before it's done gathering information.

Splitting the work gives each model call a clean, narrow job. The separation often outperforms a single call even when the total token count is higher.

## Common chain shapes

- **Extract → analyze → format.** First call extracts structured data, second analyzes it, third formats the final response.
- **Decompose → solve → aggregate.** Least-to-most structure.
- **Generate → critique → refine.** The self-refine pattern (see `prompting/self-refine.md`).
- **Classify → route.** First call picks which specialized prompt/model to call next.

## Practical rules

- **Prompt-cache stable prefixes.** The earlier links in the chain often repeat — the same system prompt, same extraction schema. Cache them (see `prompting/prompt-caching.md`).
- **Pass only what's needed between links.** Don't stuff the full prior output forward if a summary suffices.
- **Validate between links.** If step 1 produces structured output, validate it before feeding into step 2 — errors compound otherwise.
- **Measure before optimizing.** Adding chain links has real cost. If a single good prompt works, don't chain.

## When it's not worth it

- **Simple extractions, summaries, classifications.** One good prompt is cheaper and usually wins.
- **Latency-sensitive paths.** Each link adds a round-trip.

## Related entries

- `prompting/self-refine.md` — generate/critique/refine is a specific chain shape.
- `prompting/prompt-caching.md` — cache the shared prefixes across chain links.
- `agents/plan-and-solve.md` — structured chain-of-steps at agent scale.

## Status

`[provider-doc]`.
