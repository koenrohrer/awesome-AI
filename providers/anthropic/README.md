# Anthropic `[provider-doc]`

*Last reviewed: 2026-04-23. Anthropic's public Claude lineup changed materially in early 2026; verify exact availability against the [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview), [model deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations), and [system cards index](https://www.anthropic.com/system-cards/) before shipping.*

## Product surfaces

- **[Claude Code](claude-code.md)** — terminal-native coding workflow with local tools, edits, tests, and permissions.
- **[Claude Desktop](claude-desktop.md)** — desktop app surface with local MCP and desktop extensions.
- **[Claude Design](claude-design.md)** — design/prototyping surface from Anthropic Labs.

## Model pages

- [Claude Opus 4.7](models/claude-opus-4-7.md)
- [Claude Opus 4.6](models/claude-opus-4-6.md)
- [Claude Opus 4.5](models/claude-opus-4-5.md)
- [Claude Sonnet 4.6](models/claude-sonnet-4-6.md)
- [Claude Sonnet 4.5](models/claude-sonnet-4-5.md)
- [Claude Haiku 4.5](models/claude-haiku-4-5.md)

## Current models

| Family | Claude API ID | Context | Notable feature |
|---|---|---|---|
| Claude Opus 4.7 | `claude-opus-4-7` | 1M | Current flagship; adaptive thinking, strongest agentic coding |
| Claude Opus 4.6 | `claude-opus-4-6` | 1M | Prior flagship; still active |
| Claude Opus 4.5 | `claude-opus-4-5-20251101` | 1M | Older active Opus snapshot with public system card |
| Claude Sonnet 4.6 | `claude-sonnet-4-6` | 1M | Default balanced tier for most production work |
| Claude Sonnet 4.5 | `claude-sonnet-4-5-20250929` | 1M | Older active Sonnet snapshot |
| Claude Haiku 4.5 | `claude-haiku-4-5-20251001` | 200K | Fastest current Claude tier |

Anthropic's older `claude-opus-4-20250514` and `claude-sonnet-4-20250514` snapshots were deprecated on April 14, 2026 and are scheduled to retire on June 15, 2026. Use the deprecations page, not blog posts, as the source of truth.

## System cards

- [Model system cards index](https://www.anthropic.com/system-cards/) — current landing page for Claude system cards.
- The current index lists system cards for Claude Opus 4.7, Claude Opus 4.6, Claude Opus 4.5, Claude Sonnet 4.6, Claude Sonnet 4.5, and Claude Haiku 4.5.

## Strengths (cited)

- **Long-context coding and reasoning.** Current Opus and Sonnet tiers expose 1M-token context windows. See the [models overview](https://platform.claude.com/docs/en/about-claude/models/overview).
- **Adaptive thinking and effort controls.** Anthropic now distinguishes adaptive thinking from the older explicit thinking-budget path. See [What's new in Claude Opus 4.7](https://platform.claude.com/docs/en/about-claude/models/whats-new-claude-4-7).
- **Prompt caching with strong economics.** Anthropic documents cache discounts and TTL behavior in the [prompt caching docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching).
- **Structured tool use.** `tool_use` / `tool_result` block protocol with strict JSON-schema conformance. [Tool use docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use).

## Weaknesses (cited)

- **Multimodal breadth still trails OpenAI and Google.** Claude supports image input well, but Anthropic's published API surface is still lighter on native audio/video workflows than Gemini and OpenAI. See [vision docs](https://docs.anthropic.com/en/docs/build-with-claude/vision).
- **Hosted tool surface is narrower.** Anthropic does not expose the same built-in web-search / code-execution tool menu that OpenAI exposes in the Responses API.
- **Fast-moving version churn.** The Claude 4.0 snapshots were deprecated less than a year after launch. Pin exact IDs in production and watch the [deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations).

## Best-fit tasks

- Long-context code reasoning and repository work
- Agent loops where prompt caching on a stable system prompt + tools prefix materially reduces cost
- Structured extraction via tool-use schemas
- High-agency knowledge work where adaptive thinking and large outputs matter

## Provider-specific quirks

- **XML tags in prompts.** Anthropic explicitly recommends XML tags (`<instructions>`, `<example>`, `<output>`) for structured prompts. See [prompt engineering — use XML tags](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags).
- **System prompt is a top-level field**, not a message. Keep stable instructions there for better cacheability.
- **Thinking behavior changed across Claude 4 releases.** Opus 4.7 removes the older explicit `budget_tokens` path in favor of adaptive thinking. Do not assume prompt code written for 4.5/4.6 ports cleanly.

## Official docs

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [Model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations)
- [Model cards](https://platform.claude.com/docs/en/resources/overview)
- [System cards index](https://www.anthropic.com/system-cards/)
- [Prompt engineering](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [Tool use](https://docs.anthropic.com/en/docs/build-with-claude/tool-use)
- [Prompt caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)
- [Pricing](https://claude.com/pricing)

## Status

`[provider-doc]`. The active Claude lineup is now concrete enough to document by exact version, but Anthropic rotates snapshots and retirement dates quickly.
