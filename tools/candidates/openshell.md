# OpenShell candidate brief

## Candidate

- Name: OpenShell
- URL: https://github.com/NVIDIA/OpenShell
- Likely placement: `tools/`
- One-line scope: Policy-governed sandbox runtime for running autonomous coding agents with constrained filesystem, network, process, and inference access.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:30:18Z`; official repo reports Apache-2.0 license and active issue/PR volume.
- Usage evidence: Blocked for live inclusion. No maintainer-run task for this repo has been recorded.
- Docs/install: Official README documents binary install via `curl -LsSf https://raw.githubusercontent.com/NVIDIA/OpenShell/main/install.sh | sh` and PyPI install via `uv tool install -U openshell`.
- License/pricing: Apache-2.0 license. Requires Docker for the quickstart; GPU support requires NVIDIA drivers and NVIDIA Container Toolkit.
- Risks or caveats: Official README labels the project "Alpha software -- single-player mode" and warns to expect rough edges. GPU passthrough is also marked experimental.

## Inclusion decision

- Verdict: Test-first
- Badge: None yet. Target badge is `[vetted-tool]` after maintainer usage is recorded.
- Rationale: Maintained and sharply scoped, but the project self-identifies as alpha. It should be tested as a sandboxing/runtime tool, not as a production security guarantee.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: OpenShell provides policy-governed sandboxes for running agents such as Claude Code, OpenCode, Codex, Copilot CLI, OpenClaw, and Ollama.
- Required maintainer test: Create a sandbox for one supported agent, apply a read-only GitHub API policy, verify an allowed GET and blocked POST, then record logs and cleanup behavior.
- Entry caveat: Must say alpha and not production-ready; policy coverage depends on the agent and sandbox image.
- Follow-up questions: Should this be tested with Codex, Claude Code, or OpenClaw first?

## Draft entry after maintainer test

- **[OpenShell](https://github.com/NVIDIA/OpenShell)** `[vetted-tool]` — Policy-governed sandbox runtime for constraining autonomous coding agents.
  - *Last commit:* 2026-04-24. *Used for:* maintainer-run task to be filled before promotion. *Scope:* sandboxed agent execution.
  - *Gotcha:* Alpha software; treat policies as a tested constraint layer, not a production security guarantee.

## Sources

- Official repo: https://github.com/NVIDIA/OpenShell
- Official docs: https://docs.nvidia.com/openshell/about/supported-agents
- NVIDIA product page: https://build.nvidia.com/openshell
- GitHub API check: https://api.github.com/repos/NVIDIA/OpenShell
