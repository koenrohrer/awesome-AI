# awesome-AI — design

**Date:** 2026-04-22
**Status:** Locked for v0.1 scaffold

## Purpose

A curated, evidence-backed GitHub awesome-list covering the full AI landscape — prompting, agents, tool extensions, models, self-hosted setups, integrations, education — without the "trust me bro" padding that plagues most AI link lists.

## Editorial stance

Hybrid repo: mostly curated (awesome-list style), with **original content concentrated in `prompting/` and `agents/`** as the flagship. The differentiator is not "more links" but a **strict, visible evidence bar** on every entry.

## Two tracks, different bars

| Track | Scope | Bar |
|---|---|---|
| Techniques | `prompting/`, `agents/` | A+C+D only: academic paper, official provider doc, or maintainer-run test with before/after output. No vibes. |
| Tools | `extensions/`, `tools/` | `maintained` (commit within 90 days) + `used` (maintainer ran it) + `scope-fit` (names a specific problem). |
| Hardware | `self-hosted/hardware/` | Third-party source cited by name (Apple spec sheet, NVIDIA whitepaper, named YouTube benchmark, HuggingFace leaderboard). No rumors. |

## Badge vocabulary (exhaustive)

- `[paper]` — academic paper or provider research post, citation required
- `[provider-doc]` — official provider documentation, link required
- `[tested]` — maintainer ran it; before/after lives in `<category>/tests/`
- `[vetted-tool]` — meets maintained + used + scope-fit
- `[sourced]` — hardware claim with a named third-party source

Nothing bare. Every entry carries a badge.

## Taxonomy (seven top-level buckets + tools)

1. `prompting/` — evidence-backed prompting techniques (flagship)
2. `agents/` — building agents: tool use, memory, planning, evals
3. `extensions/` — skills, hooks, plugins, mcp-servers, subagents, slash-commands
4. `models/` — per-provider deep dives (claude, gpt, gemini, kimi, qwen, deepseek, grok, mistral, llama)
5. `self-hosted/` — runners, workflows, hardware (sourced)
6. `integrations/` — AI glued to non-AI: shell, CI/CD, no-code. Genuine gap.
7. `learning/` — papers, courses, architecture explainers, safety
8. `tools/` — standalone AI apps that don't fit a category

## Governance

- PRs must use the track-specific issue template. No bar-skipping.
- `awesome-lint` + `markdown-link-check` run on every PR.
- Monthly stale-check cron opens an issue for entries older than 6 months. Maintainer re-verifies or demotes.
- No link dumps. Every entry justifies its place.

## Launch waves

| Wave | What ships |
|---|---|
| v0.1 | Directory tree, README index, CONTRIBUTING, templates, CI, ~4 seed entries in `prompting/` to prove the format |
| v0.2 | 20+ entries in `prompting/` and `agents/`, first 3 `models/*.md`, first `integrations/` examples |
| v0.3 | Announce, open to contributions |

## What we rejected, and why

- **Pure curator model.** Rejected — no differentiation from the existing dozen AI awesome-lists.
- **Flexible "mix of evidence tiers" including community reports.** Rejected in favor of strict A+C+D — the maintainer wanted a bar Reddit threads couldn't clear.
- **Hardware as original content.** Rejected — maintainer lacks the physical hardware to benchmark credibly. Made it curated-with-citation instead.
- **Flat "techniques / tools / hardware" taxonomy.** Rejected in favor of user-scannable buckets (Skills, Hooks, Models, etc.) because that's how people actually search.
