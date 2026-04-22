# Self-refine `[paper]`

## One-sentence pitch

Have the model critique its own output and produce a revised version — iterative self-critique lifts quality on tasks where the model can recognize its own errors after the fact.

## Evidence

- **Primary citation:** Madaan, A., Tandon, N., Gupta, P., Hallinan, S., Gao, L., Wiegreffe, S., Alon, U., Dziri, N., Prabhumoye, S., Yang, Y., Gupta, S., Majumder, B. P., Hermann, K., Welleck, S., Yazdanbakhsh, A., & Clark, P. (2023). *Self-Refine: Iterative Refinement with Self-Feedback.* NeurIPS 2023. [arxiv.org/abs/2303.17651](https://arxiv.org/abs/2303.17651)

## What the paper shows

Prompting a model in three phases — **generate** an initial output, **feedback** (critique it), **refine** (produce a revised version using the feedback) — improves quality across seven tasks (dialogue response, code optimization, code readability, math reasoning, acronym generation, constrained generation, sentiment reversal). The gains are strongest on tasks where errors are recognizable by the same model that generated them.

## Practical rules

- **Use distinct prompts per phase.** One prompt to generate, one to critique, one to refine. Mixing them in a single long prompt performs worse in the paper's ablations.
- **Structured critique beats free-form.** Ask for specific failure categories (correctness, completeness, style) rather than "what's wrong with this?"
- **Stop early.** Most gain comes in the first refinement pass. Past 2–3 iterations, improvements plateau and cost stacks up.
- **Know when the model can't self-critique.** If the task requires ground truth the model doesn't have (e.g., factual recall outside its training), self-refine can confidently produce a worse answer.

## When it's not worth it

- **Tasks with no recognizable error structure.** Creative writing without a quality rubric — self-critique tends to produce plausible-but-arbitrary changes.
- **Latency budgets.** 3x the calls (generate + feedback + refine), minimum.
- **Models that are already near-ceiling** on the task — there's nothing to refine.

## Adjacent idea

- **Constitutional AI** (Bai et al., 2022, [arxiv.org/abs/2212.08073](https://arxiv.org/abs/2212.08073)) applies a similar self-critique pattern during training rather than inference, using a set of principles ("a constitution") as the critique criteria.

## Related entries

- `agents/reflexion.md` — the agent-loop generalization of self-refine.

## Status

`[paper]`. Upgrade path: `[tested]` comparison on a code-optimization task with single-pass vs 1-refine vs 3-refine.
