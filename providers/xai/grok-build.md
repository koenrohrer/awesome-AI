# Grok Build `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Surface | Coding agent and command-line interface |
| Interfaces | Interactive terminal UI, headless commands, Agent Client Protocol |
| Default model | `grok-4.5` |
| Extension surfaces | Skills, plugins, hooks, Model Context Protocol servers, subagents |
| Source availability | Open-source repository linked by SpaceXAI |

## What it is

Grok Build is SpaceXAI's coding-agent product surface. It can inspect and edit repositories, run terminal commands, plan changes, and delegate independent work to subagents. Headless mode exposes streaming JSON for scripts and bots.

Grok Build is separate from the Grok 4.5 model API. The product supplies the runtime, local tools, permissions, context management, and extension system; Grok 4.5 supplies the default model.

## Operational boundary

Repository instructions, project configuration, plugins, hooks, and MCP servers can all influence a run. Inspect effective configuration with the documented `grok inspect` command, review permission prompts, and treat third-party extensions as executable supply-chain inputs.

## Links

- [Product page](https://x.ai/build)
- [Documentation](https://docs.x.ai/build/overview)
- [Open-source notice and repository link](https://x.ai/open-source)
- [Changelog](https://x.ai/build/changelog)

## Status

`[provider-doc]`.
