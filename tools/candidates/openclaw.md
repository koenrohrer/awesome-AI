# OpenClaw candidate brief

## Candidate

- Name: OpenClaw
- URL: https://github.com/openclaw/openclaw
- Likely placement: `tools/`
- One-line scope: Personal AI assistant that runs on user-owned devices and reaches messaging channels through a gateway.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:36:25Z`; latest GitHub release page showed `openclaw 2026.4.23` published on April 24, 2026.
- Usage evidence: Maintainer used this wave of tools to autonomously scan a codebase overnight and report back, and to implement small high-confidence, tight-scope fixes. Maintainer impression: useful but clunky.
- Docs/install: Official README recommends `npm install -g openclaw@latest` and `openclaw onboard --install-daemon`; it documents macOS, Linux, and Windows via WSL2.
- License/pricing: MIT license; self-hosted. Model/provider and messaging-service costs depend on configured services.
- Risks or caveats: Messaging gateways process untrusted inbound content. The official README explicitly calls out DM pairing/security defaults for real messaging surfaces. Maintainer impression: useful, but still clunky.

## Inclusion decision

- Verdict: Include
- Badge: `[vetted-tool]`
- Rationale: Maintained, used by the maintainer on a real autonomous codebase-scanning/fix task, and scope-fit when limited to messaging-native codebase maintenance workflows.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: OpenClaw is a self-hosted personal AI assistant for messaging-native automation across user-owned devices.
- Required maintainer test: Preserve the overnight codebase-scan/fix task notes: repository shape, scope constraints, channel/local path, outputs, accepted fixes, rejected fixes, pairing, permissions, and cleanup behavior.
- Entry caveat: Must mention that inbound channel content is untrusted and that pairing/allowlist configuration is part of safe setup.
- Follow-up questions: Should the public entry emphasize local/device ownership or messaging-native operation?

## Draft entry

- **[OpenClaw](https://github.com/openclaw/openclaw)** `[vetted-tool]` — Self-hosted personal assistant for messaging-native automation on user-owned devices.
  - *Last commit:* 2026-04-24. *Used for:* overnight codebase scan/report and small tight-scope fixes. *Scope:* messaging-native codebase maintenance.
  - *Gotcha:* Treat inbound DMs and connected channel content as untrusted input.

## Sources

- Official repo: https://github.com/openclaw/openclaw
- Official site: https://openclaw.ai/
- GitHub releases: https://github.com/openclaw/openclaw/releases
- GitHub API check: https://api.github.com/repos/openclaw/openclaw
