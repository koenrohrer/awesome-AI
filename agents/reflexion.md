# Reflexion `[paper]`

## One-sentence pitch

When an agent fails a task, have it produce a natural-language reflection on what went wrong, then retry with that reflection in its context — materially improves success rates on multi-attempt benchmarks.

## Evidence

- **Primary citation:** Shinn, N., Cassano, F., Gopinath, A., Narasimhan, K., & Yao, S. (2023). *Reflexion: Language Agents with Verbal Reinforcement Learning.* NeurIPS 2023. [arxiv.org/abs/2303.11366](https://arxiv.org/abs/2303.11366)

## What the paper shows

Given a binary success signal on each attempt (task passed / task failed), the agent generates a short self-reflection after each failure. The reflection — not the raw trajectory — is appended to context for the next attempt. On HumanEval, ALFWorld, and HotpotQA, this dramatically improves pass@k vs naive retry with the same trajectory.

"Verbal reinforcement learning" captures the idea: the reflection *is* the reward signal, encoded as natural language the model can condition on.

## Where it fits

Reflexion is the agent-loop generalization of `prompting/self-refine.md` — self-refine operates on a single output; Reflexion operates across a multi-step trajectory.

## Practical rules

- **Reflections must be short.** A full trajectory stuffed into the next attempt's context crowds out useful reasoning. The paper's reflections are 1–3 sentences.
- **You need a success signal.** Tests, rubric-graders, or an evaluator model. Without a pass/fail, there's nothing to reflect against.
- **Cap the retries.** Like all iterative methods, gains plateau — by 3–5 attempts on most benchmarks.
- **Reflect selectively.** Not every failure warrants a reflection; sometimes the task is genuinely impossible. Some follow-ups let the reflector decide to give up.

## When it's not worth it

- **Tasks without a clean pass/fail signal** — you can't score reflections.
- **Frontier reasoning models** already do something similar internally; the external Reflexion loop provides less additional lift than on earlier models.

## Related entries

- `prompting/self-refine.md` — the single-output precursor.
- `agents/react.md` — Reflexion typically wraps a ReAct-style inner loop.

## Status

`[paper]`.
