# Few-shot prompting `[paper]`

## One-sentence pitch

Showing the model a handful of input-output examples in the prompt outperforms zero-shot on most tasks, with diminishing returns past roughly 8 examples on many benchmarks.

## Evidence

- **Foundational citation:** Brown, T. B., Mann, B., Ryder, N., Subbiah, M., et al. (2020). *Language Models are Few-Shot Learners.* NeurIPS 2020 (the GPT-3 paper). [arxiv.org/abs/2005.14165](https://arxiv.org/abs/2005.14165)
- **Sensitivity study:** Lu, Y., Bartolo, M., Moore, A., Riedel, S., & Stenetorp, P. (2022). *Fantastically Ordered Prompts and Where to Find Them: Overcoming Few-Shot Prompt Order Sensitivity.* ACL 2022. [arxiv.org/abs/2104.08786](https://arxiv.org/abs/2104.08786) — shows that the *order* of few-shot examples materially affects performance.

## What the papers show

Brown et al. (2020) established the scaling curve: accuracy rises with the number of in-context examples up to a plateau. Gains are largest going from 0 → 1 example, and meaningful through roughly 8 on many tasks.

Lu et al. (2022) show that shuffling the order of the same examples can swing accuracy by double digits — few-shot is not ordering-invariant.

## Practical rules

- **Pick representative examples.** Examples should cover the range of inputs you expect, not just the easy cases.
- **Order matters.** Put the hardest example last (closest to the query) — models attend more to recent context.
- **Avoid label imbalance.** If you're classifying and 7 of 8 examples are class A, the model will bias toward A.
- **Beware format leakage.** The model will mimic surface-level formatting of your examples — make sure the format you demonstrate is the one you want back.

## When few-shot doesn't help

- Instruction-tuned frontier models often match few-shot performance with a well-written zero-shot instruction.
- Tasks with a clear schema (classification with a fixed label set) — a single example plus the schema often suffices.

## Related entries

- `prompting/chain-of-thought.md` — few-shot + CoT is often stronger than either alone.
- `prompting/structured-output.md` — for rigid schemas, structured-output constraints can replace examples.

## Status

`[paper]`. Upgrade path: maintainer-run tests on a classification task with 0/1/4/8 examples, shuffled across orderings.
