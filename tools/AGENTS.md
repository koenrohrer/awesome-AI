# Agent Guide: Tools

This directory covers standalone AI tools that do not fit a more specific category.

## Evidence Bar

- Use `[vetted-tool]`: maintained, used, and scope-fit.
- Verify the last commit date from the official source.
- Include the maintainer's real task usage and one specific problem solved.

## Placement

- If a tool extends an existing AI tool, prefer `extensions/`.
- If it runs models locally, prefer `self-hosted/runners/`.
- If it wires AI into another workflow, prefer `integrations/`.
