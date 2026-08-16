# GPT-5.3 Instant `[provider-doc]`

*Last reviewed: 2026-08-16. API access retired.*

## At a glance

- Provider: OpenAI
- API ID when active: `gpt-5.3-chat-latest`. There is no `gpt-5.3-instant` model page in the OpenAI catalog
- Status: Retired. OpenAI shut down `gpt-5.3-chat-latest` on August 10, 2026
- Replacement named by OpenAI: `gpt-5.6-sol`
- Tier when active: Fast GPT-5-series conversational model
- Official docs: [deprecations](https://developers.openai.com/api/docs/deprecations), [models page](https://developers.openai.com/api/docs/models)
- Official system card docs: [GPT-5.3 Instant system card](https://openai.com/index/gpt-5-3-instant-system-card/)

## What it is

GPT-5.3 Instant was OpenAI's fast GPT-5-series model oriented toward lower-latency responses and better web-search flow. It reached the API through the `gpt-5.3-chat-latest` snapshot released on March 3, 2026, which pointed at the GPT-5.3 Instant model then used in ChatGPT. [Changelog](https://developers.openai.com/api/docs/changelog).

## Retirement and successor

OpenAI announced the deprecation of `gpt-5.2-chat-latest` and `gpt-5.3-chat-latest` on May 8, 2026 and shut both down on August 10, 2026, naming `gpt-5.6-sol` as the substitute. [Deprecations](https://developers.openai.com/api/docs/deprecations).

The current equivalent is the unversioned [`chat-latest`](https://developers.openai.com/api/docs/models/chat-latest) slug, which points at whichever Instant model ChatGPT is running. It carries a 400K context window, 128K maximum output, and $5 input / $30 output per 1M tokens, and OpenAI recommends GPT-5.6 Sol rather than `chat-latest` for production API use. Because the pointer moves without a version bump, it is unsuitable for evaluated workloads.

## Official system card in Markdown

This section is a markdown digest of the official OpenAI system card, not a verbatim transcription.

### Capability and product summary

- OpenAI describes GPT-5.3 Instant as a faster GPT-5-series model with richer, better-contextualized answers when searching the web.
- The system card frames it as a newer addition to the GPT-5 family rather than a standalone safety regime.

### Safety and deployment summary

- OpenAI says the safety mitigation approach is largely the same as for GPT-5.2 Instant.
- The system card is the main public safety document for this model.

## Links

- [Official system card](https://openai.com/index/gpt-5-3-instant-system-card/)
- [Deprecations](https://developers.openai.com/api/docs/deprecations)
- [`chat-latest` model page](https://developers.openai.com/api/docs/models/chat-latest)

## Status

`[provider-doc]`. `gpt-5.3-chat-latest` was retired from the API on August 10, 2026.
