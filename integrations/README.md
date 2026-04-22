# Integrations

**AI glued to the non-AI systems you already use.** This section is a genuine gap in the awesome-AI ecosystem — most lists stop at "here are 50 AI tools." This one shows how to wire AI into existing workflows.

## Sections

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

"I want to use AI in X" where X is not a chat window. The gap between "I have an AI tool" and "my real workflow gets better" is where most AI projects die. This section is the map of that gap.

## Status

Seeding in v0.2.

## What doesn't belong here

- Pure AI tools that happen to have a CLI — those live in `tools/`.
- Chat-interface integrations — if the workflow is "open a chat, paste text, copy result," that's the chat app working as intended, not an integration.
