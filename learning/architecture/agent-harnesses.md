# Agent harnesses `[provider-doc]`

## One-sentence TL;DR

An agent harness is the runtime boundary that gives a model tools, permissions, context, state, isolation, observability, evaluation hooks, and recovery behavior.

## Boundary, not intelligence

The model proposes outputs and actions. The harness decides what reaches the model, which tools exist, whether a call is allowed, how results are represented, what state survives, and when execution stops. Changing that boundary can change task results even when the model is unchanged.

A loop is the repeated control cycle. A graph is the workflow topology. A harness is the runtime in which either one executes.

## Core responsibilities

- **Tools:** narrow schemas, validated arguments, timeouts, typed errors, and idempotency keys for side effects.
- **Permissions:** least-privilege credentials, explicit approval gates, and separation of read from write authority.
- **Context:** selected instructions and evidence with provenance, size limits, and defenses against untrusted embedded instructions.
- **State:** durable task facts, checkpoints, artifact references, and versioned resumability without duplicating effects.
- **Isolation:** per-session filesystem and process boundaries, network controls, resource limits, and secret containment.
- **Observability:** model turns, tool calls, transitions, costs, latency, policy decisions, and stable run identifiers.
- **Evaluation:** reproducible tasks, graders, failure taxonomies, and comparisons that keep the harness configuration fixed.
- **Recovery:** bounded retries, rollback or compensation where possible, pause/resume, and human escalation.

## Security questions

Assume prompts, retrieved documents, repository files, webpages, and tool output are hostile. Ask which identity a tool uses, where secrets are injected, what outbound network destinations are allowed, which files can change, and how an operator can stop or inspect a run. A sandbox reduces blast radius; it does not make an unsafe action correct.

## Evaluating a harness

Use a real task with a clean starting state and an objective grader. Pin the model, prompts, tools, permissions, retry policy, and resource budget. Run both success and hostile-input cases, then inspect traces for unnecessary calls, hidden retries, leaked context, duplicate effects, and unhandled terminal states.

Do not infer a framework ranking from a model benchmark. The task, tool implementation, environment image, retry budget, and grader are all part of the measured system.

## Official references

- [AWS AgentCore Harness](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/harness.html) — a managed harness boundary with tools, memory, identity, observability, and per-session isolation.
- [Claude Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) — exposes the loop and runtime controls used by Claude Code.
- [OpenAI: Harness engineering](https://openai.com/index/harness-engineering/) — describes environment legibility, tools, documentation, and feedback loops for coding agents.
- [LangGraph overview](https://docs.langchain.com/oss/python/langgraph/overview) — documents durable execution, human review, memory, and debugging for stateful agents.

## Related entries

- [Agent loop](../../agents/agent-loop.md) — control cycle.
- [Graph-structured orchestration](../../agents/graph-structured-orchestration.md) — workflow topology.
- [TraceLab](../../agents/tracelab.md) — workload traces for observing real agent behavior.

## Status

`[provider-doc]`. Last reviewed 2026-08-06.
