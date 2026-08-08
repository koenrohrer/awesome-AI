# Context Folding `[paper]`

## One-sentence TL;DR

Context Folding lets an agent branch into a subtask, compress the completed trajectory into a result, and return that result to a smaller active context.

## Citation

Sun et al. (2026). *Scaling Long-Horizon Agent via Context Folding.* ICML 2026. [OpenReview](https://openreview.net/forum?id=lNRgWoGfYg)

## What the method changes

Long-running agents accumulate instructions, observations, intermediate reasoning, and tool output. A flat transcript makes each later model call process that history again, even when much of it only supported a completed subtask.

Context Folding gives the agent an explicit branch operation. Work inside the branch can use its own trajectory; when the branch completes, a fold operation returns a compact result to its parent and leaves the detailed branch outside the active context. The structure resembles a call stack, but the model decides when decomposition and folding are useful.

## Why it matters

The paper reports active contexts up to 10 times smaller on its evaluated long-horizon tasks. Treat that as an author-reported result, not a universal compression ratio. Savings and quality depend on whether the folded result preserves the evidence, unresolved questions, identifiers, and state needed later.

Folding also creates a recovery and audit requirement. The detailed branch should remain addressable outside the active prompt, and the folded result needs provenance. Otherwise compression can hide a failed tool call or discard a constraint that only becomes relevant later.

## Evaluate it with

- task success and grader quality, not token reduction alone;
- active and total tokens across the whole run;
- facts or constraints lost at fold boundaries;
- the cost of reopening a branch after an incomplete summary;
- hostile instructions inside branch observations.

## Related entries

- [Agent harnesses](agent-harnesses.md) — stores branch artifacts, policies, and resumable state.
- [Graph-structured orchestration](../../agents/graph-structured-orchestration.md) — represents branch and return topology.
- [KV cache](kv-cache.md) — serving-time reuse is distinct from reducing the logical context supplied to the model.

## Status

`[paper]`. Last reviewed 2026-08-06.
