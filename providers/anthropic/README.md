# Anthropic `[provider-doc]`

*Last reviewed: 2026-08-06. Anthropic's current lineup spans generally available Fable, Opus, Sonnet, and Haiku models plus the limited-access Mythos line. Verify lifecycle status against the [models overview](https://platform.claude.com/docs/en/about-claude/models/overview) and [deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations).*

## Product surfaces

- **[Claude Code](claude-code.md)** — terminal-native coding workflow with local tools, edits, tests, and permissions.
- **[Claude Desktop](claude-desktop.md)** — desktop app surface with local MCP and desktop extensions.
- **[Claude Design](claude-design.md)** — design/prototyping surface from Anthropic Labs.

## Model pages

- [Claude Fable 5](models/claude-fable-5.md)
- [Claude Mythos 5](models/claude-mythos-5.md)
- [Claude Opus 5](models/claude-opus-5.md)
- [Claude Sonnet 5](models/claude-sonnet-5.md)
- [Claude Opus 4.7](models/claude-opus-4-7.md)
- [Claude Opus 4.6](models/claude-opus-4-6.md)
- [Claude Opus 4.5](models/claude-opus-4-5.md)
- [Claude Sonnet 4.6](models/claude-sonnet-4-6.md)
- [Claude Sonnet 4.5](models/claude-sonnet-4-5.md)
- [Claude Haiku 4.5](models/claude-haiku-4-5.md)

## Current models

| Family | Claude API ID | Availability | Context / max output | Input / output per 1M tokens |
|---|---|---|---|---|
| Claude Fable 5 | `claude-fable-5` | Generally available | 1M / 128K | $10 / $50 |
| Claude Mythos 5 | `claude-mythos-5` | Limited Project Glasswing access | 1M / 128K | $10 / $50 |
| Claude Opus 5 | `claude-opus-5` | Generally available | 1M / 128K | $5 / $25 |
| Claude Sonnet 5 | `claude-sonnet-5` | Generally available | 1M / 128K | $2 / $10 through August 31; then $3 / $15 |
| Claude Haiku 4.5 | `claude-haiku-4-5-20251001` | Generally available | 200K / 64K | $1 / $5 |

Anthropic also lists Opus 4.8, 4.7, 4.6, and 4.5 and Sonnet 4.6 and 4.5 as active. The deprecations page is authoritative for the Claude API: it records Opus 4.1 as retired on August 5, 2026 and the original Opus 4 and Sonnet 4 snapshots as retired on June 15, 2026.

## Availability boundaries

- **Fable 5:** generally available in the Claude API and supported cloud platforms. After its June suspension, Anthropic restored product access globally on July 1; subscription use requires usage credits after July 7.
- **Mythos 5:** limited to approved Project Glasswing customers. It is not a generally available or self-serve API option.
- **Opus 5:** generally available in the API and cloud platforms and available to Claude Pro, Max, Team, and Enterprise users.
- **Sonnet 5:** generally available in the API and cloud platforms and available across Claude plans and Claude Code.

## Model cards

- [Model-card resources](https://platform.claude.com/docs/en/resources/overview) — current Claude model-card documents.
- [System cards index](https://www.anthropic.com/system-cards/) — public system-card landing page.
- [Fable 5 and Mythos 5 system card](https://www-cdn.anthropic.com/2f9323abbcc4abe219577539efe19a623c9ca2bd/Claude%20Fable%205%20%26%20Claude%20Mythos%205%20System%20Card.pdf).

## Strengths (cited)

- **Long-context current tiers.** Fable 5, Opus 5, and Sonnet 5 expose 1M-token context and 128K-token synchronous output. [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview).
- **Effort controls and adaptive thinking.** Current Fable, Opus, and Sonnet lines expose model-specific thinking and effort behavior. Read the [models overview](https://platform.claude.com/docs/en/about-claude/models/overview) and model migration guides before changing aliases.
- **Structured tool protocol.** Anthropic documents `tool_use` and `tool_result` blocks with JSON schemas in the [tool-use guide](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview).
- **Prompt caching.** Anthropic documents cache pricing, minimums, and time-to-live behavior in the [prompt-caching guide](https://platform.claude.com/docs/en/build-with-claude/prompt-caching).

## Weaknesses (cited)

- **Model-specific breaking changes.** Sonnet 5 changes tokenization and rejects manual thinking budgets and non-default sampling parameters. [What's new in Sonnet 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-sonnet-5).
- **Fable refusal handling is part of the API contract.** Classifier refusals return HTTP 200 with `stop_reason: "refusal"`; integrations need an explicit fallback policy. [Fable and Mythos API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5).
- **Mythos access and retention are restrictive.** Mythos is invitation-only, and both Fable and Mythos require 30-day retention rather than zero data retention. [Fable and Mythos API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5).
- **Lifecycle churn requires active monitoring.** Pin exact IDs and watch the [deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations).

## Fits

- Long-context code reasoning and repository work
- Agent loops that benefit from prompt caching and effort controls
- Structured extraction through tool-use schemas
- Long-horizon knowledge work with explicit lifecycle and fallback handling

## Provider-specific quirks

- **Dateless IDs are pinned.** Starting with Claude 4.6, IDs such as `claude-opus-5` identify fixed versions rather than evergreen aliases. [Model IDs and versioning](https://platform.claude.com/docs/en/about-claude/models/model-ids-and-versions).
- **Thinking behavior varies by generation.** The Fable/Mythos [API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5) keeps adaptive thinking on, while the Opus and Sonnet migration guides document their controls.
- **Refusals can be successful API responses.** Treat `stop_reason: "refusal"` as a control-flow state, not a transport error. [Fable and Mythos API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5).

## Official docs

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [Model IDs and versioning](https://platform.claude.com/docs/en/about-claude/models/model-ids-and-versions)
- [Model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations)
- [Fable 5 and Mythos 5 API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5)
- [What's new in Claude Opus 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-opus-5)
- [What's new in Claude Sonnet 5](https://platform.claude.com/docs/en/about-claude/models/whats-new-sonnet-5)
- [Pricing](https://platform.claude.com/docs/en/about-claude/pricing)

## Status

`[provider-doc]`. Fable, Opus, Sonnet, and Haiku are generally available; Mythos remains restricted to approved Project Glasswing customers.
