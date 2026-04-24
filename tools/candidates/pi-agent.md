# Pi Agent candidate brief

## Candidate

- Name: Pi Agent
- URL: https://github.com/badlogic/pi-mono
- Likely placement: `tools/`
- One-line scope: Minimal terminal coding harness and agent toolkit with a CLI, SDK, unified provider layer, TUI, and extension primitives.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:33:04Z`; GitHub releases showed v0.70.2 published on April 24, 2026.
- Usage evidence: Blocked for live inclusion. No maintainer-run task for this repo has been recorded.
- Docs/install: Official site documents `npm install -g @mariozechner/pi-coding-agent`; repo points readers to `packages/coding-agent` for installation and usage.
- License/pricing: MIT license; users bring model/provider credentials.
- Risks or caveats: Pi intentionally omits built-in plan mode, subagents, permission popups, background bash, and MCP. Those can be built or installed as extensions, but they are not core defaults.

## Inclusion decision

- Verdict: Test-first
- Badge: None yet. Target badge is `[vetted-tool]` after maintainer usage is recorded.
- Rationale: Maintained and scope-fit appear to pass. The likely live entry should focus on Pi as a minimal coding harness, not as a general-purpose assistant.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: Pi is a minimal terminal coding agent for developers who want to control prompts, extensions, skills, and provider routing.
- Required maintainer test: Install the coding agent, run one small repository-edit task in print/JSON or interactive mode, record model/provider setup, output quality, and where missing defaults mattered.
- Entry caveat: Must say that common agent features are intentionally left to extensions or user-built workflows.
- Follow-up questions: Should the maintainer test cover the interactive TUI, print/JSON mode, or SDK embedding?

## Draft entry after maintainer test

- **[Pi Agent](https://github.com/badlogic/pi-mono)** `[vetted-tool]` — Minimal terminal coding harness for custom provider, prompt, skill, and extension workflows.
  - *Last commit:* 2026-04-24. *Used for:* maintainer-run task to be filled before promotion. *Scope:* customizable terminal coding agent.
  - *Gotcha:* Common workflow features are intentionally extension territory, not built-in defaults.

## Sources

- Official repo: https://github.com/badlogic/pi-mono
- Official site: https://pi.dev/
- GitHub releases: https://github.com/badlogic/pi-mono/releases
- GitHub API check: https://api.github.com/repos/badlogic/pi-mono
