# Claude Sonnet 5 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Provider | Anthropic |
| Model ID | `claude-sonnet-5` |
| Availability | Generally available in the Claude API and supported cloud platforms; available across Claude plans and Claude Code |
| Context / max output | 1M / 128K tokens |
| Modalities | Text and image input; text output |
| Thinking | Adaptive thinking on by default |
| API price per 1M tokens | $2 input, $10 output through August 31, 2026; then $3 / $15 |

## What it is

Claude Sonnet 5 is Anthropic's current balanced tier for coding, tool use, and high-volume professional workflows.

## Integration notes

- Manual extended thinking with `budget_tokens` is removed; use adaptive thinking and effort.
- Non-default `temperature`, `top_p`, or `top_k` values return a 400 response.
- Anthropic says the new tokenizer produces about 30% more tokens than Sonnet 4.6 for the same text. Recount prompts and revisit output limits before migrating.
- Sonnet 5 supports zero data retention for organizations with qualifying agreements.

## Links

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [What's new in Claude Sonnet 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-sonnet-5)
- [Launch announcement](https://www.anthropic.com/news/claude-sonnet-5)
- [System cards index](https://www.anthropic.com/system-cards/)

## Status

`[provider-doc]`. Generally available; introductory API pricing ends August 31, 2026.
