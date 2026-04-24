# OpenClaw candidate brief

## Candidate

- Name: OpenClaw
- URL: https://github.com/openclaw/openclaw
- Likely placement: `tools/`
- One-line scope: Personal AI assistant that runs on user-owned devices and reaches messaging channels through a gateway.

## Evidence snapshot

- Maintenance: Active. GitHub API showed `pushed_at: 2026-04-24T17:36:25Z`; latest GitHub release page showed `openclaw 2026.4.23` published on April 24, 2026.
- Usage evidence: Blocked for live inclusion. No maintainer-run task for this repo has been recorded.
- Docs/install: Official README recommends `npm install -g openclaw@latest` and `openclaw onboard --install-daemon`; it documents macOS, Linux, and Windows via WSL2.
- License/pricing: MIT license; self-hosted. Model/provider and messaging-service costs depend on configured services.
- Risks or caveats: Messaging gateways process untrusted inbound content. The official README explicitly calls out DM pairing/security defaults for real messaging surfaces.

## Inclusion decision

- Verdict: Test-first
- Badge: None yet. Target badge is `[vetted-tool]` after maintainer usage is recorded.
- Rationale: Maintained and scope-fit appear to pass, but OpenClaw is high-blast-radius because it connects models, user devices, messaging channels, skills, and optional automation.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: OpenClaw is a self-hosted personal AI assistant for messaging-native automation across user-owned devices.
- Required maintainer test: Install in a disposable environment, configure one low-risk channel or local CLI path, run one bounded task, and record pairing, permission, and cleanup behavior.
- Entry caveat: Must mention that inbound channel content is untrusted and that pairing/allowlist configuration is part of safe setup.
- Follow-up questions: Which channel should be tested first: local CLI, Telegram, Slack, or Discord?

## Draft entry after maintainer test

- **[OpenClaw](https://github.com/openclaw/openclaw)** `[vetted-tool]` — Self-hosted personal assistant for messaging-native automation on user-owned devices.
  - *Last commit:* 2026-04-24. *Used for:* maintainer-run task to be filled before promotion. *Scope:* messaging-native personal automation.
  - *Gotcha:* Treat inbound DMs and connected channel content as untrusted input.

## Sources

- Official repo: https://github.com/openclaw/openclaw
- Official site: https://openclaw.ai/
- GitHub releases: https://github.com/openclaw/openclaw/releases
- GitHub API check: https://api.github.com/repos/openclaw/openclaw
