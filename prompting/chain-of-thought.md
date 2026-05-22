# Chain-of-thought prompting `[paper]`

## One-sentence pitch

Prompting the model to show intermediate reasoning before answering improves accuracy on multi-step arithmetic and commonsense benchmarks.

## Evidence

- **Primary citation:** Wei, J., Wang, X., Schuurmans, D., Bosma, M., Ichter, B., Xia, F., Chi, E., Le, Q., & Zhou, D. (2022). *Chain-of-Thought Prompting Elicits Reasoning in Large Language Models.* NeurIPS 2022. [arxiv.org/abs/2201.11903](https://arxiv.org/abs/2201.11903)
- **Zero-shot follow-up:** Kojima, T., Gu, S. S., Reid, M., Matsuo, Y., & Iwasawa, Y. (2022). *Large Language Models are Zero-Shot Reasoners.* NeurIPS 2022. [arxiv.org/abs/2205.11916](https://arxiv.org/abs/2205.11916) — showed that the prompt "Let's think step by step" alone (no few-shot examples) produces significant gains.

## What the papers show

Wei et al. (2022) found that few-shot examples with written intermediate reasoning improve performance on GSM8K, SVAMP, and StrategyQA. The effect appears at sufficient model scale; smaller models show small or negative gains.

Kojima et al. (2022) found that appending "Let's think step by step" can elicit similar zero-shot gains without hand-crafted examples.

## What it doesn't show

- Gains are task-dependent — chain-of-thought barely helps on tasks that aren't multi-step.
- The effect size shrinks as frontier models are already trained with reasoning-heavy data.
- It increases output tokens, which increases cost and latency. Use only when the task benefits.

## How to use it

**Zero-shot form:**
```
<question>
Let's think step by step.
```

**Few-shot form:** Provide 2-8 examples showing the intermediate reasoning and final answer.

## Related entries

- `prompting/few-shot.md` — how to pick good examples to pair with CoT.

## Status

This entry is `[paper]`. Upgrading to `[tested]` requires a maintainer-run test directory in `prompting/tests/chain-of-thought/`.
