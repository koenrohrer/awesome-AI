# Agents

Building autonomous agents. This section uses the same evidence bar as `prompting/`: `[paper]`, `[provider-doc]`, or `[tested]`.

## Scope

This section is about **building** agents. Using an agent-framework (Claude Code, Cursor, etc.) lives under `extensions/` or `tools/`.

Subtopics we'll cover as entries accumulate:

- **Tool use / function calling** — schemas, error handling, parallel calls
- **Memory** — short-term context, long-term retrieval, memory-augmented agents
- **Planning** — ReAct, Plan-and-Solve, hierarchical planners
- **Multi-agent orchestration** — manager-worker, debate, voting
- **Evaluation** — agent eval harnesses, where SWE-Bench / GAIA / τ-bench fit
- **Hardening** — prompt-injection resistance, tool-output sanitization, sandboxing

## Entries

### Patterns

- **[ReAct: Reasoning + Acting](react.md)** `[paper]` — Interleave reasoning traces, actions, and observations in a tool-use loop.
- **[Toolformer](toolformer.md)** `[paper]` — Training-time tool-use behavior from self-supervised API-call filtering.
- **[Plan-and-Solve prompting](plan-and-solve.md)** `[paper]` — Plan first, then execute; useful when a flat prompt skips subproblems.
- **[Reflexion](reflexion.md)** `[paper]` — Verbal self-reflection after failures, kept in context for the next attempt.
- **[Voyager](voyager.md)** `[paper]` — Open-ended agent loop: automatic curriculum + reusable skill library + environment-grounded feedback.

### Tool use (provider APIs)

- **[Tool use (Anthropic / Claude)](tool-use-anthropic.md)** `[provider-doc]` — `tool_use` / `tool_result` protocol, parallel calls, cacheable tool definitions.
- **[Tool use (OpenAI)](tool-use-openai.md)** `[provider-doc]` — Function calling + hosted tools (`web_search`, `code_interpreter`, etc.) in the Responses API.

### Evaluation

- **[SWE-Bench](swe-bench.md)** `[paper]` — Real GitHub issues for evaluating coding-agent scaffolds.
- **[GAIA: General AI Assistant benchmark](gaia.md)** `[paper]` — 466 multi-tool, multimodal questions for evaluating model plus scaffold behavior.

## Out of scope

- Agent product reviews — those belong in `tools/`.
- Trend commentary without a paper, provider doc, or maintainer-run test.
