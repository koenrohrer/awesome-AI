---
title: "Program-aided prompting"
badge: paper
evidence_url: https://arxiv.org/abs/2211.10435
evidence_summary: "PAL generates programs as intermediate reasoning steps and delegates solving to an interpreter on math, symbolic, and algorithmic tasks."
last_verified: 2026-05-19
stale_after_days: 45
arxiv_id: "2211.10435"
paper_venue: "ICML 2023"
authored_by_agent: true
agent_model: "gpt-5"
agent_run_id: "2026-05-19T13:03:49Z-awesome-ai-topic-scout-pr"
---

# Program-aided prompting `[paper]`

## One-sentence pitch

Generate executable code for the reasoning steps, then let an interpreter handle arithmetic or symbolic computation.

## Evidence

- **Primary citation:** Gao, L., Madaan, A., Zhou, S., Alon, U., Liu, P., Yang, Y., Callan, J., & Neubig, G. (2023). *PAL: Program-aided Language Models.* ICML 2023. [arxiv.org/abs/2211.10435](https://arxiv.org/abs/2211.10435); [PMLR proceedings](https://proceedings.mlr.press/v202/gao23f.html)

## What the paper shows

PAL keeps the language model responsible for reading a natural-language problem and translating the reasoning steps into executable code. The final computation is delegated to a runtime such as Python, so arithmetic, symbolic manipulation, and algorithmic bookkeeping are not left to token-by-token text generation.

The paper evaluates PAL across mathematical, symbolic, and algorithmic reasoning tasks from BIG-Bench Hard and related benchmarks. Its central finding is narrower than "code solves reasoning": program-aided prompting helps when the model can express the decomposition correctly and an interpreter can reliably execute the resulting steps.

## How to use it

- **Prompt for runnable code, not prose.** Few-shot examples should map a problem statement to a small program that computes the answer.
- **Keep the runtime constrained.** Treat generated code as untrusted. Execute it in a sandbox with tight filesystem, network, and time limits.
- **Return the computed answer.** The interpreter output is the source of the final value; the model should not recompute it in prose after execution.
- **Use it for exact computation.** Arithmetic word problems, table calculations, date math, and deterministic symbolic transforms are the natural fit.

## When it's not worth it

- **No safe execution environment.** Without sandboxing, generated code creates more risk than value.
- **Judgment-heavy tasks.** If the hard part is ambiguity, preference, or synthesis, a program may only make the answer look more precise.
- **Poor decomposition.** The interpreter can execute wrong logic perfectly; PAL does not fix misunderstood problem statements.

## Related entries

- `prompting/chain-of-thought.md` — PAL replaces prose-only intermediate reasoning with executable steps.
- `prompting/structured-output.md` — use schema constraints when the output shape matters more than computation.
- `agents/tool-use-openai.md` — provider-hosted code interpreters are one execution surface for program-aided workflows.

## Status

`[paper]`. Upgrade path: `[tested]` comparison on arithmetic or table-QA prompts with and without sandboxed code execution.
