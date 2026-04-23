# Tree of Thoughts (ToT) `[paper]`

## One-sentence pitch

Generalize chain-of-thought from a linear chain into a **tree** of partial reasoning states, with explicit evaluation and search — lets the model look ahead, backtrack, and try alternatives on problems where a single reasoning path isn't enough.

## Evidence

- **Primary citation:** Yao, S., Yu, D., Zhao, J., Shafran, I., Griffiths, T. L., Cao, Y., & Narasimhan, K. (2023). *Tree of Thoughts: Deliberate Problem Solving with Large Language Models.* NeurIPS 2023. [arxiv.org/abs/2305.10601](https://arxiv.org/abs/2305.10601)

## What the paper shows

On Game of 24 (combinatorial math), Creative Writing, and Mini Crosswords — tasks where a single forward reasoning chain struggles — ToT dramatically outperforms CoT. The gains are largest where the task has a clear intermediate-state evaluator.

## The four ingredients

1. **Thought decomposition.** Break the problem into intermediate states (e.g., "after applying this operation, what's the remaining subproblem?").
2. **Thought generation.** At each state, sample multiple candidate next-thoughts.
3. **State evaluation.** Score each candidate (via the same LM: "is this state promising?").
4. **Search algorithm.** BFS or DFS over the scored tree, expanding promising states, pruning weak ones.

## Practical rules

- **The evaluator matters more than the generator.** If the LM can't score partial states well, the tree has no useful signal to search on — and you're just burning calls.
- **Use BFS for breadth-critical problems, DFS for depth-critical.** Game-of-24 is BFS-friendly (wide candidate space, shallow solution depth); crosswords are DFS-friendly.
- **Cost explodes fast.** A branching factor of 5 over 4 steps is 625 LM calls per problem. ToT is for problems where single-path CoT demonstrably fails — not for routine use.
- **Prune aggressively.** Keep only top-k candidates per state. The paper keeps 1–5 depending on task.

## When it's not worth it

- **Problems CoT already solves** — the extra calls buy nothing.
- **Tasks without a clean intermediate-state evaluator** — without scoring, ToT degenerates to random sampling.
- **Modern reasoning models** (Claude extended thinking, o-series) perform structured internal search; external ToT on top is often redundant and expensive.

## Related entries

- `prompting/chain-of-thought.md` — the linear special case.
- `prompting/self-consistency.md` — a simpler aggregation scheme with less machinery.
- `agents/plan-and-solve.md` — the agent-loop generalization.

## Status

`[paper]`.
