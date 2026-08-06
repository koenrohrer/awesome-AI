# GPT-5.4 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

- Provider: OpenAI
- Model ID: `gpt-5.4`
- Tier: Older active API tier; GPT-5.6 is current
- Context window: 1.05M tokens
- Max output: 128K tokens
- Official docs: [model page](https://developers.openai.com/api/docs/models/gpt-5.4), [launch post](https://openai.com/index/introducing-gpt-5-4/)
- Official system card docs: [GPT-5.4 Thinking system card](https://openai.com/index/gpt-5-4-thinking-system-card)

## What it is

GPT-5.4 is an older active API model for complex professional work, coding, and agentic workflows. GPT-5.6 is OpenAI's current starting family for new work.

## Official system card in Markdown

This section is a markdown digest of the official OpenAI system card, not a verbatim transcription.

### Capability and product summary

- GPT-5.4 was OpenAI's frontier model for agentic, coding, and professional workflows before GPT-5.5 and GPT-5.6.
- OpenAI highlights native computer use, strong tool orchestration, long-horizon execution, and improved token efficiency versus GPT-5.2.
- The official model page lists broad tool support, including web search, file search, image generation, code interpreter, hosted shell, apply patch, skills, computer use, MCP, and tool search.

### Safety and deployment summary

- OpenAI treats GPT-5.4 as High cyber capability under its Preparedness Framework.
- The GPT-5.4 Thinking system card states that the cyber safety approach builds on the safeguards introduced for GPT-5.3-Codex.
- OpenAI positions the system card as the main public safety document even though the API model ID is `gpt-5.4`.

### Integration notes

- Start new evaluations with GPT-5.6; retain `gpt-5.4` where its behavior is already part of an evaluated contract.
- If you need more raw capability and can tolerate much higher cost/latency, evaluate `gpt-5.4-pro`.
- If you need cheaper subagents, use the mini/nano variants.

## Links

- [Model page](https://developers.openai.com/api/docs/models/gpt-5.4)
- [Launch post](https://openai.com/index/introducing-gpt-5-4/)
- [Official system card](https://openai.com/index/gpt-5-4-thinking-system-card)

## Status

`[provider-doc]`. Active older model; last reviewed 2026-08-06.
