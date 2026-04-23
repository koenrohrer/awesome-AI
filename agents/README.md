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

## Entries

### Patterns

- **[ReAct: Reasoning + Acting](react.md)** `[paper]` — Interleave Thought/Action/Observation; the pattern underlying most modern tool-using agents.
- **[Toolformer](toolformer.md)** `[paper]` — Training-time tool use: the model learns when to emit calls via self-supervised filtering.
- **[Plan-and-Solve prompting](plan-and-solve.md)** `[paper]` — Plan first, then execute; the planner/worker split underlying most agent frameworks.
- **[Reflexion](reflexion.md)** `[paper]` — Verbal self-reflection after failures, kept in context for the next attempt.
- **[Voyager](voyager.md)** `[paper]` — Open-ended agent loop: automatic curriculum + reusable skill library + environment-grounded feedback.

### Tool use (provider APIs)

- **[Tool use (Anthropic / Claude)](tool-use-anthropic.md)** `[provider-doc]` — `tool_use` / `tool_result` protocol, parallel calls, cacheable tool definitions.
- **[Tool use (OpenAI)](tool-use-openai.md)** `[provider-doc]` — Function calling + hosted tools (`web_search`, `code_interpreter`, etc.) in the Responses API.

### Evaluation

- **[SWE-Bench](swe-bench.md)** `[paper]` — Real GitHub issues as the eval; the single most-cited agent-coding benchmark.
- **[GAIA: General AI Assistant benchmark](gaia.md)** `[paper]` — 466 multi-tool, multimodal questions; grades the whole agent stack, not just the model.

## Out of scope

- Agent product reviews — those belong in `tools/`.
- "Is AutoGPT back?" hot takes — if there's a paper or eval, it belongs here; otherwise it doesn't.
