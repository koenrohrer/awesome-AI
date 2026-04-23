# Emerging Watchlist + Agent-PR Loop — design

**Date:** 2026-04-22
**Status:** Locked for design. Implementation staged (see Launch waves).

## Purpose

Capture practitioner signal from X / Reddit / HN / named blogs that surfaces real patterns months before papers or provider docs catch up (the Karpathy-skills case), without diluting the repo's evidence bar or turning it into a vibes dump.

## The problem the existing bar misses

The current bars (`[paper]`, `[provider-doc]`, `[tested]`, `[vetted-tool]`, `[sourced]`) exclude patterns that are real, widely adopted by named practitioners, and useful — but not yet formalized. Waiting for formalization means the repo lags the field by months. Ignoring the signal means losing the repo's most valuable possible differentiator: surfacing what's actually being used, not just what's been published.

## Content tier: `[emerging]`

A new provisional badge with its own, visibly weaker bar. Reader sees at a glance that evidence strength is lower than `[paper]` / `[provider-doc]` / `[tested]`.

**Entry bar.** A candidate qualifies as `[emerging]` only if all of:

1. Attributable to a **named practitioner** from the curated source list (not an anonymous thread).
2. Has a **concrete artifact** — a repo, a gist, a runnable example, a blog post with code — not just a tweet-length assertion.
3. **Independently referenced** by at least two other practitioners from the curated source list (protects against clout-farming a single account).
4. Public and **citeable** via URL (no Discord leaks, no private-community signal).

**What `[emerging]` is not.** It is not "`[tested]` lite." It is not a path around the evidence bar for the maintainer's own hot takes. It is strictly for externally-surfaced practitioner signal that meets the four entry criteria.

## Placement in repo

Separate per-category Watchlist, not inline with hard-evidence entries.

- `prompting/watchlist.md`, `agents/watchlist.md`, `extensions/watchlist.md`, etc.
- Main category README links to the Watchlist as a distinct section, visually demoted ("Emerging — practitioner signal, not yet formalized").
- Readers who want only hard-evidence entries skip the Watchlist. Readers who want the frontier read it knowing what they're getting.
- Graduation = entry moves from `watchlist.md` to the main list with a hard badge. Movement between files is itself a liveness signal.

## Agent-PR loop (steady state)

The Watchlist is maintained by an agent opening PRs; humans merge or close. The repo is the only source of truth — no side-state, no backlog file.

**Agent responsibilities.**

- **Scout** the curated source list on a schedule.
- **Draft** candidate entries with provenance (source URL, named referencers, artifact link, date).
- **Open PRs** for adds, graduations (emerging → hard tier when conditions are met), and prunes.
- **Act on repo state** — when a `[paper]` lands that contradicts an existing `[emerging]` entry, open a prune or graduation PR on that entry.
- **Dedupe** against closed PR signatures so rejected candidates don't re-appear.

**Human responsibilities.**

- Merge or close each PR.
- Close with a reason label (taxonomy below) so the agent's next pass is better than the last.
- Periodically edit the source-list config (itself a PR-able file).

**What the human never has to do.** Maintain a separate Watchlist backlog. Schedule reviews. Remember what was proposed. Chase down stale entries. State lives in git.

## Scouting sources — curated, not algorithmic

The contamination risk is *algorithmic feeds* (X For You, r/all, Google results), not "the internet." Scouting inputs are author-gated or subreddit-specific, never open search.

| Source | Tier | Access | Notes |
|---|---|---|---|
| Named practitioner blogs / Substacks (Simon Willison, Swyx, Eugene Yan, Lilian Weng, Sebastian Raschka, Karpathy, Tim Dettmers, Jay Alammar, et al.) | 1 | RSS | Highest signal per minute of reading |
| GitHub trending + star-velocity in AI/ML topics | 1 | GitHub API | Code is the artifact; star velocity + diverse committers = real signal |
| Hacker News | 1 | Algolia API | Filter by keyword + min-comment-count; comments often beat articles |
| Vendor research posts / changelogs (Anthropic, OpenAI, Google DeepMind, Mistral, DeepSeek) | 1 | RSS / watch | Already upstream of `[provider-doc]`; used here as a graduation trigger |
| r/MachineLearning, r/LocalLLaMA | 2 | Reddit API | Specific subreddits only |
| X — curated handle list (~20-50 names) | 2 | Official API, author-gated | **Never** Search / Trending / For You |
| Podcast transcripts (Latent Space, Dwarkesh Patel) | 2 | RSS / site feeds | Lags audio 1-3 days, citeable |
| r/ClaudeAI, r/ChatGPT, r/OpenAI | — | — | Lagging indicators; skip for intake |
| r/singularity, r/all, X Search / For You | — | — | **Excluded.** GIGO vectors. |
| Discord servers | — | — | **Excluded.** Can't meet citeability bar |

**Source config.** `.watchlist/sources.yml` — plain YAML listing X handles, subreddits, RSS feeds, GitHub topics. Edited via PR. Agent reads this file as its only input whitelist.

## PR format

Three PR types, each with a required template.

**Add PR** — proposes a new `[emerging]` entry.

- Title: `[emerging] <category>: <one-line name>`
- Body: artifact URL, origin source URL, ≥2 independent referencer URLs from the source list, date first seen, agent confidence score, proposed watchlist file + line placement.
- Diff: single file change appending to `<category>/watchlist.md`.

**Graduation PR** — proposes moving an entry from `watchlist.md` to the main list.

