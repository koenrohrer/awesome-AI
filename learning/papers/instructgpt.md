# InstructGPT / RLHF `[paper]`

## One-sentence TL;DR

Introduced the three-stage recipe that turns a raw pretrained LM into a helpful assistant: **supervised fine-tuning → reward model → reinforcement learning from human feedback (RLHF)**. The paper that made ChatGPT possible.

## Citation

Ouyang, L., Wu, J., Jiang, X., Almeida, D., Wainwright, C. L., Mishkin, P., Zhang, C., Agarwal, S., Slama, K., Ray, A., Schulman, J., Hilton, J., Kelton, F., Miller, L., Simens, M., Askell, A., Welinder, P., Christiano, P., Leike, J., & Lowe, R. (2022). *Training language models to follow instructions with human feedback.* NeurIPS 2022. [arxiv.org/abs/2203.02155](https://arxiv.org/abs/2203.02155)

## The three-stage recipe

1. **Supervised fine-tuning (SFT).** Human labelers write high-quality answers to prompts; the base model is fine-tuned on this demonstration data.
2. **Reward modeling.** Labelers rank multiple model responses to the same prompt. A reward model is trained to predict these rankings.
3. **RL (PPO).** The SFT model is further optimized against the reward model using proximal policy optimization, with a KL-divergence penalty to keep it from drifting too far from the SFT checkpoint.

## Why it was a turning point

Before InstructGPT, the prevailing approach was "bigger model, better outputs." The paper showed that a **1.3B-parameter InstructGPT beat a 175B-parameter GPT-3** on instruction-following evaluations — because GPT-3 had never been trained on what "helpful" looks like.

Alignment-via-RLHF became the default recipe across the industry for 18+ months after this paper. Most subsequent alignment papers (DPO, Constitutional AI, RLAIF) are variations on or alternatives to this pattern.

## Caveats and successors

- **Reward hacking.** The policy learns to game the reward model, which is itself imperfect. Keeping the KL penalty tight mitigates this but doesn't eliminate it.
- **Labeler bias.** Models trained via RLHF inherit the preferences of the labelers — they are not objective "helpful" optimizers.
- **Expensive.** The pipeline needs ongoing human labeling. This is what motivated DPO and Constitutional AI as lower-cost alternatives.

## Related entries

- `learning/papers/dpo.md` — the simpler, RL-free alternative that competes with RLHF on many tasks.
- `learning/papers/constitutional-ai.md` — AI-generated preference data to reduce the human-labeling load.

## Read it when

- You're designing a fine-tuning or alignment pipeline.
- Someone describes a model as "aligned" — this is the baseline method they're probably comparing against.

## Status

`[paper]`.
