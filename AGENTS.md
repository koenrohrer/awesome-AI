# Agent Contributor Guide

This repository is an evidence-backed AI landscape guide. It is not a link dump. Every entry must make a narrow claim, point to evidence, and carry one of the approved badges.

## Project Contract

- Keep the badge vocabulary exhaustive: `[paper]`, `[provider-doc]`, `[tested]`, `[vetted-tool]`, `[sourced]`.
- Do not add bare entries. If a candidate cannot clear a badge bar, leave it out or document it as unvetted only where a README explicitly allows candidates.
- Prefer primary sources: papers, official provider docs, official repos, upstream release pages, spec sheets, or named reproducible benchmarks.
- Keep entry pitches short, factual, and scoped. Avoid hype, rankings without methodology, and vague claims like "best", "powerful", or "game-changing".
- Update the nearest README index when adding, removing, or renaming a page.
- Preserve relative Markdown links and the existing list style.

## Evidence Rules

- `[paper]`: cite the paper or official research post directly. Include enough citation detail to identify the work.
- `[provider-doc]`: link to official provider documentation, not a tutorial about the docs.
- `[tested]`: include maintainer-run before/after material in the relevant `tests/<slug>/` directory.
- `[vetted-tool]`: verify maintained, used, and scope-fit. Do not invent maintainer usage.
- `[sourced]`: cite named third-party hardware sources for every spec, benchmark, or compatibility claim.

## Working Process

1. Read the nearest `AGENTS.md`, then the nearest `README.md`, then `CONTRIBUTING.md` if changing entries.
2. For current model, pricing, tool maintenance, or hardware facts, verify against live upstream sources before editing.
3. Add the smallest useful page or entry. Do not broaden the taxonomy without a clear gap.
4. Run a quick Markdown sanity check by reviewing links, headings, badge spelling, and index coverage.

## Repository Shape

- `prompting/` and `agents/`: flagship original technique content.
- `extensions/`, `tools/`, and `self-hosted/runners/`: vetted tools and extension surfaces.
- `providers/`: per-provider deep dives with date-sensitive model and product-surface facts.
- `self-hosted/hardware/`: sourced hardware guidance only.
- `integrations/`: AI wired into existing non-AI workflows.
- `learning/`: foundational papers, courses, architecture, and safety.
- `.github/`: contribution templates and CI guardrails.
