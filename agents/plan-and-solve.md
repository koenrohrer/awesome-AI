# Plan-and-Solve prompting `[paper]`

## One-sentence pitch

Prompt the model to first generate a plan, then execute each step of the plan — outperforms zero-shot chain-of-thought on multi-step reasoning by explicitly separating planning from solving.

## Evidence

- **Primary citation:** Wang, L., Xu, W., Lan, Y., Hu, Z., Lan, Y., Lee, R. K.-W., & Lim, E.-P. (2023). *Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought Reasoning by Large Language Models.* ACL 2023. [arxiv.org/abs/2305.04091](https://arxiv.org/abs/2305.04091)

## The recipe

1. **Plan.** Prompt: "Let's first understand the problem and devise a plan to solve the problem. Then, let's carry out the plan and solve the problem step by step."
2. **Solve.** Continue generation; the model executes the plan it just wrote.

A stronger variant — **PS+** — adds explicit error-reduction cues: "Pay attention to calculation", "extract relevant variables", "consider dimensions/units".

## What the paper shows

On GSM8K, AQuA, SVAMP, AddSub, and similar reasoning benchmarks, Plan-and-Solve consistently beats zero-shot CoT ("Let's think step by step"). The gap is largest on problems where calculation errors or missed subproblems dominate — the explicit plan reduces skip-ahead mistakes.

## Why it matters for agents

Most agent loops that look more capable than they ought to given their model choice are implementing a plan-and-solve split:
- A **planner** call produces a numbered list of steps.
- An **executor** call (often the same model) works through the plan one step at a time, with the plan in context.

This separation is the basis for modern agent-framework conventions (plans + tool calls, planner/worker roles, decomposition before execution).

## Practical rules

- **The plan is context, not contract.** Let the executor adapt when it hits surprise state. Rigidly forcing each step breaks on real-world tasks.
- **Validate the plan before executing.** A cheap check call ("does this plan cover the problem?") catches decomposition errors before you spend tokens on bad subproblems.
- **Keep plans short.** Plans with 12+ steps tend to drift. Re-plan at natural breakpoints instead.
- **Combine with reflexion.** If a plan fails, a self-reflection step can rewrite the plan before the next attempt.

## Related entries

- `prompting/least-to-most.md` — the prompting-level precursor.
- `prompting/chain-of-thought.md` — Plan-and-Solve is CoT with explicit planning structure.
- `agents/reflexion.md` — pairs well as a recovery mechanism after failed plans.

## Status

`[paper]`.
