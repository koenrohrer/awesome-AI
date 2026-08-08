# TraceLab `[paper]`

## One-sentence pitch

TraceLab publishes coding-agent trajectories so harness and serving decisions can be studied from workload evidence.

## Evidence

- **Paper:** Zhu et al. (2026). *TraceLab: Characterizing Coding Agent Workloads for LLM Serving.* [arxiv.org/abs/2606.30560](https://arxiv.org/abs/2606.30560)
- **Project:** [tracelab.cs.washington.edu](https://tracelab.cs.washington.edu/)
- **Artifacts:** [uw-syfi/TraceLab](https://github.com/uw-syfi/TraceLab)

## What it contributes

The authors report roughly 4,300 coding-agent sessions containing about 350,000 model steps and 430,000 tool calls from day-to-day Claude Code and Codex use. The release includes end-to-end trajectories rather than only prompts and final answers, making it possible to study context growth, tool-call bursts, token use, cache reuse, and failure patterns.

This is a method and dataset for workload characterization. It is not a general agent-quality benchmark: one collected workload cannot establish which model, framework, or orchestration design is best elsewhere.

## Practical use

- Derive realistic replay workloads before sizing an inference or tracing system.
- Compare context-management policies against observed trajectory lengths and reuse.
- Build failure labels around complete action histories instead of final answers alone.
- Check whether a synthetic load test preserves the tool and token distributions that matter.

Before using the dataset, inspect its collection procedure, licenses, and privacy handling. Keep the harness version and sampling slice with any result so later readers can reproduce the workload.

## Related entries

- [Agent harnesses](../learning/architecture/agent-harnesses.md) — the runtime surface represented by a trace.
- [Agent loop](agent-loop.md) — the repeated actions and observations captured in a trajectory.
- [SWE-Bench](swe-bench.md) — a task benchmark rather than a production-workload trace.

## Status

`[paper]`. Last reviewed 2026-08-06.
