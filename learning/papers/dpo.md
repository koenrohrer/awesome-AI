# Direct Preference Optimization (DPO) `[paper]`

## One-sentence TL;DR

A closed-form objective that optimizes a language model directly from preference data — no separate reward model, no RL loop. Competes with RLHF on most tasks while being dramatically simpler to implement.

## Citation

Rafailov, R., Sharma, A., Mitchell, E., Ermon, S., Manning, C. D., & Finn, C. (2023). *Direct Preference Optimization: Your Language Model is Secretly a Reward Model.* NeurIPS 2023 (Outstanding Paper). [arxiv.org/abs/2305.18290](https://arxiv.org/abs/2305.18290)

## The key insight

In the RLHF formulation (reward model + PPO with a KL penalty against a reference policy), the optimal policy has a closed-form expression in terms of the reward and the reference policy. Rafailov et al. show you can reparameterize this: treat the *log-ratio* between the learned policy and the reference policy as the reward, and then the preference-learning objective becomes a simple classification-style loss over pairs of responses — no explicit reward model, no RL.

The resulting training loop is roughly as simple as supervised fine-tuning, while producing models that match or beat RLHF on alignment benchmarks.

## Why it mattered

- **Accessibility.** RLHF's engineering complexity kept it out of reach for most teams. DPO runs on a standard fine-tuning stack.
- **Reproducibility.** Fewer moving parts (no reward model to train, no PPO hyperparameters to tune) means results are more consistent across teams.
- **Basis for follow-ups.** IPO, KTO, ORPO, and other preference-optimization variants all descend from the DPO reformulation.

## When DPO is enough

- You have a preference dataset (pairs of responses labeled "A preferred over B") and want to align a model.
- The preference data is high quality and well-distributed over the tasks you care about.
- You don't need online exploration (the RL that RLHF provides is valuable when you want the model to discover preferred responses beyond the demonstration distribution).

## When you still want RLHF (or successors)

- Online RL with a live reward model captures behaviors that static preference data can't teach.
- Some teams find RLHF's exploration leads to qualitatively different behaviors than DPO on open-ended tasks.

## Related entries

- `learning/papers/instructgpt.md` — the RLHF pipeline DPO replaces.
- `learning/papers/constitutional-ai.md` — generating preference data at scale without human labelers.

## Status

`[paper]`.
