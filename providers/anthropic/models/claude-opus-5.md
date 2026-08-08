# Claude Opus 5 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Provider | Anthropic |
| Model ID | `claude-opus-5` |
| Availability | Generally available in the Claude API and supported cloud platforms; available on Claude Pro, Max, Team, and Enterprise |
| Context / max output | 1M / 128K tokens |
| Modalities | Text and image input; text output |
| Thinking | Adaptive thinking on by default; `low` through `max` effort |
| API price per 1M tokens | $5 input, $25 output |

## What it is

Claude Opus 5 is Anthropic's current Opus tier for complex agentic coding, long-horizon work, and enterprise workflows.

## Integration notes

- Thinking is on by default. Disabling thinking is accepted only at `high` effort or below.
- Fast mode is an API-only research preview and uses separate pricing.
- Mid-conversation tool changes and server-side fallbacks remain beta features with dated headers.
- The model ID is a pinned dateless version, not an evergreen alias.

## Links

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [What's new in Claude Opus 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-opus-5)
- [Launch announcement](https://www.anthropic.com/news/claude-opus-5)
- [Opus product page](https://www.anthropic.com/claude/opus)
- [Model-card resources](https://platform.claude.com/docs/en/resources/overview)

## Status

`[provider-doc]`. Generally available; fast mode and selected API features remain preview/beta.
