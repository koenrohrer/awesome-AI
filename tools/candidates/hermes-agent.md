# Hermes Agent candidate brief

## Candidate

- Name: Hermes Agent
- URL: https://github.com/NousResearch/hermes-agent
- Likely placement: `tools/`
- One-line scope: Persistent self-hosted agent with memory, skills, messaging gateway, scheduling, and multiple execution backends.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:35:45Z`; public repo reports MIT license, Python implementation, and active issue/PR volume. Official site currently shows Hermes Agent v0.11.0.
- Usage evidence: Maintainer used this wave of tools to autonomously scan a codebase overnight and report back, and to implement small high-confidence, tight-scope fixes. Maintainer impression: useful but clunky.
- Docs/install: Official README and site document install via `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash`, then `hermes setup`.
- License/pricing: MIT license; self-hosted. Model/provider costs depend on configured providers.
- Risks or caveats: Large autonomy surface: persistent memory, messaging gateway, scheduled automations, subagents, browser/web tools, and remote/container backends all need a narrow documented task before recommendation. Maintainer impression: useful, but still clunky.

## Inclusion decision

- Verdict: Include
- Badge: `[vetted-tool]`
- Rationale: Maintained, used by the maintainer on a real autonomous codebase-scanning/fix task, and scope-fit when limited to narrow codebase maintenance workflows.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: Hermes Agent is a self-hosted persistent agent for memory-backed, scheduled, and messaging-surface workflows.
- Required maintainer test: Preserve the overnight codebase-scan/fix task notes: repository shape, scope constraints, provider/model, outputs, accepted fixes, rejected fixes, setup friction, permissions, and cleanup path.
- Entry caveat: Do not recommend for broad personal automation without explicitly noting the security review burden of long-running agents.
- Follow-up questions: Should the public entry emphasize overnight reporting, tight-scope code fixes, or both?

## Draft entry

- **[Hermes Agent](https://github.com/NousResearch/hermes-agent)** `[vetted-tool]` — Self-hosted persistent agent for memory-backed scheduled workflows.
  - *Last commit:* 2026-04-24. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* scheduled self-hosted codebase maintenance.
  - *Gotcha:* Long-running agents need explicit secrets, permissions, and gateway review before use.

## Sources

- Official repo: https://github.com/NousResearch/hermes-agent
- Official site: https://hermes-agent.nousresearch.com/
- GitHub API check: https://api.github.com/repos/NousResearch/hermes-agent
