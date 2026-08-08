# Graph-structured orchestration `[provider-doc]`

## One-sentence TL;DR

A workflow graph makes control flow explicit as state, nodes, and transitions, including branches, cycles, fan-out, handoffs, and failure routes.

## What a graph adds

A single agent loop answers, “what happens next?” A graph records the larger workflow topology:

- **branches** select different paths from state or a model decision;
- **cycles** return to an earlier node for review, repair, or another observation;
- **fan-out and fan-in** run independent work and combine the results;
- **handoffs** transfer a bounded task and selected state to another worker or agent;
- **durable checkpoints** allow pause, resume, replay, and human review;
- **failure edges** route timeouts, policy denials, and exhausted retries deliberately.

Not every agent needs a graph framework. A short, linear loop is easier to test. Reach for a graph when the workflow already has meaningful branches, resumable state, parallel work, or different recovery policies.

## State and recovery

Define the state schema before the diagram grows. Separate durable facts and completed side effects from transient model messages. Give nodes narrow inputs and outputs, and make reducers explicit when parallel branches update the same field.

Checkpoint before external side effects and at human-review boundaries. Resuming a checkpoint must not repeat an email, payment, deployment, or other non-idempotent action. Record which node ran, its inputs, outputs, error, and transition so an operator can reconstruct a failure.

## Termination and escalation

Cycles require independent step and recursion limits. Conditional edges should have a fallback for missing or invalid state. A human interrupt is a state transition, not an exception to observability: save the proposed action, evidence, required authority, and the decision that resumes or terminates the run.

## “Graph engineering”

“Graph engineering” is an emerging label for designing and operating these stateful topologies. It does not describe a capability distinct from workflow orchestration, state machines, durable execution, or agent loops. Use the term only when its meaning is defined locally.

## Official references

- [LangGraph Graph API](https://docs.langchain.com/oss/python/langgraph/graph-api) — state, nodes, edges, reducers, branches, loops, and recursion limits.
- [LangGraph persistence](https://docs.langchain.com/oss/python/langgraph/persistence) — checkpoints, threads, replay, fault tolerance, and human-in-the-loop workflows.
- [Microsoft Agent Framework workflows](https://learn.microsoft.com/en-gb/agent-framework/) — graph-based workflows alongside agent abstractions.

## Related entries

- [Agent loop](agent-loop.md) — the repeated decision cycle that can run within a node.
- [Agent harnesses](../learning/architecture/agent-harnesses.md) — runtime controls shared across the graph.
- [Build an agent](../guides/build-an-agent.md) — a practical sequence for choosing the smallest sufficient topology.

## Status

`[provider-doc]`. Last reviewed 2026-08-06.
