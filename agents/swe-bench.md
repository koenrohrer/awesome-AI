# SWE-Bench `[paper]`

## One-sentence pitch

A benchmark of 2,294 real GitHub issues from mature Python repos — the agent gets the repo and the issue, must produce a patch that passes the upstream maintainers' test suite. The eval everyone quotes when they say "AI can code."

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
- **SWE-Bench Verified** — 500 problems human-validated for solvability; most papers now report on this variant.

## What a result *means*

A "pass" requires the agent's patch to compile, install, and make the hidden test suite go from failing to passing without breaking other tests. No partial credit. Numbers are hard to inflate, which is why the benchmark has staying power.

## Practical takeaways

- When evaluating a coding agent, SWE-Bench Verified (pass@1) is the single most citable number. Track the scaffold the score was obtained with — a given model's score varies substantially across different agent harnesses.
- The benchmark's age means leaderboard top performers are approaching saturation. Expect the community to move to SWE-Bench Multimodal, SWE-Bench Pro, or successor benchmarks over time.

## Related entries

- `agents/react.md` — nearly all SWE-Bench scaffolds are ReAct-style under the hood.

## Status

`[paper]`.
