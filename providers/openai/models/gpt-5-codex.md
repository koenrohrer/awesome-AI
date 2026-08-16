# GPT-5-Codex `[provider-doc]`

*Last reviewed: 2026-08-16. Retired.*

## At a glance

- Provider: OpenAI
- Model ID: `gpt-5-codex`
- Status: Retired. OpenAI shut down API access on July 23, 2026 and marks the snapshot Deprecated on the model page
- Replacement named by OpenAI: `gpt-5.6-sol`
- Tier when active: Dedicated Codex coding model
- Context window: 400K tokens (272K maximum input, 128K maximum output)
- Official docs: [model page](https://developers.openai.com/api/docs/models/gpt-5-codex), [deprecations](https://developers.openai.com/api/docs/deprecations)
- Official system card docs: [Addendum to GPT-5 system card: GPT-5-Codex](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)

## What it is

GPT-5-Codex was a GPT-5 variant optimized for agentic coding tasks in Codex and similar environments. It is no longer callable.

## Retirement

OpenAI announced the deprecation on April 22, 2026 and shut the model down on July 23, 2026, together with `gpt-5.1-codex`, `gpt-5.1-codex-max`, `gpt-5.1-codex-mini`, and `gpt-5.2-codex`. The deprecations page names `gpt-5.6-sol` as the substitute. [Deprecations](https://developers.openai.com/api/docs/deprecations).

For a current coding-specialized ID, use [GPT-5.3-Codex](gpt-5-3-codex.md). This page is kept for migration reference.

## Official system card in Markdown

This section is a markdown digest of OpenAI's GPT-5-Codex addendum, not a verbatim transcription.

### Capability and product summary

- OpenAI says GPT-5-Codex was trained for real-world coding tasks in varied environments.
- The addendum frames it as a model tuned to behave more like a software-engineering colleague: following instructions, iterating, and running tests until results are correct.

### Safety and deployment summary

- OpenAI's addendum focuses on both model-level mitigations and product-level mitigations such as agent sandboxing and configurable network access.
- The safety story is presented as an extension of the GPT-5 system-card framework rather than a separate new framework.

## Links

- [Model page](https://developers.openai.com/api/docs/models/gpt-5-codex)
- [Official system card addendum](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)
- [GPT-5 system card](https://openai.com/blog/gpt-5-system-card/)

## Status

`[provider-doc]`. Retired from the API on July 23, 2026.
