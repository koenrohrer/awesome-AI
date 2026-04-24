# OpenShell candidate brief

## Candidate

- Name: OpenShell
- URL: https://github.com/NVIDIA/OpenShell
- Likely placement: `tools/`
- One-line scope: Policy-governed sandbox runtime for running autonomous coding agents with constrained filesystem, network, process, and inference access.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:30:18Z`; official repo reports Apache-2.0 license and active issue/PR volume.
- Usage evidence: Maintainer used this wave of tools to autonomously scan a codebase overnight and report back, and to implement small high-confidence, tight-scope fixes. Maintainer impression: useful but clunky.
- Docs/install: Official README documents binary install via `curl -LsSf https://raw.githubusercontent.com/NVIDIA/OpenShell/main/install.sh | sh` and PyPI install via `uv tool install -U openshell`.
- License/pricing: Apache-2.0 license. Requires Docker for the quickstart; GPU support requires NVIDIA drivers and NVIDIA Container Toolkit.
- Risks or caveats: Official README labels the project "Alpha software -- single-player mode" and warns to expect rough edges. GPU passthrough is also marked experimental. Maintainer impression: useful, but still clunky.

## Inclusion decision

- Verdict: Include
- Badge: `[vetted-tool]`
- Rationale: Maintained, used by the maintainer on real autonomous codebase-scanning/fix work, and scope-fit as a sandbox runtime for constrained agent execution.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: OpenShell provides policy-governed sandboxes for running agents such as Claude Code, OpenCode, Codex, Copilot CLI, OpenClaw, and Ollama.
- Required maintainer test: Preserve the overnight codebase-scan/fix task notes: agent used, sandbox policy, allowed and blocked operations, outputs, accepted fixes, rejected fixes, logs, and cleanup behavior.
- Entry caveat: Must say alpha and not production-ready; policy coverage depends on the agent and sandbox image.
- Follow-up questions: Which agent was used inside OpenShell during the overnight codebase-scan/fix task?

## Draft entry

- **[OpenShell](https://github.com/NVIDIA/OpenShell)** `[vetted-tool]` — Policy-governed sandbox runtime for constraining autonomous coding agents.
  - *Last commit:* 2026-04-24. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* sandboxed agent execution.
  - *Gotcha:* Alpha software; treat policies as a tested constraint layer, not a production security guarantee.

## Sources

- Official repo: https://github.com/NVIDIA/OpenShell
- Official docs: https://docs.nvidia.com/openshell/about/supported-agents
- NVIDIA product page: https://build.nvidia.com/openshell
- GitHub API check: https://api.github.com/repos/NVIDIA/OpenShell
