# Awesome AI [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated, **evidence-backed** guide to the AI landscape — prompting, agents, tool extensions, models, self-hosted setups, integrations, and education. Every entry carries a badge showing the evidence behind it. Nothing unlabeled.

Most "awesome AI" lists are vibes-based link dumps. This one isn't. If a technique claims to improve outputs, there's a paper, an official provider doc, or a maintainer-run test backing it. If a tool is listed, it's maintained, used, and fits a specific problem. If a hardware spec is quoted, it cites a third-party source by name.

## Contents

- [Badge legend](#badge-legend)
- [Prompting](#prompting) — evidence-backed techniques
- [Agents](#agents) — building autonomous agents
- [Extensions](#extensions) — skills, hooks, plugins, MCP servers, subagents
- [Models](#models) — per-provider deep dives
- [Self-hosted](#self-hosted) — runners, workflows, hardware
- [Integrations](#integrations) — AI + non-AI (shell, CI/CD, no-code)
- [Learning](#learning) — papers, courses, architecture, safety
- [Tools](#tools) — standalone AI apps
- [Contributing](#contributing)

## Badge legend

| Badge | Meaning |
|---|---|
| `[paper]` | Peer-reviewed paper, arxiv preprint, or official provider research post |
| `[provider-doc]` | Official provider documentation |
| `[tested]` | Maintainer ran it; before/after output lives in `<category>/tests/` |
| `[vetted-tool]` | Maintained (commit within 90 days) + used + scope-fit |
| `[sourced]` | Hardware claim with a named third-party source |

No entry is bare. If something doesn't carry a badge, it doesn't belong.

---

## Prompting

Evidence-backed prompting techniques. This is the flagship section — see [prompting/README.md](prompting/README.md) for the full list and [prompting/tests/](prompting/tests/) for reproducible before/after comparisons.

- **[Chain-of-thought prompting](prompting/chain-of-thought.md)** `[paper]` — "Let's think step by step" lifts reasoning accuracy on multi-step tasks by a double-digit margin on published benchmarks.
- **[Few-shot prompting](prompting/few-shot.md)** `[paper]` — In-context examples outperform zero-shot on most tasks; example count has diminishing returns past ~8.
- **[Prompt caching](prompting/prompt-caching.md)** `[provider-doc]` — Reuse a static prefix across requests to cut cost ~90% and latency materially on repeated long-context calls.
- **[Structured output](prompting/structured-output.md)** `[provider-doc]` — JSON-schema-constrained generation eliminates parsing errors and reduces hallucinated fields.

## Agents

Building agents — not using them. See [agents/README.md](agents/README.md).

*Seeding in v0.2.*

## Extensions

Make your existing AI tool do more. Each extension type is its own curated list:

- **[Skills](extensions/skills/)** — Claude Agent SDK skills and equivalents
- **[Hooks](extensions/hooks/)** — lifecycle hooks in Claude Code and similar tools
- **[Plugins](extensions/plugins/)** — tool-level plugins and addons
- **[MCP Servers](extensions/mcp-servers/)** — Model Context Protocol servers
- **[Subagents](extensions/subagents/)** — specialized agent configurations
- **[Slash commands](extensions/slash-commands/)** — custom commands

*Seeding in v0.2.*

## Models

Per-provider deep dives: available models, context windows, pricing, strengths/weaknesses (cited), best-fit tasks. See [models/README.md](models/README.md).

*Seeding in v0.2 — starting with `claude.md`, `gpt.md`, `gemini.md`.*

## Self-hosted

Running models locally.

- **[Runners](self-hosted/runners/)** — ollama, LMStudio, llama.cpp, vLLM comparisons
- **[Workflows](self-hosted/workflows/)** — local-first setups that work end-to-end
- **[Hardware](self-hosted/hardware/)** — sourced hardware guides, `[sourced]` only

*Seeding in v0.2.*

## Integrations

**AI glued to non-AI systems.** This section is a genuine gap in the ecosystem — most lists stop at "here are 50 AI tools." This one shows you how to wire AI into what you already use.

- **[CI/CD](integrations/ci-cd/)** — PR review bots, test generation, release-note automation
- **[Shell](integrations/shell/)** — AI in shell scripts, git hooks, cron jobs
- **[No-code](integrations/no-code/)** — n8n, Zapier, Make, and similar

*Seeding in v0.2.*

## Learning

- **[Papers](learning/papers/)** — landmark papers with TL;DRs
- **[Courses](learning/courses/)** — vetted courses worth your time
- **[Architecture explainers](learning/architecture/)** — transformers, MoE, diffusion, etc.
- **[Safety](learning/safety/)** — red-teaming, jailbreak resistance, prompt injection

*Seeding in v0.2.*

## Tools

Standalone AI apps that don't fit a category. See [tools/README.md](tools/README.md).

*Seeding in v0.2.*

## Contributing

Every contribution goes through a template that enforces the evidence bar for its track. Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a PR.

Tracks and bars:

- **Techniques** (`prompting/`, `agents/`) — `[paper]`, `[provider-doc]`, or `[tested]` only.
- **Tools** (`extensions/`, `tools/`) — maintained + used + scope-fit.
- **Hardware** (`self-hosted/hardware/`) — third-party source cited by name.

## License

[CC0 1.0 Universal](LICENSE) — public domain dedication. Fork it, copy entries, build on it.
