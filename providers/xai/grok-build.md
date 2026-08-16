# Grok Build `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Surface | Coding agent and command-line interface |
| Interfaces | Interactive terminal UI, headless commands, Agent Client Protocol |
| Default model | `grok-4.6` |
| Extension surfaces | Skills, plugins, hooks, Model Context Protocol servers, subagents |
| Source availability | Open-source repository linked by SpaceXAI |

## What it is

Grok Build is SpaceXAI's coding-agent product surface. It can inspect and edit repositories, run terminal commands, plan changes, and delegate independent work to subagents. Headless mode exposes streaming JSON for scripts and bots.

Grok Build is separate from the model API. The product supplies the runtime, local tools, permissions, context management, and extension system. The Grok 4.6 developer guide names Grok 4.6 as the default model of the coding agent, on both the API and the CLI. [Grok 4.6 guide](https://docs.x.ai/developers/grok-4-6).

The `grok-build-0.1` model ID is a different thing from this product. It is a 256K-context coding model on the models page and is not documented as the agent's default. See [Grok Build 0.1](models/grok-build-0-1.md).

## Operational boundary

Repository instructions, project configuration, plugins, hooks, and MCP servers can all influence a run. Inspect effective configuration with the documented `grok inspect` command, review permission prompts, and treat third-party extensions as executable supply-chain inputs.

## Links

- [Product page](https://x.ai/build)
- [Documentation](https://docs.x.ai/build/overview)
- [Grok 4.6 developer guide](https://docs.x.ai/developers/grok-4-6)
- [Open-source notice and repository link](https://x.ai/open-source)
- [Changelog](https://x.ai/build/changelog)

## Status

`[provider-doc]`.
