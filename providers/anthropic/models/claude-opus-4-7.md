# Claude Opus 4.7 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

- Provider: Anthropic
- Model ID: `claude-opus-4-7`
- Tier: Older active Opus tier; Opus 5 is current
- Context window: 1M tokens
- Max output: 128K tokens
- Official docs: [models overview](https://platform.claude.com/docs/en/about-claude/models/overview), [What's new in Claude Opus 4.7](https://platform.claude.com/docs/en/about-claude/models/whats-new-claude-4-7)
- Official system card docs: [Anthropic system cards index](https://www.anthropic.com/system-cards/)

## What it is

Claude Opus 4.7 is an older active Opus model for complex reasoning, agentic coding, long-horizon work, and vision tasks. Opus 5 is the current Opus tier.

## Official system card in Markdown

This section is a markdown digest of Anthropic's official system-card material and launch documentation, not a verbatim transcription.

### Capability and product summary

- Opus 4.7 preceded Opus 5 as Anthropic's top API model for advanced software-engineering and knowledge-work tasks.
- Anthropic documents 1M-token context, 128K-token max output, adaptive thinking, and a new `xhigh` effort level.
- The release notes call out stronger long-running task execution, better self-verification, and improved high-resolution image support.

### Safety and deployment summary

- Anthropic lists a public system card for Claude Opus 4.7 on its system-cards index.
- The Opus 4.7 launch notes emphasize new safeguards around cybersecurity misuse and position the model below Mythos Preview in cyber capability.
- Anthropic documents breaking API changes versus earlier Opus releases, including the move away from the older explicit thinking-budget pattern.

### Integration notes

- Start new Opus evaluations with Opus 5; retain `claude-opus-4-7` where its behavior is already evaluated or pinned.
- Review the migration notes if you previously depended on explicit thinking budgets or non-default sampling controls.

## Links

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [What's new in Claude Opus 4.7](https://platform.claude.com/docs/en/about-claude/models/whats-new-claude-4-7)
- [System cards index](https://www.anthropic.com/system-cards/)
- [Launch announcement](https://www.anthropic.com/news/claude-opus-4-7)

## Status

`[provider-doc]`. Active older model; last reviewed 2026-08-06.