- Title: `[graduate] <category>: <name> → [paper|provider-doc|tested|vetted-tool]`
- Body: evidence that triggered graduation (new paper URL / provider doc URL / link to reproducible test in `<category>/tests/`).
- Diff: removes line from `watchlist.md`, adds entry to main category README.

**Prune PR** — proposes removing an `[emerging]` entry.

- Title: `[prune] <category>: <name>`
- Body: explicit evidence (author retracted / contradicting paper / engagement collapsed by metric / 90 days with no graduation trigger).
- 7-day "last call" comment auto-posted by the agent; PR not mergeable before that elapses.
- Diff: removes line from `watchlist.md`. If pruned as *contradicted*, adds a line to `<category>/graveyard.md` with the contradicting evidence — this is the honest story for `[emerging]` entries that didn't pan out.

## Close-reason taxonomy (mandatory)

Every closed PR gets exactly one label. The agent reads closed PRs weekly and adjusts scouting.

- `off-topic` — doesn't fit a category
- `not-enough-signal` — fails entry bar (one referencer, anonymous, no artifact)
- `duplicate-of-#N` — already covered
- `contradicted` — evidence against it landed before merge
- `stretched-bar` — would require redefining `[emerging]` to include
- `source-degraded` — the scouting source itself is producing slop; feeds into source-health metric

## Rate limits

- **Max 5 open agent PRs at any time.** Agent pauses scouting above this.
- **Weekly scouting cycle.** No real-time firehose — the point is to catch up weekly, not to be first.
- **Agent self-scores candidates.** Only candidates above confidence threshold become PRs; remainder are dropped (not queued). Dropped candidates re-surface only if new referencers push them over threshold.

## Add/prune asymmetry

- **Add PRs: liberal bar.** A wrong `[emerging]` entry = one noisy line you later prune. Bias toward adding.
- **Prune PRs: strict bar.** Removing a valid entry = deleting information the community relied on. Require explicit cited evidence + 7-day last-call window.

## Source-health metric

Per source, rolling 30-day **merge rate** = merged / (merged + closed).

- Source below 10% merge rate over 30 days → auto-demoted (lower weight).
- Source below 5% merge rate over 60 days → agent opens a PR against `.watchlist/sources.yml` proposing removal.
- Source-degradation is a feature, not a bug: platforms decay, the source list should too.

## Launch waves

| Wave | What ships |
|---|---|
| v0 | Manual Watchlist: per-category `watchlist.md`, entry bar documented in `CONTRIBUTING.md`, quarterly review cadence. No agent. |
| v0.5 | Agent produces a weekly scouting digest as a single GitHub issue. Maintainer triages into Watchlist manually. |
| v1 | Full agent-PR loop: adds, graduations, prunes as PRs. Close-reason labels feed back into scouting. Rate-limited at 5 open. |
| v2 | Agent auto-merges the lowest-blast-radius class only — prune PRs where the original source URL 404s or the author explicitly retracted. Everything else stays human-merged. |
| *never* | Full autonomy. The human seat is part of the trust story. |

## Accepted losses (be honest)

- **Unknown practitioners.** Next-Karpathy-who-isn't-famous-yet won't be on any source list until someone on the list quotes them. Trade-off: coverage for cleanness.
- **Private-first signal.** Patterns worked out in Discords / Slacks for weeks before going public. Agent sees them only at the public threshold.
- **Selection bias.** The source list is itself a curatorial choice with its own blind spots. Mitigated but not eliminated by making the source file a PR-able artifact.

## Risks

- **Slop laundering.** AI-generated hype about AI patterns, scouted by an AI agent, landing in an AI resource guide. The curated-source design + source-health metric is the defense, but a single bad merge is reputationally expensive. Keep the human in the merge loop permanently.
- **Reviewer fatigue.** Rate limit + weekly cadence are load-bearing. If PR volume breaks the reviewer, the loop breaks.
- **Feedback loop gaming.** If scoring heuristics leak, clout-farmers optimize against them. Keep the rubric semi-opaque; don't publish exact thresholds.
- **Character shift.** Agent-curated feels different from human-curated. The README should name that the Watchlist is agent-assisted once v1 ships — don't launder the authorship.

## What we rejected, and why

- **Option #1 — scouting-only, no new badge.** Rejected: throws away attribution, pressures `[tested]` to stretch, and leaves genuinely useful practitioner signal sitting in a private backlog forever.
- **New `[community-vetted]` badge with engagement thresholds.** Rejected: thresholds are gameable, and anything numeric becomes the target of farming within a quarter.
- **Watchlist inline with hard-evidence entries in the main README.** Rejected: visually mixes evidence quality. Separate file per category is more honest and makes graduation visible.
- **Staged agent rollout V1 → V2 → V3 → full autonomy.** Rejected in favor of the agent-PR loop from v1 as steady state. Full autonomy never ships; the human merge is the trust story.
- **Open scouting (X Search, r/all, Google).** Rejected: GIGO. Curated follow list only.
- **Graveyard for every pruned entry.** Rejected: only `contradicted` prunes graveyard. Stale prunes (nothing materialized in 90 days) just disappear — the repo isn't a historical archive of hype.

## Open questions (to resolve before v0 ships)

- Exact quarterly cadence for the v0 manual review — first Sunday of Jan/Apr/Jul/Oct, or triggered by Watchlist size?
- Initial source list: who's on the v0 practitioner follow list? Target ~30 names to start; PR-able as `.watchlist/sources.yml`.
- Does the existing `CONTRIBUTING.md` need a new track for Watchlist submissions, or is this maintainer-only until v1?
