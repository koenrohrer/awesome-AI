# Anthropic `[provider-doc]`

*Last reviewed: 2026-04-22. Anthropic's primary model family is Claude. Prices and context windows change; verify against [the Anthropic pricing page](https://www.anthropic.com/pricing) before building a cost model.*

## Product surfaces

- **[Claude Code](claude-code.md)** — terminal-native coding workflow with local tools, edits, tests, and permissions.
- **[Claude Desktop](claude-desktop.md)** — desktop app surface with local MCP and desktop extensions.
- **[Claude Design](claude-design.md)** — design/prototyping surface from Anthropic Labs.

## Current models

| Family | Context | Notable feature |
|---|---|---|
| Claude Opus 4.x | 200K (1M beta) | Flagship; deep reasoning, extended thinking |
| Claude Sonnet 4.x | 200K | Balanced cost/quality for most production workloads |
| Claude Haiku 4.x | 200K | Low-latency, high-throughput tier |

Exact pricing and the current version letters (e.g., Opus 4.7, Sonnet 4.6) are listed on the pricing page. The family tiers (Opus/Sonnet/Haiku) are stable; version numbers roll forward.

See [Claude model docs](https://docs.anthropic.com/en/docs/about-claude/models) for specs, context windows, and vision support.

## Strengths (cited)

- **Long-context coding and reasoning.** Anthropic publishes SWE-Bench Verified numbers in model announcements; Claude consistently ranks at or near the top of the public leaderboard at release time. See [swebench.com](https://www.swebench.com/) for current standings.
- **Extended thinking mode.** Controllable reasoning-token budget, with visible reasoning content when enabled. [Extended thinking docs](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking).
- **Prompt caching with generous economics.** Cached input tokens bill at 10% of base; 5-minute TTL by default, extended cache options available. [Prompt caching docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching).
- **Structured tool use.** `tool_use` / `tool_result` block protocol with strict JSON-schema conformance. [Tool use docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use).

## Weaknesses (cited)

- **Multimodal breadth.** Claude supports vision for images, but Anthropic's published multimodal coverage trails OpenAI and Google on audio/video input. Check [supported input types](https://docs.anthropic.com/en/docs/build-with-claude/vision) before assuming parity.
- **No hosted web-search/code-execution by default** in the API the way OpenAI's Responses API exposes `web_search` and `code_interpreter`. The Claude Agent SDK adds some hosted utilities, but parity with OpenAI's hosted tools is not assumed.

## Best-fit tasks

- Long-context code reasoning (whole-repo reads, multi-file edits)
- Agent loops where prompt caching on a stable system-prompt+tools prefix materially reduces cost
- Structured extraction using tool-use schemas
- Tasks where extended thinking's controllable budget maps well to the problem

## Provider-specific quirks

- **XML tags in prompts.** Anthropic explicitly recommends XML tags (`<instructions>`, `<example>`, `<output>`) for structured prompts. Cited in [prompt engineering — use XML tags](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags).
- **System prompt is a top-level field**, not a message. Put stable instructions there for cacheability.
- **Tool definitions go at the top of the request.** Cache them.

## Official docs

- [Models](https://docs.anthropic.com/en/docs/about-claude/models)
- [Prompt engineering](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [Tool use](https://docs.anthropic.com/en/docs/build-with-claude/tool-use)
- [Prompt caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)
- [Extended thinking](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking)
- [Pricing](https://www.anthropic.com/pricing)

## Status

`[provider-doc]`. Prices, benchmark rankings, and exact version numbers rotate — treat this page as a pointer, not a source of truth.
