# Prompt caching `[provider-doc]`

## One-sentence pitch

When the same long prefix (system prompt, tool definitions, reference docs) appears across many requests, prompt caching reuses the KV cache and drops input-token cost by up to ~90% on cached portions, with significant latency reduction.

## Evidence

- **Anthropic:** [Prompt caching — Claude docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching) — states that cache hits are billed at 10% of base input-token cost (90% savings), and cache writes at 125% (one-time premium). TTL is 5 minutes unless using extended cache options.
- **OpenAI:** [Prompt caching — OpenAI docs](https://platform.openai.com/docs/guides/prompt-caching) — automatic caching on eligible long prompts with up to 50% cost savings on cached input tokens and latency reduction.
- **Google:** [Context caching — Gemini docs](https://ai.google.dev/gemini-api/docs/caching) — explicit cache creation with a minimum size (model-dependent) and a configurable TTL.

## What caching actually does

Every provider implements it slightly differently, but the pattern is:

1. You mark a prefix (or one gets auto-detected) as cacheable.
2. First request pays the normal write cost.
3. Subsequent requests within the TTL pay a reduced per-token rate on the cached portion.

## When it pays off

- **High prefix-to-suffix ratio.** System prompt + tool definitions + reference docs (10k+ tokens) shared across many short user queries.
- **Bursty workloads.** Many requests within the TTL window.
- **Agent loops.** Same system prompt and tool definitions across every step of an agent's run.

## When it doesn't

- **One-off requests.** The write premium is a net loss.
- **Rapidly changing prefixes.** If your "static" section actually changes, you pay writes repeatedly.
- **Below minimum cache size.** Small prompts don't qualify on some providers.

## Measurement

Providers return cache-hit metadata (Anthropic: `usage.cache_read_input_tokens` / `usage.cache_creation_input_tokens`; OpenAI: `usage.prompt_tokens_details.cached_tokens`; Gemini: cache handle). Track hit rate — if it's below ~50% in production, revisit your cache boundaries.

## Related entries

- *(coming)* `agents/` — caching matters most in agent loops; will be cross-linked once `agents/` seeds.

## Status

`[provider-doc]`. The specific cost savings are cited from provider docs; actual savings vary with prefix length and hit rate.
