# Toolformer `[paper]`

## One-sentence pitch

Train a model to call APIs from self-supervised data. Candidate tool calls are generated, filtered by loss improvement, and used for fine-tuning.

## Evidence

- **Primary citation:** Schick, T., Dwivedi-Yu, J., Dessì, R., Raileanu, R., Lomeli, M., Zettlemoyer, L., Cancedda, N., & Scialom, T. (2023). *Toolformer: Language Models Can Teach Themselves to Use Tools.* NeurIPS 2023. [arxiv.org/abs/2302.04761](https://arxiv.org/abs/2302.04761)

## What the paper shows

Given an unlabeled dataset, a base LM can (1) generate candidate API calls at positions in text, (2) execute them, (3) keep only calls that reduce perplexity on subsequent tokens, and (4) fine-tune on the filtered data. The resulting model reports stronger math and QA benchmark results than larger baselines without those tool-use traces.

## Why it matters

ReAct and API-calling patterns work at *inference* time through prompting and tool orchestration. Toolformer demonstrates tool use as a *training-time* capability: tool-call behavior is learned from filtered examples rather than added only by an external loop.

Modern frontier models ship with tool-use behavior baked in from post-training (RLHF/RLAIF on tool-augmented tasks). Toolformer is the canonical citation for that approach.

## Practical takeaways

- **If you're evaluating a model's tool-use fitness**, distinguish between "can follow a ReAct-style prompt" (prompt-time) and "emits tool calls naturally where they help" (training-time). Frontier models do both.
- **Self-supervised filtering generalizes.** The pattern — generate candidates, filter by downstream loss, fine-tune on survivors — shows up in many subsequent tool-use, agent-training, and reasoning-training papers.

## Related entries

- `agents/react.md` — the inference-time complement to Toolformer's training-time approach.
- `agents/tool-use-anthropic.md`, `agents/tool-use-openai.md` — consumer-facing APIs to models that inherit Toolformer-style training.

## Status

`[paper]`.
