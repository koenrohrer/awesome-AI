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

## Status

Seeding in v0.2.

## Examples of candidates the maintainer wants to vet

(Unvetted until they pass the bar — listed here only to scope what v0.2 will evaluate.)

- Get-Shit-Done
- OpenClaw
- Hermes Agent

## What doesn't belong

- Paid-only closed-source tools with no free tier — we won't recommend what a reader can't try. Exceptions require a clear justification in the PR.
- Tools whose last commit is older than 90 days. If it's good but abandoned, it goes in a future `archived.md` — not the live list.
