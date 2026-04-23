# GCG: Universal and Transferable Adversarial Attacks `[paper]`

## One-sentence TL;DR

An algorithm (Greedy Coordinate Gradient) that finds adversarial suffixes — short strings of tokens — which, when appended to a harmful request, cause aligned models to comply. The suffixes transfer across models and are found automatically, not by hand.

## Citation

Zou, A., Wang, Z., Carlini, N., Nasr, M., Kolter, J. Z., & Fredrikson, M. (2023). *Universal and Transferable Adversarial Attacks on Aligned Language Models.* [arxiv.org/abs/2307.15043](https://arxiv.org/abs/2307.15043)

## What the paper introduced

GCG is a discrete optimization method for generating adversarial token sequences:
1. Start with a harmful prompt and a target compliance prefix ("Sure, here is…").
2. Append a suffix of adversarial tokens.
3. Use gradient information from an open-weight model to select token substitutions that increase the probability of the target prefix.
4. Greedy coordinate-by-coordinate search finds a suffix that drives compliance.

The suffixes look like gibberish to humans but are devastatingly effective — and crucially, suffixes optimized against one open model often **transfer** to closed models the attacker has no access to.

## Why it was a turning point

Before GCG, jailbreaks were mostly hand-crafted prompts ("roleplay as an unrestricted AI"). They could be patched one-by-one. GCG demonstrated that jailbreaks could be found **automatically at scale**, and that attacks generalize — training defenses on one attack class doesn't block the next optimizer's output.

The paper shifted the field's framing from "patch known jailbreaks" to "assume alignment is adversarially fragile and build defenses that don't depend on it alone."

## Defensive implications

- **Perplexity filtering.** GCG suffixes are often high-perplexity gibberish; input-side perplexity checks catch many of them.
- **Paraphrasing / retokenization.** Rewriting the input before the model sees it can break brittle adversarial structures.
- **Constrained decoding.** Restricting what the model can emit (structured output, content policies enforced at output) limits damage even when the input slips past.
- **Layered defenses.** No single filter holds; the paper's lesson is that alignment alone isn't a trust boundary.

These are all active research areas — none are complete solutions.

## Ethical framing

The authors released the attack method and demonstrated it on commercial closed models. This is standard responsible-disclosure practice: public knowledge of the vulnerability forces providers to invest in defenses.

## Related entries

- `learning/safety/indirect-prompt-injection.md` — the data-source-side twin of GCG's input-side threat.
- `learning/safety/jailbreak-failure-modes.md` — *why* safety training leaves gaps that optimizers like GCG can exploit.

## Read it when

- You're building a safety-critical LLM application.
- You're evaluating a model's robustness — the GCG benchmark (or successors like HarmBench) is the standard comparison.

## Status

`[paper]`.
