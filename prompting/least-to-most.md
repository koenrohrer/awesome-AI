# Least-to-most prompting `[paper]`

## One-sentence pitch

Decompose a hard problem into a sequence of easier subproblems, solve them in order, and use each answer as context for the next — teaches the model to break problems down before diving in.

## Evidence

- **Primary citation:** Zhou, D., Schärli, N., Hou, L., Wei, J., Scales, N., Wang, X., Schuurmans, D., Cui, C., Bousquet, O., Le, Q., & Chi, E. (2022). *Least-to-Most Prompting Enables Complex Reasoning in Large Language Models.* ICLR 2023. [arxiv.org/abs/2205.10625](https://arxiv.org/abs/2205.10625)

## What the paper shows

On compositional generalization benchmarks (SCAN, DROP, GSM8K), chain-of-thought prompted with a single trajectory struggles on problems that are harder than the few-shot examples demonstrate. Least-to-most splits problem-solving into two phases:
1. **Decomposition** — prompt the model to list subproblems.
2. **Sequential solve** — solve subproblems one at a time, appending each solution to the context of the next.

The decomposition-and-sequence structure generalizes to harder instances than CoT does — with the same model, same examples, significantly higher accuracy on out-of-distribution instances.

## Why it matters

Least-to-most isolates **what** to do (decompose) from **how** to do each step (solve). This separation underpins much of modern agent planning — most agent frameworks that distinguish "planner" and "worker" roles are implementing a least-to-most structure.

## Practical rules

- **Verify decompositions.** If the decomposition phase produces bad subproblems, the sequence is doomed. Some implementations include a critique/fix pass on the decomposition itself.
- **Keep subproblem context small.** If every subproblem carries the full history, context balloons. Summarize each subproblem's result before the next step.
- **Don't split further than the model can handle.** Over-decomposition creates too many handoff points where context drift accumulates.
- **Few-shot the decomposition itself.** The paper provides few-shot examples of (problem → subproblem list) separately from (subproblem + history → solution).

## When it's not worth it

- **Problems the model solves in a single CoT pass.** The sequential overhead is pure cost.
- **Tasks where subproblems are tightly interdependent** — if you can't solve step k without simultaneously reasoning about step k+3, the sequential structure breaks down.

## Related entries

- `prompting/chain-of-thought.md` — least-to-most is CoT applied recursively.
- `agents/plan-and-solve.md` — the agent-loop cousin.

## Status

`[paper]`.
