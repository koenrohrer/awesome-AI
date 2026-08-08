# SWE-Bench `[paper]`

## One-sentence pitch

A benchmark that grades coding-agent patches against tests derived from real GitHub issues.

## Evidence

- **Primary citation:** Jimenez, C. E., Yang, J., Wettig, A., Yao, S., Pei, K., Press, O., & Narasimhan, K. (2024). *SWE-Bench: Can Language Models Resolve Real-World GitHub Issues?* ICLR 2024. [arxiv.org/abs/2310.06770](https://arxiv.org/abs/2310.06770)
- **Leaderboard:** [swebench.com](https://www.swebench.com/) — current results with methodology links.

## Why it matters

Most code benchmarks (HumanEval, MBPP) are single-function puzzles with perfect problem statements. SWE-Bench grades against:
- Real, multi-file repositories
- Natural-language issue descriptions written by actual users
- The maintainers' original test suite as the judge

It's the benchmark that separates "can write a function" from "can operate a codebase."

## Variants

- **SWE-Bench** (full) — 2,294 problems across 12 repos.
- **SWE-Bench Lite** — 300-problem subset for faster iteration.
- **SWE-Bench Verified** — 500 problems selected through human validation, but later auditing found substantial test-quality and contamination concerns.
- **SWE-Bench Pro** — a harder successor with broader repositories and longer tasks; a later audit also found substantial broken-task risk.

## What a result *means*

A "pass" requires the patch to satisfy the benchmark's test harness. That is evidence about the model-plus-harness on a specific task image, but it is not automatically evidence that the patch satisfies the issue's intended behavior.

OpenAI's February 2026 audit examined 138 of the 500 SWE-Bench Verified tasks (27.6%), selected because one model did not solve them consistently. It reported material issues in 59.4% of that audited subset and also found contamination concerns. In July, OpenAI reported that a manual review identified issues in 249 of 731 SWE-Bench Pro tasks, including overly strict tests, underspecified or misleading prompts, and inadequate test coverage. These are OpenAI's audit findings, not a neutral re-labeling of every task.

Sources:

- [Why we no longer evaluate on SWE-bench Verified](https://openai.com/index/why-we-no-longer-evaluate-swe-bench-verified/)
- [Separating signal from noise in coding evaluations](https://openai.com/index/separating-signal-from-noise-coding-evaluations/)

## Practical takeaways

- Treat any aggregate as a model-plus-harness result. Record the exact task set, image, model snapshot, tool surface, retry budget, and grader.
- Audit a sample of failures and passes against the issue's intended behavior. Test success can reward an incomplete patch when coverage is weak or reject a correct patch when tests are over-constrained.
- Prefer multiple task sets and real repository acceptance tests over one headline number.

## Related entries

- `agents/react.md` — nearly all SWE-Bench scaffolds are ReAct-style under the hood.

## Status

`[paper]`. Last reviewed 2026-08-06.
