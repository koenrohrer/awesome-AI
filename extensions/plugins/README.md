# Plugins

Tool-level plugins for IDEs, CLIs, and agents — bundles that add commands, skills, hooks, and MCP servers as a unit.

## Inclusion bar

`[vetted-tool]` — maintained + used + scope-fit. See [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Curated entries

- **[Atomic Agents Claude Code Plugin](https://github.com/BrainBlend-AI/atomic-agents/tree/main/claude-plugin/atomic-agents)** `[vetted-tool]` — Adds Claude Code skills and subagents for Atomic Agents app scaffolding, mapping, and review.
  - *Last commit:* 2026-04-18. *Used for:* assisting maintainer-built agentic workflows and systems. *Scope:* Atomic Agents Python framework development in Claude Code.
  - *Evidence:* official repo, plugin manifest, changelog, and maintainer usage report.
  - *Gotcha:* Use the BrainBlend marketplace path; upstream notes the official marketplace entry was broken in April 2026.
- **[Get Shit Done](https://github.com/gsd-build/get-shit-done)** `[vetted-tool]` — Installs spec-driven AI coding workflows across Claude Code, Codex, Gemini CLI, and OpenCode.
  - *Last commit:* 2026-04-23. *Used for:* building Agent OS and SalesEngine through multi-phase GSD plans. *Scope:* phase planning and execution for AI coding agents.
  - *Evidence:* official repo and npm package metadata; maintainer local projects `agent-os` and `sales-engine` contain GSD planning state.
  - *Gotcha:* Codex support is active but has recent install and hook compatibility issues.
