# Agent loop `[provider-doc]`

## One-sentence TL;DR

An agent loop repeatedly chooses an action, observes the result, updates its working state, and either continues, stops, or escalates.

## What the loop controls

A minimal loop has five responsibilities:

1. **Plan or select** the next action from the current goal and observations.
2. **Act** through a narrowly described tool or return a final answer.
3. **Observe** the structured result, including errors and side effects.
4. **Evaluate** progress against an explicit success or failure signal.
5. **Stop, retry, or escalate** according to policy.

This is a control cycle, not a guarantee of autonomy. A workflow can use one loop inside a single process, several loops at different graph nodes, or no model-directed loop at all.

## Budgets and termination

Every production loop needs limits that are independent of the model:

- maximum model turns, tool calls, elapsed time, and spend;
- per-tool timeouts and retry limits;
- a definition of success, terminal failure, and lack of progress;
- idempotency or duplicate-action protection for side-effecting tools;
- an escalation path when the agent lacks permission, evidence, or a safe next step.

Retry only when the observation distinguishes a transient failure from a bad plan. Repeating the same call with the same state is not recovery. When a budget expires, preserve the latest verified state and explain what remains rather than inventing completion.

## Tool and observation boundaries

Treat tool output as untrusted input. Validate schemas, cap output size, keep provenance for retrieved material, and prevent instructions inside documents or webpages from silently changing the agent's authority. Give read and write tools separate permissions, and require review for high-impact actions.

An observation should be useful to the next decision: result data, error class, side effects, and stable identifiers. Raw logs and entire documents often consume the context budget without improving the decision.

## Evaluation

Evaluate the whole loop, not only the model response. Record the model and prompt, tool inventory, permission policy, retry and stopping rules, state passed between turns, and grader. Useful measures include task success, unsafe or duplicate actions, retries, tool errors, latency, cost, and human escalations.

## Official references

- [Claude Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) — describes the built-in agent loop, tools, permissions, sessions, and observability surface.
- [LangGraph workflows and agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents) — distinguishes predetermined workflows from agents that choose their own process and tool usage.
- [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/) — documents agents, handoffs, guardrails, sessions, tracing, and the built-in loop.

## Related entries

- [ReAct](react.md) — a paper-backed reasoning-and-action pattern commonly implemented as a loop.
- [Graph-structured orchestration](graph-structured-orchestration.md) — topology for branches, cycles, fan-out, and handoffs.
- [Agent harnesses](../learning/architecture/agent-harnesses.md) — the runtime boundary around the loop.
- [Indirect prompt injection](../learning/safety/indirect-prompt-injection.md) — the threat model for agents that read untrusted content.

## Status

`[provider-doc]`. Last reviewed 2026-08-06.
