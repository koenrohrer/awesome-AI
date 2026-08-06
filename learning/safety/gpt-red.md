# GPT-Red `[paper]`

## One-sentence pitch

GPT-Red uses automated attacker-defender self-play to discover prompt-injection failures and turn them into defensive evaluations.

## Evidence

- **Paper:** Wallace et al. (2026). *GPT-Red: Automated Red Teaming via Self-Play at Scale.* [arxiv.org/abs/2607.26115](https://arxiv.org/abs/2607.26115)
- **Provider report:** [Unlocking self-improvement for AI agents with GPT-Red](https://openai.com/index/unlocking-self-improvement-gpt-red/)

## Defensive use

GPT-Red alternates between an attacker that searches for prompt-injection strategies and a defender that updates its mitigations. The useful artifact for builders is a repeatable evaluation loop: define the protected instruction, constrain the attack surface, grade whether the injected instruction changed behavior, and preserve newly found failures as regression cases.

OpenAI reports that this self-play setup found new attacks and improved defenses in its evaluated environments. Those are provider-reported results. They do not show that one defense generalizes to different tools, permissions, models, or untrusted-content channels.

## Safe evaluation pattern

- Use synthetic secrets, inert tools, and an isolated environment.
- Test indirect injection in documents and tool output as well as direct user prompts.
- Grade both task completion and policy preservation; a system that refuses everything is not useful.
- Store attack categories and pass/fail outcomes without publishing reusable exploit strings.
- Route suspected real-world bypasses through the affected provider's disclosure process.

This page intentionally omits working jailbreak prompts and optimization details that would increase exploit capability.

## Related entries

- [Indirect Prompt Injection](indirect-prompt-injection.md) — the core threat model for untrusted retrieved content.
- [GCG](gcg-attack.md) — an earlier automated adversarial-search method.
- [Agent harnesses](../architecture/agent-harnesses.md) — the permission and isolation boundary defenses must protect.

## Status

`[paper]`. Last reviewed 2026-08-06.
