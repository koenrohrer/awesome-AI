# Build an agent with testable boundaries

## The Short Version

Start with a narrow task, a small tool set, and a way to tell whether the agent succeeded. Most useful agents are not "autonomous" in the broad sense. They are bounded systems with a loop, an optional workflow graph, and a runtime harness.

Use the agent papers as design patterns, not as proof that a generic agent will work in your product. ReAct gives the core loop. Plan-and-Solve separates planning from execution. Reflexion helps only when you have a real success signal. SWE-Bench and GAIA are evaluation references, not product claims.

Treat tool outputs as untrusted data. Any agent that reads webpages, documents, email, repository files, or chat messages needs prompt-injection boundaries before it gets write access or side-effecting tools.

## Use This Guide When

Use this guide when you are designing an agent loop rather than choosing an off-the-shelf assistant: code repair, research workflows, data cleanup, ticket triage, browser tasks, or any system where model output selects the next action.

## Fast Path

- **[ReAct: Reasoning + Acting](../agents/react.md)** `[paper]` — start here for the thought/action/observation loop.
- **[Agent loop](../agents/agent-loop.md)** `[provider-doc]` — define budgets, retries, termination, and escalation around repeated actions.
- **[Graph-structured orchestration](../agents/graph-structured-orchestration.md)** `[provider-doc]` — add branches, cycles, fan-out, or durable handoffs only when the task needs them.
- **[Agent harnesses](../learning/architecture/agent-harnesses.md)** `[provider-doc]` — establish the tools, permissions, state, isolation, tracing, evaluation, and recovery boundary.
- **[Tool use (Anthropic / Claude)](../agents/tool-use-anthropic.md)** `[provider-doc]` — map the loop onto one provider API before comparing protocol differences.
- **[Plan-and-Solve prompting](../agents/plan-and-solve.md)** `[paper]` — split planning from execution when one flat loop drifts.
- **[Reflexion](../agents/reflexion.md)** `[paper]` — add retry learning only when you can score failures.
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]` — read before connecting untrusted content to tools.
- **[SWE-Bench](../agents/swe-bench.md)** `[paper]` — use as a benchmark reference for coding-agent stacks.

## Decision Points

First decide what counts as done. If the task cannot be scored by tests, exact answers, human review, or a narrow rubric, the agent will be hard to improve.

Then decide which tools are allowed to act. Read-only tools are a different risk class from tools that send messages, edit files, create tickets, move money, or deploy code.

Choose the loop shape last. A single ReAct loop is enough for short tasks. Add a planner when tasks need decomposition. Add Reflexion when retries can use a pass/fail signal. Add a skill library only when solved work is reusable.

Keep three layers distinct:

- The **loop** is the control cycle: choose, act, observe, evaluate, then stop, retry, or escalate.
- The **graph** is the workflow topology: branches, cycles, parallel paths, joins, and handoffs.
- The **harness** is the runtime boundary: tools, permissions, context, state, isolation, observability, evaluation, and recovery.

A graph can contain several loops, and one harness can execute either a graph or a linear loop. Start with one loop in one harness. Introduce graph structure only when an observed branch, recovery path, or durability need justifies it.

## Field Notes

Tool schemas are product design. Narrow names, required fields, enums, and clear descriptions reduce misrouted calls.

Observations need budgets. Long raw tool outputs can bury the state the next step needs. Summarize, retrieve, or cite instead of dumping everything into context.

Retries need a cap and a failure signal. Without both, Reflexion-style loops mostly spend tokens and repeat mistakes.

Termination is a product requirement. Set maximum turns, tool calls, elapsed time, and spend outside the model; preserve verified state and escalate when the system cannot proceed safely.

Benchmarks measure scaffolds as much as models. SWE-Bench and GAIA results depend on the harness, tool inventory, retry policy, and grading setup.

## What To Avoid

Avoid building a broad "agent platform" before you have one narrow task that works end to end.

Avoid giving side-effecting tools to an agent that receives untrusted content without explicit trust boundaries and review points.

Avoid treating a benchmark citation as evidence for your own workflow unless your task, tools, and grading method resemble the benchmark.

Avoid vague tool descriptions. If two tools sound interchangeable, the model will route calls unpredictably.

## Evidence Library

- **[ReAct: Reasoning + Acting](../agents/react.md)** `[paper]`
- **[Agent loop](../agents/agent-loop.md)** `[provider-doc]`
- **[Graph-structured orchestration](../agents/graph-structured-orchestration.md)** `[provider-doc]`
- **[Agent harnesses](../learning/architecture/agent-harnesses.md)** `[provider-doc]`
- **[TraceLab](../agents/tracelab.md)** `[paper]`
- **[Toolformer](../agents/toolformer.md)** `[paper]`
- **[Plan-and-Solve prompting](../agents/plan-and-solve.md)** `[paper]`
- **[Reflexion](../agents/reflexion.md)** `[paper]`
- **[Voyager](../agents/voyager.md)** `[paper]`
- **[SWE-Bench](../agents/swe-bench.md)** `[paper]`
- **[GAIA: General AI Assistant benchmark](../agents/gaia.md)** `[paper]`
- **[Tool use (Anthropic / Claude)](../agents/tool-use-anthropic.md)** `[provider-doc]`
- **[Tool use (OpenAI)](../agents/tool-use-openai.md)** `[provider-doc]`
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]`
- **[GCG: Universal Adversarial Attacks](../learning/safety/gcg-attack.md)** `[paper]`
- **[Jailbroken: How Does LLM Safety Training Fail?](../learning/safety/jailbreak-failure-modes.md)** `[paper]`
