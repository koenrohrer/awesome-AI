# Toolformer `[paper]`

## One-sentence pitch

Teach a model to call APIs via self-supervised training — the model learns *when* to emit a tool call from training data augmented with candidate calls it filters itself.

## Evidence

- **Primary citation:** Schick, T., Dwivedi-Yu, J., Dessì, R., Raileanu, R., Lomeli, M., Zettlemoyer, L., Cancedda, N., & Scialom, T. (2023). *Toolformer: Language Models Can Teach Themselves to Use Tools.* NeurIPS 2023. [arxiv.org/abs/2302.04761](https://arxiv.org/abs/2302.04761)

## What the paper shows

Given an unlabeled dataset, a base LM can (1) generate candidate API calls at positions in text, (2) execute them, (3) keep only calls that reduce the model's perplexity on subsequent tokens, and (4) fine-tune on the filtered data. The resulting model learns to call calculators, Wikipedia, translators, and calendars on its own — outperforming much larger models on math and QA benchmarks.

## Why it matters

ReAct and API-calling patterns work at *inference* time — clever prompting of a general-purpose model. Toolformer demonstrates tool use as a *training-time* capability: the model learns when each tool is useful and emits calls reflexively rather than being prompted through a loop.

Modern frontier models ship with tool-use behavior baked in from post-training (RLHF/RLAIF on tool-augmented tasks). Toolformer is the canonical citation for that approach.

## Practical takeaways

- **If you're evaluating a model's tool-use fitness**, distinguish between "can follow a ReAct-style prompt" (prompt-time) and "emits tool calls naturally where they help" (training-time). Frontier models do both.
- **Self-supervised filtering generalizes.** The pattern — generate candidates, filter by downstream loss, fine-tune on survivors — shows up in many subsequent tool-use, agent-training, and reasoning-training papers.

## Related entries

- `agents/react.md` — the inference-time complement to Toolformer's training-time approach.
- `agents/tool-use-anthropic.md`, `agents/tool-use-openai.md` — consumer-facing APIs to models that inherit Toolformer-style training.

## Status

`[paper]`.
