# Voyager: Open-ended agent in Minecraft `[paper]`

## One-sentence pitch

An LLM-powered agent that plays Minecraft with no predefined goals — proposing its own curriculum, writing reusable skills as code, and storing them in a growing skill library. The cleanest demonstration of lifelong-learning agent patterns.

## Evidence

- **Primary citation:** Wang, G., Xie, Y., Jiang, Y., Mandlekar, A., Xiao, C., Zhu, Y., Fan, L., & Anandkumar, A. (2023). *Voyager: An Open-Ended Embodied Agent with Large Language Models.* [arxiv.org/abs/2305.16291](https://arxiv.org/abs/2305.16291)

## The three components

1. **Automatic curriculum.** The LLM proposes the next task for the agent to pursue based on what it already knows. No human-specified goals — the agent explores by choosing its own next challenge.
2. **Skill library.** When the agent solves a task, the solution is stored as reusable code (a function). Future tasks retrieve relevant skills by semantic similarity and compose them.
3. **Iterative prompting with environment feedback.** When code fails in the game environment, the error is fed back into the LLM, which revises the skill — a tight execute-observe-fix loop.

## Why it matters

Most agent benchmarks are closed tasks: here's a problem, here's a clear success signal. Voyager is open-ended: the agent chooses what to do, the world is procedurally generated, and progress is measured by the **diversity and complexity** of skills acquired.

The paper demonstrates that LLMs can drive long-horizon, open-ended behavior when paired with:
- A writable skill store
- Environment-grounded error feedback
- A self-directed curriculum

These three ideas show up in most subsequent "agent operating system" designs. Voyager is the canonical citation for them.

## Limitations worth knowing

- **Domain-specific scaffolding.** The Minecraft API, the MineDojo codebase, the specific skill-library design — all had to be built. Voyager is not a general agent architecture; it's a demonstration that the *pattern* works in a nontrivial domain.
- **No closed-loop generalization.** A Voyager agent in Minecraft doesn't transfer to other games. The paper's contribution is the pattern, not a portable runtime.
- **GPT-4-era results.** Benchmarks and costs have moved on; newer models and scaffolds may reproduce the behaviors more cheaply, but the architectural lessons remain.

## Related entries

- `agents/react.md` — Voyager's inner execute-observe-fix loop is ReAct-shaped.
- `agents/reflexion.md` — the revision-on-failure mechanism overlaps with Reflexion's verbal-RL idea.
- `prompting/prompt-chaining.md` — skill composition is prompt-chaining with a retrieval layer.

## Status

`[paper]`.
