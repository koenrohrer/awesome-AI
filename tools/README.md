# Tools

Standalone AI tools and apps that don't fit a more specific category. If a tool *extends* an existing agent (skill, hook, plugin, MCP server), it belongs in [`extensions/`](../extensions/) instead.

## Inclusion bar

`[vetted-tool]` — maintained + used + scope-fit:

1. **Maintained** — commit within 90 days.
2. **Used** — a maintainer ran it on a real task. Describe the task in the entry.
3. **Scope-fit** — names one specific problem the tool solves. "General-purpose AI assistant" is not a scope.

## Entry format

```markdown
- **[Tool name](repo-or-homepage)** `[vetted-tool]` — one sentence: what it is + the specific problem it solves.
  - *Last commit:* YYYY-MM-DD. *Used for:* one real task you ran it on. *Scope:* the one problem.
  - *Gotcha:* (optional) one honest caveat.
```

## Entries

- **[anydoc](https://github.com/firecrawl/anydoc)** `[vetted-tool]` — Local Rust converter turning Office, OpenDocument, EPUB, and PDF files into clean Markdown so agents can read them.
  - *Last commit:* 2026-08-13. *Used for:* converting Office documents to Markdown so coding agents could read them in-context. *Scope:* document-to-Markdown conversion for agent consumption.
  - *Gotcha:* Repository created 2026-08-03 and still on `v0.1.x`; images and embedded objects become alt text, not extracted files.
- **[Hermes Agent](https://github.com/NousResearch/hermes-agent)** `[vetted-tool]` — Self-hosted persistent agent for memory-backed scheduled codebase maintenance.
  - *Last commit:* 2026-08-06. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* scheduled self-hosted codebase maintenance.
  - *Gotcha:* Useful, but long-running agents need explicit secrets, permissions, and gateway review before use.
- **[OpenClaw](https://github.com/openclaw/openclaw)** `[vetted-tool]` — Self-hosted personal assistant for messaging-native codebase maintenance.
  - *Last commit:* 2026-08-06. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* messaging-native codebase maintenance.
  - *Gotcha:* Treat inbound DMs and connected channel content as untrusted input.
- **[OpenShell](https://github.com/NVIDIA/OpenShell)** `[vetted-tool]` — Policy-governed sandbox runtime for constraining autonomous coding agents.
  - *Last commit:* 2026-08-05. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* sandboxed agent execution.
  - *Gotcha:* Alpha software; treat policies as a tested constraint layer, not a production security guarantee.
- **[Pi Agent](https://github.com/earendil-works/pi)** `[vetted-tool]` — Minimal terminal coding harness for custom provider, prompt, skill, and extension workflows.
  - *Last commit:* 2026-08-05. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* customizable terminal coding agent.
  - *Gotcha:* Common workflow features are extension territory, not built-in defaults.

## Status

Seeded in v0.5 with four maintainer-tested, codebase-maintenance scoped tools. anydoc joins as a document-conversion tool for agent consumption, so the directory is no longer scoped to codebase maintenance alone.

## Decision briefs

Detailed decision briefs capture source checks, caveats, and follow-up questions for each entry.

- [anydoc](candidates/anydoc.md)
- [Hermes Agent](candidates/hermes-agent.md)
- [OpenClaw](candidates/openclaw.md)
- [OpenShell](candidates/openshell.md)
- [Pi Agent](candidates/pi-agent.md)

## What doesn't belong

- Paid-only closed-source tools with no free tier — we won't recommend what a reader can't try. Exceptions require a clear justification in the PR.
- Tools whose last commit is older than 90 days. Maintained tools stay in the live list; abandoned tools belong in a future `archived.md`.
