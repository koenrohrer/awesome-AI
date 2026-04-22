# Extensions

Make your existing AI tool do more. Every entry is `[vetted-tool]` — maintained (commit within 90 days), used by a maintainer, and solving a specific named problem.

## Sections

- **[Skills](skills/)** — Claude Agent SDK skills and skill-like patterns in other tools
- **[Hooks](hooks/)** — lifecycle hooks (Claude Code, others) that run custom logic before/after tool use
- **[Plugins](plugins/)** — tool-level plugins for IDEs, CLIs, and agents
- **[MCP Servers](mcp-servers/)** — Model Context Protocol servers worth running
- **[Subagents](subagents/)** — specialized agent configurations (role, prompt, tool-set)
- **[Slash commands](slash-commands/)** — custom commands for Claude Code / similar

## Why a section per kind

"AI extensions" collectively cover very different problem shapes. A skill is documentation + conventions; a hook is a lifecycle callback; an MCP server is a running process. Putting them in the same list would muddle the tradeoffs. Each subsection has its own page with a short primer on what the extension type is and when to use it.

## Status

Seeding in v0.2. Each subsection starts with its own README once we have 3+ vetted entries to put in it.

## Inclusion rule recap

1. **Maintained** — commit within 90 days.
2. **Used** — a maintainer ran it on a real task (not just read the README).
3. **Scope-fit** — it names one specific problem. "General assistant" is not a scope.
