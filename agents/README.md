# Agents

Building autonomous agents. Same evidence bar as `prompting/` — only `[paper]`, `[provider-doc]`, or `[tested]` entries belong here.

## Scope

This section is about **building** agents. Using an agent-framework (Claude Code, Cursor, etc.) lives under `extensions/` or `tools/`.

Subtopics we'll cover as entries accumulate:

- **Tool use / function calling** — schemas, error handling, parallel calls
- **Memory** — short-term context, long-term retrieval, memory-augmented agents
- **Planning** — ReAct, Plan-and-Solve, hierarchical planners
- **Multi-agent orchestration** — manager-worker, debate, voting
- **Evaluation** — agent eval harnesses, where SWE-Bench / GAIA / τ-bench fit
- **Hardening** — prompt-injection resistance, tool-output sanitization, sandboxing

## Status

Seeding in v0.2. This README will fill in as entries land.

## Out of scope

- Agent product reviews — those belong in `tools/`.
- "Is AutoGPT back?" hot takes — if there's a paper or eval, it belongs here; otherwise it doesn't.
