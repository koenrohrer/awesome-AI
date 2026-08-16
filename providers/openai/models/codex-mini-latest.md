# codex-mini-latest `[provider-doc]`

*Last reviewed: 2026-08-16. Retired.*

## At a glance

- Provider: OpenAI
- Model ID: `codex-mini-latest`
- Status: Retired. OpenAI shut down API access on February 12, 2026 and marks the snapshot Deprecated on the model page
- Replacement named by OpenAI: `gpt-5-codex-mini`, which no longer has a model page in the current catalog
- Tier when active: Budget Codex helper
- Context window: 200K tokens (100K maximum output)
- Official docs: [model page](https://developers.openai.com/api/docs/models/codex-mini-latest), [deprecations](https://developers.openai.com/api/docs/deprecations)
- Closest public system card docs: [Addendum to GPT-5 system card: GPT-5-Codex](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)

## What it is

`codex-mini-latest` was a fast Codex-oriented model for responsive coding support in the Codex CLI and related tooling. It is no longer callable.

## Retirement

OpenAI announced the deprecation on November 17, 2025 and shut the model down on February 12, 2026, naming `gpt-5-codex-mini` as the replacement. The same announcement dropped support for the legacy local shell tool, which was only available with this model. The later `gpt-5.1-codex-mini` line was shut down on July 23, 2026, with `gpt-5.6-terra` named as its substitute, so no small Codex-specific ID remains in the current catalog. [Deprecations](https://developers.openai.com/api/docs/deprecations), [models page](https://developers.openai.com/api/docs/models).

For a current coding-specialized ID, use [GPT-5.3-Codex](gpt-5-3-codex.md). This page is kept for migration reference.

## Official system card in Markdown

OpenAI does not currently publish a separate public system card specifically for `codex-mini-latest`.

### Relevant official coverage in Markdown

- The public model page says it is optimized for the Codex CLI and is a fine-tuned version of `o4-mini`.
- For public safety context, the closest official Codex-family safety document is the GPT-5-Codex addendum.

## Links

- [Model page](https://developers.openai.com/api/docs/models/codex-mini-latest)
- [Closest official system-card coverage](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)

## Status

`[provider-doc]`. Retired from the API on February 12, 2026.
