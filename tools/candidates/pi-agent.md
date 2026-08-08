# Pi Agent candidate brief

## Candidate

- Name: Pi Agent
- URL: https://github.com/earendil-works/pi
- Likely placement: `tools/`
- One-line scope: Minimal terminal coding harness and agent toolkit with a CLI, SDK, unified provider layer, TUI, and extension primitives.

## Evidence snapshot

- Maintenance: Active. The canonical repository is now `earendil-works/pi`. The latest default-branch commit was `6b461b7` at `2026-08-05T21:23:12Z`.
- Usage evidence: Maintainer used this wave of tools to autonomously scan a codebase overnight and report back, and to implement small high-confidence, tight-scope fixes. Maintainer impression: useful with setup friction.
- Docs/install: The official site documents `npm install -g --ignore-scripts @earendil-works/pi-coding-agent` and a first-party install script.
- License/pricing: MIT license; users bring model/provider credentials.
- Risks or caveats: Pi intentionally omits built-in plan mode, subagents, permission popups, background bash, and MCP. Those can be built or installed as extensions, but they are not core defaults. Maintainer impression: useful with setup friction.

## Inclusion decision

- Verdict: Include
- Badge: `[vetted-tool]`
- Rationale: Maintained, used by the maintainer on a real autonomous codebase-scanning/fix task, and scope-fit when limited to customizable terminal coding-agent workflows.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: Pi is a minimal terminal coding agent for developers who want to control prompts, extensions, skills, and provider routing.
- Required maintainer test: Preserve the overnight codebase-scan/fix task notes: repository shape, prompt/constraints, provider/model setup, mode used, outputs, accepted fixes, rejected fixes, and where missing defaults mattered.
- Entry caveat: Must say that common agent features are intentionally left to extensions or user-built workflows.
- Follow-up questions: Which mode was used for the overnight codebase-scan/fix task: interactive TUI, print/JSON mode, or SDK embedding?

## Draft entry

- **[Pi Agent](https://github.com/earendil-works/pi)** `[vetted-tool]` — Minimal terminal coding harness for custom provider, prompt, skill, and extension workflows.
  - *Last commit:* 2026-08-05. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* customizable terminal coding agent.
  - *Gotcha:* Common workflow features are intentionally extension territory, not built-in defaults.

## Sources

- Official repo: https://github.com/earendil-works/pi
- Official site: https://pi.dev/
- GitHub releases: https://github.com/earendil-works/pi/releases
- GitHub API check: https://api.github.com/repos/earendil-works/pi
- Latest verified commit: https://github.com/earendil-works/pi/commit/6b461b75b39b5a19b378dc42fbfbd1655bc446a6
