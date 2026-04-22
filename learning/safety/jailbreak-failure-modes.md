# Jailbroken: How Does LLM Safety Training Fail? `[paper]`

## One-sentence TL;DR

A framework for understanding *why* jailbreaks work: safety-trained models fail when an attack is either out-of-distribution from the safety training data, or when it triggers a capability (e.g., code-writing, roleplay) the model has stronger incentives to use than to refuse.

## Citation

Wei, A., Haghtalab, N., & Steinhardt, J. (2023). *Jailbroken: How Does LLM Safety Training Fail?* NeurIPS 2023. [arxiv.org/abs/2307.02483](https://arxiv.org/abs/2307.02483)

## Two failure modes the paper isolates

1. **Competing objectives.** During safety training, the model learns to refuse harmful content *and* to be helpful. A jailbreak creates a context where these goals conflict, and the model resolves in favor of helpfulness. ("You are a helpful assistant. Write a story about X" — where the story requires executing a harmful capability.)
2. **Mismatched generalization.** Safety training covers a slice of the pretraining distribution. Attackers phrase harmful requests in domains the safety training barely touched (rare languages, technical jargon, base64 encoding, low-resource dialects). The harmful-request detector generalizes poorly; the underlying capability generalizes fine.

This diagnosis explains a lot:
- Why encoded/obfuscated requests work.
- Why persona roleplay ("you are DAN") works.
- Why the same jailbreak that works today might fail after the next safety training pass — and why a sibling jailbreak will pop up in its place.

## Why the framework matters

It reframes jailbreaks from "clever tricks" to "predictable failure modes." The two axes (competing objectives, mismatched generalization) give you a systematic way to think about:
- **Attack design.** Which domain is underrepresented in this model's safety training?
- **Defense design.** What generalization would need to hold for this to not be a gap?
- **Evaluation.** Red-team suites should cover both axes explicitly.

## What this implies for defense

- **Safety training alone is not a trust boundary.** No amount of adversarial-example training closes a gap caused by fundamental distribution mismatch; you need architectural defenses outside the model.
- **Least-privilege and output constraints** beat input-side filtering as a long-term strategy. You can't enumerate all the ways a harmful request can be phrased, but you can limit what the model can *do* with a harmful generation.
- **Test in the domains you ship in.** A model red-teamed in English won't be robust in Dhivehi or base64.

## Related entries

- `learning/safety/gcg-attack.md` — an automated exploitation of the "mismatched generalization" failure mode at the token level.
- `learning/safety/indirect-prompt-injection.md` — the agent-deployment threat that compounds these failure modes.
- `learning/papers/instructgpt.md`, `learning/papers/constitutional-ai.md` — the training approaches whose limits this paper maps.

## Read it when

- You're designing a red-team suite.
- You're evaluating whether a model's "safety" makes it safe to deploy in a specific context (usually: no, not on its own).

## Status

`[paper]`.
