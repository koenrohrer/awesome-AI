# Safety

Red-teaming, jailbreak resistance, and prompt injection. Tilted toward defensive content — how to evaluate and harden systems you're building.

## Inclusion bar

`[paper]` or `[provider-doc]` for claims about attack or defense efficacy. See [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Scope

- Attack taxonomies (direct prompt injection, indirect, data exfiltration, tool-call manipulation)
- Defensive patterns (input filtering, output constraints, sandboxing, permission models)
- Evaluation methodologies (red-team suites, automated jailbreak benchmarks)

## What doesn't belong

Actual novel jailbreak prompts or uplift content. This section is about understanding and defending, not publishing attack recipes.

## Entries

- **[Indirect Prompt Injection](indirect-prompt-injection.md)** `[paper]` — Greshake et al. 2023. The threat-model paper for agents that read untrusted content.
- **[GCG: Universal Adversarial Attacks](gcg-attack.md)** `[paper]` — Zou et al. 2023. Automated jailbreak discovery; suffixes transfer across models.
- **[Jailbroken: How Does LLM Safety Training Fail?](jailbreak-failure-modes.md)** `[paper]` — Wei et al. 2023. Framework for *why* jailbreaks work: competing objectives + mismatched generalization.
