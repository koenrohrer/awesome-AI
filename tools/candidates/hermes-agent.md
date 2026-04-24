# Hermes Agent candidate brief

## Candidate

- Name: Hermes Agent
- URL: https://github.com/NousResearch/hermes-agent
- Likely placement: `tools/`
- One-line scope: Persistent self-hosted agent with memory, skills, messaging gateway, scheduling, and multiple execution backends.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:35:45Z`; public repo reports MIT license, Python implementation, and active issue/PR volume. Official site currently shows Hermes Agent v0.11.0.
- Usage evidence: Blocked for live inclusion. No maintainer-run task for this repo has been recorded.
- Docs/install: Official README and site document install via `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash`, then `hermes setup`.
- License/pricing: MIT license; self-hosted. Model/provider costs depend on configured providers.
- Risks or caveats: Large autonomy surface: persistent memory, messaging gateway, scheduled automations, subagents, browser/web tools, and remote/container backends all need a narrow test plan before recommendation.

## Inclusion decision

- Verdict: Test-first
- Badge: None yet. Target badge is `[vetted-tool]` after maintainer usage is recorded.
- Rationale: Maintained and scope-fit appear to pass, but `[vetted-tool]` requires real maintainer usage. The supportable claim should stay limited to self-hosted persistent agent workflows until tested.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: Hermes Agent is a self-hosted persistent agent for memory-backed, scheduled, and messaging-surface workflows.
- Required maintainer test: Install on a disposable VM or container, configure one provider, create a single scheduled report or repo-audit task, and record setup friction, permissions, outputs, and cleanup path.
- Entry caveat: Do not recommend for broad personal automation without explicitly noting the security review burden of long-running agents.
- Follow-up questions: Which provider should be used for the maintainer test? Should the test cover CLI only, or CLI plus a messaging gateway?

## Draft entry after maintainer test

- **[Hermes Agent](https://github.com/NousResearch/hermes-agent)** `[vetted-tool]` — Self-hosted persistent agent for memory-backed scheduled workflows.
  - *Last commit:* 2026-04-24. *Used for:* maintainer-run task to be filled before promotion. *Scope:* scheduled self-hosted agent workflow.
  - *Gotcha:* Long-running agents need explicit secrets, permissions, and gateway review before use.

## Sources

- Official repo: https://github.com/NousResearch/hermes-agent
- Official site: https://hermes-agent.nousresearch.com/
- GitHub API check: https://api.github.com/repos/NousResearch/hermes-agent
