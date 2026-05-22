# Integrations

AI wired into non-AI systems: CI pipelines, shell workflows, automations, no-code flows, and recurring jobs.

## Sections

- **[Automations](automations/)** — scheduled and trigger-based routines, background jobs, and recurring AI workflows
- **[CI/CD](ci-cd/)** — PR review bots, test generation, release-note automation, changelog generation, flaky-test triage
- **[Shell](shell/)** — AI in shell scripts, git hooks (pre-commit, prepare-commit-msg), cron jobs, tmux integrations
- **[No-code](no-code/)** — n8n, Zapier, Make — prompt-driven flows that do real work

## Entry format

```markdown
- **[Pattern or project name](link)** `[vetted-tool]` or `[tested]` — what it does + the surface it plugs into.
  - *Evidence:* repo URL + last commit, OR test directory for maintainer-run examples.
  - *Gotcha:* one sentence of honest caveat.
```

## Why this section exists

This section covers workflows where AI is one step in a larger operational path, not the whole product surface.

## Status

Scaffolded in v0.4. Section primers exist; tested/vetted entries are still being seeded.

## What doesn't belong here

- Pure AI tools that happen to have a CLI — those live in `tools/`.
- Chat-interface integrations — if the workflow is "open a chat, paste text, copy result," that's the chat app working as intended, not an integration.
- First-party product overviews — those live under `providers/` when the main story is the provider-owned surface itself.
