# Agent Guide: Extensions

This directory covers ways to extend existing AI tools: skills, hooks, plugins, MCP servers, subagents, and slash commands.

## Evidence Bar

- Entries are `[vetted-tool]`: maintained, used, and scope-fit.
- Verify upstream maintenance from the official repo or package source.
- Do not add tools only because they are popular. Name the specific problem solved.

## Placement

- `skills/`: procedural docs or configurations that teach an AI tool a workflow.
- `hooks/`: lifecycle callbacks around tool actions.
- `plugins/`: bundles that add commands, skills, hooks, or servers.
- `mcp-servers/`: MCP processes exposing tools, prompts, or resources.
- `subagents/`: named specialist agent configurations.
- `slash-commands/`: reusable command invocations.
