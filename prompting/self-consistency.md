# Self-consistency `[paper]`

## One-sentence pitch

Sample multiple chain-of-thought reasoning paths and take the majority vote — beats single-sample CoT on reasoning benchmarks, especially when the task has a discrete answer space.

## Evidence

- **Primary citation:** Wang, X., Wei, J., Schuurmans, D., Le, Q., Chi, E., Narang, S., Chowdhery, A., & Zhou, D. (2022). *Self-Consistency Improves Chain of Thought Reasoning in Language Models.* ICLR 2023. [arxiv.org/abs/2203.11171](https://arxiv.org/abs/2203.11171)

## What the paper shows

On multiple reasoning benchmarks (GSM8K, AQuA, SVAMP, StrategyQA, ARC-challenge), sampling multiple CoT reasoning paths with temperature > 0 and aggregating by majority vote over the final answers significantly outperforms greedy single-sample CoT. The gains persist across model scales.

The intuition: different reasoning paths can land on the same correct answer even when individual paths have errors; aggregation smooths out the noise.

## Practical rules

- **Discrete answer spaces help.** Self-consistency is cleanest when you can extract a clean answer from each sample and count votes. Continuous or free-form outputs require more involved aggregation.
- **Sample count tradeoff.** Gains rise with samples but plateau. Past ~10–40 samples the marginal benefit is small; cost scales linearly.
- **Temperature matters.** Too low (0.1) — samples collapse; too high (1.0+) — samples become nonsensical. 0.5–0.7 is a common sweet spot.
- **Pair with few-shot CoT.** The paper uses few-shot prompts + sampling; zero-shot CoT + self-consistency also helps but with smaller gains.

## When it's not worth it

- **Latency-sensitive tasks.** N-times the calls for one answer.
- **Frontier reasoning models** (Claude with extended thinking, OpenAI o-series) already do internal consistency-style search; external self-consistency is redundant.
- **Non-discrete answers.** If extracting a comparable answer from each sample is hard, the aggregation step dominates.

## Related entries

- `prompting/chain-of-thought.md` — the technique self-consistency aggregates over.
- `prompting/extended-thinking.md` — provider-native alternative to client-side sampling.

## Status

`[paper]`. Upgrade path: `[tested]` comparison on GSM8K (or similar) with N ∈ {1, 5, 20} at T = 0.7.
