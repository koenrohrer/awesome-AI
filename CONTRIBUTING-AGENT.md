# Contributing as an AI agent

**Spec version:** 1.0
**Effective:** 2026-04-22
**Supplements:** [CONTRIBUTING.md](CONTRIBUTING.md)

This document is the contract for an AI agent maintaining this repo.

- If you are a human contributor, read [CONTRIBUTING.md](CONTRIBUTING.md) — this file does not apply to you.
- If you are an AI agent, every rule below is **normative**. CI will reject PRs that violate the machine-enforceable rules; the maintainer will reject PRs that violate the rest.

The goal of this spec is to let an agent do useful maintenance work without introducing the failure modes agents typically introduce: fabricated citations, interpolated specs, silent link-rot, badge inflation, and scope creep.

---

## 1. Scope

### 1.1 What the agent is allowed to do

- **Refresh** existing entries when the source of truth has changed (new model version, updated pricing, clarifying provider doc).
- **Add new entries** under existing categories using the templates in this document, provided the evidence clears the bar.
- **Fix** dead links, broken references, or invalid frontmatter identified by CI.
- **Flag** inconsistencies, staleness, and conflicts — but open an issue rather than guessing the fix.
- **Maintain the Watchlist** per §12 — scout curated sources, open Add / Graduation / Prune PRs for `<category>/watchlist.md` files on a weekly cadence.

### 1.2 What the agent is NOT allowed to do

- Modify [CONTRIBUTING.md](CONTRIBUTING.md), this file, the badge legend in [README.md](README.md), [LICENSE](LICENSE), or the CI workflow files under `.github/workflows/` without an explicit human-authored issue approving the change.
- Modify `.watchlist/sources.yml` to **add** sources. The agent may propose removals when source-health triggers fire (§8, §12.4); additions are human-only.
- Delete entries. Escalate instead (see §8).
- Refactor the directory structure.
- Add new categories or change the taxonomy.
- Merge its own PRs (see §9.2 for the narrow exception reserved for a later trust wave).
- Force-push, rewrite history, bypass hooks, or disable CI checks.
- Run `git reset --hard`, `git clean -fdx`, or any destructive operation on branches it did not create in the current session.

### 1.3 One task per PR

A single PR addresses a single coherent change. Examples of acceptable scope:

- "Refresh all Anthropic model pages after the Opus 4.8 announcement."
- "Add three new `learning/papers/` entries on mixture-of-experts."
- "Fix the 14 dead links flagged by the staleness cron."

Examples of **un**acceptable scope:

- "Monthly maintenance update" covering unrelated categories.
- Any PR that both restructures and adds new content.

If the agent's task expands mid-work, it stops and opens a new PR for the new scope.

---

## 2. Evidence bar (stricter for agents than humans)

The base evidence bar from [CONTRIBUTING.md](CONTRIBUTING.md) applies to all contributors. The following restrictions apply **only to AI agents**:

### 2.1 Badges the agent may assign

- `[paper]` — the agent must have retrieved the cited arxiv/DOI URL and confirmed it returns HTTP 200. The entry summary must not contradict the paper's abstract or introduction.
- `[provider-doc]` — the agent must have retrieved the cited URL and confirmed it returns HTTP 200. Every quantitative claim (context window, price, benchmark number) must appear in the retrieved text or a sibling page on the same provider's official domain.
- `[emerging]` — the agent may assign `[emerging]` **only** to entries in `<category>/watchlist.md` files (never inline with hard-evidence entries in main category READMEs). A candidate must meet all four Watchlist entry criteria (§12.2) and all sources cited must come from `.watchlist/sources.yml`. See §12 for the full Watchlist loop.

### 2.2 Badges the agent MUST NOT assign unilaterally

- `[tested]` — requires a maintainer-signed `README.md` in the test directory (see §4.3 of [CONTRIBUTING.md](CONTRIBUTING.md)). The agent may draft a test but must **not** assign the badge itself; a human grants it by merging a separate PR that adds the `maintainer_signed: true` frontmatter field.
- `[vetted-tool]` — requires a human-confirmed "used on a real task" attestation. The agent may gather maintenance signals (last-commit date, star count, recent releases) and draft a candidate entry, but must leave the badge as `[vetted-tool-pending]` and assign it to a human for sign-off.
- `[sourced]` — the agent may link Apple/NVIDIA/AMD spec-sheet pages, HuggingFace leaderboard entries with DOIs, or GitHub benchmark repos. The agent MUST NOT cite YouTube videos, Twitter posts, Reddit threads, or blog posts — a human must introduce those sources through a human-authored PR.

### 2.3 Disallowed source types (applies to all agent-authored content)

The agent must not cite — for **any** badge, including `[emerging]`:

- X Search results, X Trending, X "For You" feeds (named-handle posts from `.watchlist/sources.yml` are allowed for `[emerging]` only; never for hard-evidence badges)
- Reddit `r/all`, Google search results, HackerNews front page scraping (specific subreddits named in `.watchlist/sources.yml` are allowed for `[emerging]` only)
- Discord and Slack screenshots or leaks (fails citeability)
- Blog posts *about* papers (link the paper directly)
- YouTube videos (human-only — see §2.2)
- Wayback Machine snapshots of retired pages (escalate instead)
- Any URL the agent could not successfully fetch

---

## 3. Frontmatter schema (normative)

Every content entry (`.md` file under `prompting/`, `agents/`, `models/`, `extensions/`, `self-hosted/`, `integrations/`, `learning/`, `tools/`, `providers/`) must begin with YAML frontmatter.

### 3.1 Required fields (every entry)

```yaml
---
title: "Chain-of-thought prompting"
badge: paper                    # one of: paper | provider-doc | tested | vetted-tool | vetted-tool-pending | sourced | emerging
evidence_url: https://arxiv.org/abs/2201.11903
evidence_summary: "Few-shot CoT lifts reasoning accuracy on GSM8K et al. by double-digit margins at sufficient scale."
last_verified: 2026-04-22       # ISO 8601 date, updated when an agent or human confirms the source still supports the entry's claims
stale_after_days: 45            # optional; defaults to 45 for hard badges, 30 for [emerging]
---
```

### 3.2 Badge-specific required fields

**`[paper]`:**
```yaml
arxiv_id: "2201.11903"          # or doi: "10.48550/..."
paper_venue: "NeurIPS 2022"
```

**`[provider-doc]`:**
```yaml
provider: anthropic              # slug: anthropic | openai | google | xai | moonshot | qwen | deepseek | meta | mistral | ...
```

**`[tested]`:**
```yaml
test_dir: prompting/tests/chain-of-thought
maintainer_signed: true          # MUST be absent or false in agent-authored PRs
```

**`[vetted-tool]` or `[vetted-tool-pending]`:**
```yaml
repo_url: https://github.com/...
last_commit_date: 2026-03-14
used_by: koenrohrer              # GitHub handle — MUST be absent in agent-authored PRs proposing a new vetted-tool
scope: "MCP server for Stripe test-mode API inspection"
```

**`[sourced]`:**
```yaml
source_name: "Apple M4 Max product page"
source_url: https://www.apple.com/shop/buy-mac/...
```

**`[emerging]`:** (only valid in `<category>/watchlist.md` files)
```yaml
originated_by: "Karpathy"                 # named practitioner from .watchlist/sources.yml
artifact_url: https://github.com/.../example
origin_source_url: https://karpathy.bearblog.dev/...    # where the agent first saw this
referencer_urls:                          # ≥2 independent referencers, each from sources.yml
  - https://simonwillison.net/...
  - https://eugeneyan.com/...
first_seen_date: 2026-04-19
watchlist_category: prompting             # the <category>/watchlist.md it lives in
agent_confidence: 0.78                    # self-scored, 0–1; only candidates above threshold get PR'd
# `evidence_url` on an [emerging] entry is the artifact itself; `evidence_summary`
# states the pattern in one line with attribution.
```

### 3.3 Agent-specific metadata (required on every agent-authored entry)

```yaml
authored_by_agent: true
agent_model: "claude-opus-4-7"   # slug; for human contributions this field is absent
agent_run_id: "2026-04-22T14:03:00Z-abc123"   # unique per run, for traceability
```

### 3.4 Validation

CI runs `frontmatter-check`:
- Every `.md` in a content directory has frontmatter.
- Every required field is present and well-typed.
- `badge` is from the allowed enum.
- `last_verified` is a valid ISO 8601 date within the past 365 days.
- Badge-specific required fields are present for the assigned badge.
- `[emerging]` entries may only appear in files matching `*/watchlist.md`; entries with any other badge may not appear in those files.
- `[emerging]` entries' `originated_by` is listed in `.watchlist/sources.yml`, and every URL in `referencer_urls` comes from a domain/handle in that file.

PRs that fail `frontmatter-check` are rejected automatically.

---

## 4. Mandatory actions

Every agent PR must do all of the following.

### 4.1 Update `last_verified` on every entry it touches

Even cosmetic edits require a fresh `last_verified` if the agent re-confirmed the source in the course of editing.

### 4.2 Resolve every URL it writes

Before opening the PR, the agent fetches each URL it has added or modified. If a fetch fails (non-200, timeout, redirect loop, cert error), the agent:

1. Does not silently change the URL.
2. Does not silently remove the entry.
3. Opens an issue describing the failure and holds the PR until human guidance arrives (see §8).

### 4.3 Respect the commit-trailer contract (see §6)

Every commit includes machine-readable trailers listing the sources it verified against.

### 4.4 Stay within scope

If mid-task the agent identifies additional work (e.g., five other entries have the same kind of error), it completes only the original task and opens a follow-up issue for the rest.

### 4.5 Preserve human-authored content verbatim

When an agent edits an entry that was originally human-authored (`authored_by_agent: false` or field absent), it must not rewrite prose in the `evidence_summary` or body beyond what the source-of-truth change requires. Light edits to reflect a changed fact are fine; rephrasing for style is not.

---

## 5. Prohibited actions

The agent must not:

- Invent, guess, or approximate any citation identifier (arxiv ID, DOI, version number, date, price, benchmark score, context-window size).
- Quote or paraphrase sources it did not successfully retrieve in this run.
- Modify content the maintainer marked `agent_editable: false` in frontmatter.
- Move, rename, or restructure files (any directory change is refactor scope — forbidden by §1.2).
- Merge its own PRs, approve its own PRs, or mark its own `[tested]` / `[vetted-tool]` badges.
- Respond to `@mentions` in PR comments by making code changes without a new task invocation — comment-driven edits are a rabbit hole the agent always loses.
- Edit this file or the badge legend in [README.md](README.md) without a human-authored issue explicitly directing the change.

### 5.1 Watchlist-specific prohibitions

- Inline `[emerging]` entries into main category READMEs or hard-evidence files — `[emerging]` lives only in `<category>/watchlist.md`.
- Add sources to `.watchlist/sources.yml`. Removal proposals via PR are allowed when source-health triggers fire (§12.4); additions are human-only.
- Exceed the 5-open-agent-PR rate limit (§12.5). Above the limit, the agent pauses scouting and waits for merges or closures.
- Merge or close its own Prune PRs before the mandatory 7-day last-call window has elapsed (§12.3.3).
- Re-propose a candidate that was previously closed with a `not-enough-signal`, `stretched-bar`, or `off-topic` label, unless materially new evidence has accrued (new referencers, new artifact) — track the signature of closed PRs and dedupe against it.
- Use `.watchlist/sources.yml` as cover for citing otherwise-disallowed sources in hard-evidence entries. `[emerging]` sources are valid for `[emerging]` only; a `[paper]` or `[provider-doc]` entry still requires its own qualifying citation (§2.3).

---

## 6. Commit and PR format

### 6.1 Commit message format

Every commit produced by the agent must use this shape:

```
<subject: imperative, under 72 chars>

<body: what changed and why, wrapped at 72 chars; may span multiple paragraphs>

Verified-sources:
  - https://arxiv.org/abs/2201.11903
  - https://docs.anthropic.com/en/docs/build-with-claude/tool-use
Agent-run-id: 2026-04-22T14:03:00Z-abc123
Agent-model: claude-opus-4-7
```

The `Verified-sources:` trailer is mandatory — one URL per line, indented by two spaces. Every URL here must have been fetched in this run and returned HTTP 200 (or be on the known ignore list).

### 6.2 PR description template

The agent opens PRs using this template (enforced by the existing PR template plus agent-specific additions):

```markdown
## Summary
<one sentence>

## Scope
<which entries / categories this PR affects>

## Sources verified (HTTP 200 in this run)
- <url>
- <url>

## Sources attempted but failed (if any)
- <url> — <status code or error>
  - *Action taken:* <opened issue #N | entry flagged | etc.>

## Frontmatter changes
<list of entries whose frontmatter was updated, with old → new values for changed fields>

## Run context
- Agent model: <slug>
- Run ID: <ISO timestamp + short hash>
- Spec version this PR targets: 1.0
```

### 6.3 Branch naming

Branches follow the pattern `agent/<date>/<short-task-slug>`:
- `agent/2026-04-22/refresh-anthropic-models`
- `agent/2026-04-22/add-moe-papers`

Watchlist PRs prefix the slug with the PR type:
- `agent/2026-04-22/emerging-add-prompting-claude-skills`
- `agent/2026-04-22/emerging-graduate-agents-react-retry`
- `agent/2026-04-22/emerging-prune-extensions-abandoned-mcp`

### 6.4 One commit, or a logical series

The agent prefers one commit per PR. If the work genuinely requires multiple commits (e.g., split "add template" + "add content using template"), each commit still follows §6.1 independently.

### 6.5 Watchlist PR types

Three dedicated PR types for the Watchlist loop. Each has its own title prefix, body template, and mergeability rules — all defined in §12.3.

| Type | Title prefix | Purpose |
|---|---|---|
| Add | `[emerging] <category>: <name>` | Propose a new `[emerging]` entry in `<category>/watchlist.md` |
| Graduate | `[graduate] <category>: <name> → [<hard-badge>]` | Move an entry from `watchlist.md` to the main list when a hard badge becomes earnable |
| Prune | `[prune] <category>: <name>` | Remove an `[emerging]` entry (contradicted, retracted, or 90-day stale). Mandatory 7-day last-call window. |

---

## 7. CI contract

The following CI jobs gate every agent-authored PR. A PR that fails any of them is not eligible for merge even if a human approves the content.

### 7.1 Existing jobs (carry over)

- `badge-check` — every entry's rendered bullet in README.md carries one of the five legal badges.
- `link-check` (markdown-link-check) — every link in changed files resolves or is in the ignore list.

### 7.2 New jobs required by this spec

- `frontmatter-check` — every content `.md` has valid frontmatter with required fields, correct types, and a `badge` from the enum.
- `citation-check` — for every `[paper]` entry, fetch `https://arxiv.org/abs/<arxiv_id>` and confirm HTTP 200; for every `[provider-doc]` entry, fetch `evidence_url` and confirm HTTP 200.
- `staleness-check` (cron, nightly) — open an issue for any entry where `last_verified + stale_after_days < today`. Does not block PRs; produces a living to-do list.
- `trailer-check` — every commit in the PR has `Verified-sources:` and `Agent-run-id:` trailers; every URL in `Verified-sources:` is in the changed files of the commit.
- `watchlist-sources-check` — for every `[emerging]` entry, verify `originated_by` is listed in `.watchlist/sources.yml` and each URL in `referencer_urls` is from a domain/handle listed there. Verify the entry lives in a `*/watchlist.md` file.
- `watchlist-placement-check` — `[emerging]` badges appear only in `*/watchlist.md`; those files contain only `[emerging]` entries.
- `watchlist-rate-limit-check` — on PR open, count open agent-authored PRs (labeled `agent-pr`). If ≥5, mark the new PR `rate-limited` and block merge until the count drops below the limit.
- `watchlist-lastcall-check` — Prune PRs are not mergeable until the bot comment `[last-call: YYYY-MM-DD]` is more than 7 days old. (The agent posts this comment when opening; merge UI blocks on it.)

### 7.3 Implementation note

These jobs do not exist yet. The spec precedes the implementation. Agent onboarding must not happen until `frontmatter-check`, `citation-check`, and `trailer-check` are green on `main`. The Watchlist-specific jobs (`watchlist-*`) must be green before the agent is permitted to open `[emerging]` PRs.

---

## 8. Escalation protocol

The agent escalates — rather than guessing — in all of the following situations:

| Situation | Action |
|---|---|
| A previously-valid URL returns 404 | Open issue titled `[stale-link] <entry-path>`, include the old URL and the HTTP status. Do not edit the entry. |
| A cited paper appears retracted, withdrawn, or replaced | Open issue titled `[retraction] <entry-path>`. Do not remove the entry. |
| A provider releases a model that conflicts with an existing entry's claims | Open issue titled `[conflict] <entry-path>`. Draft the update in a separate PR but mark it "blocked on §8 resolution" until the maintainer comments. |
| A fetch succeeds but the content doesn't support the entry's claim | Open issue titled `[unsupported-claim] <entry-path>`. Do not silently weaken the claim. |
| The agent's task as given conflicts with this spec | Stop. Open issue titled `[scope-conflict]`. Do not proceed. |
| A human edit to an entry contradicts retrieved sources | Open issue titled `[human-disagreement]`. The agent defers to the human until resolved. |
| A scouting source drops below 10% 30-day merge rate | Demote the source locally for the next scouting cycle (lower weight). Below 5% over 60 days, open a PR against `.watchlist/sources.yml` proposing removal, titled `[source-health] remove <source>`. |
| An `[emerging]` entry's artifact URL 404s mid-lifetime | Open a Prune PR (contradicted-by-link-rot) with the 7-day last-call window. Do not silently remove. |
| A `[paper]` or `[provider-doc]` lands that clearly supersedes an `[emerging]` entry | Open a Graduation PR; let the maintainer decide graduate vs prune. |
| Closed-PR label feedback suggests systemic scouting drift (e.g., many `stretched-bar` closes from one source) | Open issue titled `[scouting-drift]` summarizing the pattern. Do not adjust thresholds or rubric without maintainer input. |

### 8.1 Issue format for escalations

```markdown
## Escalation type
<from the table above>

## Entry affected
<path/to/entry.md>

## What I found
<one paragraph; factual, no speculation>

## URLs attempted
- <url> → <status>

## What I did not do (and why)
<one sentence — references §8>

## Requested guidance
<what decision is needed from the maintainer>
```

Escalation issues are labeled `agent-escalation`.

---

## 9. Review process

### 9.1 Maintainer review checklist

When reviewing an agent PR, the maintainer confirms:

1. CI is green.
2. Every `Verified-sources:` URL resolved when you spot-check 2–3 of them.
3. No `[tested]` / `[vetted-tool]` badge was self-assigned.
4. `last_verified` is updated on every touched entry.
5. The PR respects its declared scope.
6. No changes to the restricted files listed in §1.2.
7. Prose in existing human-authored entries is preserved per §4.5.

For Watchlist PRs, add:

8. **Add PR** — `originated_by` and every `referencer_url` trace back to `.watchlist/sources.yml`; the artifact URL resolves; the entry is in the correct `<category>/watchlist.md`.
9. **Graduation PR** — the triggering hard-evidence source (`[paper]` / `[provider-doc]` / `[tested]`) is genuine and actually supports the claim; the `watchlist.md` line is removed in the same PR.
10. **Prune PR** — 7-day last-call has elapsed; prune reason matches the evidence; if `contradicted`, the `<category>/graveyard.md` line exists.

The checklist fits on a post-it deliberately. If review gets complicated, the PR is too big — ask the agent to split it.

### 9.2 Trust graduation

This spec assumes human merge-gating. After 50 consecutive clean agent PRs, the maintainer may move specific narrow task types to automatic-merge-on-CI-green. Trust graduation happens task-type-by-task-type, recorded in a `TRUST.md` file the maintainer controls and the agent does not edit.

Initial candidates for graduation, in ascending risk order:

1. **Prune PRs where the source URL 404s** — the safest auto-merge; the loss is at most deleting an already-dead link.
2. **Prune PRs where the named author explicitly retracted** (signed retraction linked, human-verifiable).
3. **Staleness-triggered `last_verified` refreshes** where no content changed and all cited URLs still resolve.

Full autonomy is not on this list and never will be. The human merge is the repo's trust story.

---

## 10. Changing this spec

### 10.1 Versioning

This spec uses semantic versioning:

- **Major** bump for changes that invalidate prior agent behavior (e.g., adding a required frontmatter field, removing an allowed badge).
- **Minor** bump for additive, non-breaking changes (e.g., adding a new badge-specific optional field).
- **Patch** bump for typo fixes and clarifications.

The `Spec version:` at the top of this file is the authoritative version. Agents must record the version they targeted in their PR description (§6.2).

### 10.2 Who changes it

Only the maintainer. An agent must never submit a PR that modifies this file. If an agent believes the spec is wrong or ambiguous, it opens an issue labeled `agent-spec-feedback` and waits.

### 10.3 Deprecation

When a rule is removed or relaxed, the spec notes the version in which it was changed:

```markdown
> **Removed in v1.1:** the `agent_model` frontmatter field is no longer required.
```

Old entries remain valid until the next major version, at which point a migration PR cleans them up.

---

## 11. Onboarding checklist (before any agent does its first real PR)

Before the agent is pointed at the repo:

### 11.1 Core infrastructure (required for any agent PR)

- [ ] CI jobs `frontmatter-check`, `citation-check`, and `trailer-check` exist and pass on `main`.
- [ ] Existing content entries have been migrated to include the frontmatter required by §3 (can be done in a single human-authored migration PR).
- [ ] This spec is linked from the main [README.md](README.md) and [CONTRIBUTING.md](CONTRIBUTING.md).
- [ ] The agent's system prompt or task instructions point to this file explicitly.
- [ ] The agent does not have merge permission on its own PRs.
- [ ] `TRUST.md` exists (initially empty — auto-merge granted task-type-by-task-type over time).

### 11.2 Watchlist infrastructure (required before agent opens `[emerging]` PRs)

- [ ] `.watchlist/sources.yml` exists with an initial source list (tier, handle/URL, access method, notes — schema per §12.4).
- [ ] One `<category>/watchlist.md` file exists per top-level content category, each with an explanatory header and empty-state copy.
- [ ] `<category>/graveyard.md` files exist for categories where `contradicted` prunes will accrue.
- [ ] CI jobs `watchlist-sources-check`, `watchlist-placement-check`, `watchlist-rate-limit-check`, and `watchlist-lastcall-check` exist and pass on `main`.
- [ ] Main category READMEs link to their Watchlist file in a visually-demoted section ("Emerging — practitioner signal, not yet formalized").
- [ ] A label set exists on the GitHub repo: `agent-pr`, `agent-escalation`, `rate-limited`, plus the close-reason taxonomy from §12.6 (`off-topic`, `not-enough-signal`, `duplicate-of-N`, `contradicted`, `stretched-bar`, `source-degraded`).

Until all boxes in §11.1 are checked, the agent operates in draft mode only — it may open PRs, but the maintainer does not merge them until the infrastructure is live. Until all boxes in §11.2 are also checked, the agent must not open `[emerging]` / Graduation / Prune PRs.

---

## 12. Watchlist loop (`[emerging]`)

The Watchlist captures practitioner signal — patterns real named practitioners are using that haven't yet been formalized in a paper or provider doc. It exists because waiting for formalization means the repo lags the field by months; ignoring it means missing the repo's most valuable differentiator.

**Full design rationale:** [`docs/plans/2026-04-22-emerging-watchlist-design.md`](docs/plans/2026-04-22-emerging-watchlist-design.md). This section is the agent-binding portion; the design doc has the "why" behind each rule.

### 12.1 Placement and visibility

- `[emerging]` entries live **only** in `<category>/watchlist.md` — never inline with hard-evidence entries in a main category README.
- Main category READMEs link to the Watchlist as a distinct, visually-demoted section ("Emerging — practitioner signal, not yet formalized").
- `<category>/graveyard.md` holds entries pruned as `contradicted`, with a one-line note of the contradicting evidence.
- Stale prunes (90 days with no graduation trigger) are removed without a graveyard entry — the repo is not a historical archive of hype.

### 12.2 Entry bar (all four required)

A candidate qualifies as `[emerging]` only if **all** of the following hold:

1. Attributable to a **named practitioner** listed in `.watchlist/sources.yml` (not an anonymous thread).
2. Has a **concrete artifact** — a repo, a gist, a runnable example, a blog post with code — not a tweet-length assertion.
3. **Independently referenced** by at least two other named practitioners from `.watchlist/sources.yml` (protects against clout-farming a single account).
4. **Public and citeable** via URL (no Discord leaks, no private-community signal, no Wayback-only).

All four go in the entry's frontmatter (§3.2). CI enforces source-list membership; the maintainer checks the substantive qualification during review.

### 12.3 Watchlist PR types

#### 12.3.1 Add PR

- **Title:** `[emerging] <category>: <one-line name>`
- **Label:** `agent-pr`, `emerging-add`
- **Diff:** single-file append to `<category>/watchlist.md` with the new entry and its frontmatter.
- **Body template:**

```markdown
## Artifact
<url>

## Origin source
<url from .watchlist/sources.yml>

## Independent referencers (≥2, all from sources.yml)
- <url>
- <url>

## First seen
<YYYY-MM-DD>

## Proposed placement
`<category>/watchlist.md` — section: <topic grouping>

## Agent confidence
<0.00–1.00>

## Why this clears the four-criterion bar (§12.2)
<one paragraph>
```

#### 12.3.2 Graduation PR

- **Title:** `[graduate] <category>: <name> → [<hard-badge>]`
- **Label:** `agent-pr`, `emerging-graduate`
- **Trigger:** a qualifying hard-evidence source has emerged (paper published, provider doc shipped, maintainer-run test in `<category>/tests/`).
- **Diff:** removes line from `<category>/watchlist.md`; adds entry to main category README with the new hard badge; updates frontmatter to the new badge's required fields.
- **Body template:**

```markdown
## Graduating entry
`<category>/watchlist.md:<line>` — <name>

## Target badge
`[paper]` | `[provider-doc]` | `[tested]`

## Triggering evidence
<full citation or URL>

## Why this now clears the hard bar
<one paragraph>
```

#### 12.3.3 Prune PR

- **Title:** `[prune] <category>: <name>`
- **Label:** `agent-pr`, `emerging-prune`
- **Triggers** (exactly one, stated in body):
  - `contradicted` — evidence against the pattern landed (paper, retraction, author disavowal)
  - `source-degraded` — the originating source's merge rate dropped below threshold (§12.4)
  - `stale-90d` — no graduation trigger in 90 days
  - `link-rot` — artifact URL 404s with no replacement
- **Mandatory 7-day last-call window.** On PR open, the agent posts a comment with `[last-call: YYYY-MM-DD]` where the date is 7 days out. The PR is not mergeable before that date; `watchlist-lastcall-check` enforces this.
- **Diff:** removes line from `<category>/watchlist.md`. If trigger is `contradicted`, also adds a line to `<category>/graveyard.md` with the contradicting evidence URL.

### 12.4 Source list — `.watchlist/sources.yml`

The only allowed input whitelist for Watchlist scouting. No open search, no For-You feeds, no r/all, no Google. Schema:

```yaml
# .watchlist/sources.yml
version: 1
sources:
  - handle: "karpathy"
    tier: 1
    access: rss
    url: https://karpathy.bearblog.dev/rss/
    domains: [karpathy.bearblog.dev, github.com/karpathy]
    added: 2026-04-22
    notes: "Highest signal per minute of reading."

  - handle: "r/LocalLLaMA"
    tier: 2
    access: reddit-api
    subreddit: LocalLLaMA
    added: 2026-04-22
    notes: "Subreddit-scoped only. Never r/all."

  - handle: "anthropic-research"
    tier: 1
    access: rss
    url: https://www.anthropic.com/research/rss.xml
    domains: [anthropic.com]
    added: 2026-04-22
    notes: "Upstream of [provider-doc]; used as a graduation trigger."
```

Only the **maintainer** adds entries to this file. The agent may open a PR *removing* an entry when source-health triggers fire (see below), but never one adding.

**Source-health thresholds:**

- Rolling 30-day merge rate = (merged agent PRs from this source) / (merged + closed agent PRs from this source).
- Below **10%** over 30 days → agent demotes the source locally (lower weight in next scouting cycle).
- Below **5%** over 60 days → agent opens a `[source-health] remove <source>` PR against `.watchlist/sources.yml`.

### 12.5 Rate limits

- **Maximum 5 open agent-authored PRs across the repo at any time.** Above the limit, the agent pauses scouting and waits for human merge/close actions to drain the queue.
- **Weekly scouting cadence.** No real-time firehose. The goal is to catch up weekly, not to be first to surface a pattern.
- **Agent self-scores candidates.** Only candidates above the confidence threshold (set by the agent's runtime config, not in this spec) become PRs; the remainder are dropped, not queued. Dropped candidates re-surface only when new referencers push them back above threshold.

### 12.6 Close-reason taxonomy (mandatory label on every closed PR)

The maintainer applies exactly one label when closing an agent PR. The agent reads closed PRs and adjusts scouting. Undisambiguated close-no-label = signal the agent cannot learn from.

| Label | Meaning |
|---|---|
| `off-topic` | Doesn't fit a category in this repo. |
| `not-enough-signal` | Failed the four-criterion entry bar (§12.2). |
| `duplicate-of-N` | Already covered by entry or PR #N. |
| `contradicted` | Evidence against the pattern landed before merge. |
| `stretched-bar` | Would require redefining `[emerging]` to admit. |
| `source-degraded` | The originating source in `.watchlist/sources.yml` is producing slop; feeds into source-health metric (§12.4). |

### 12.7 Accepted losses

The Watchlist by design does not catch:

- **Unknown practitioners.** Next-Karpathy-who-isn't-famous-yet is invisible until somebody on the list quotes them. The trade-off is coverage for cleanness.
- **Private-first signal.** Patterns worked out in Discords/Slacks before going public.
- **Selection bias in `.watchlist/sources.yml`.** The source list is itself a curatorial choice with blind spots. Mitigated but not eliminated by making the source file a PR-able artifact humans edit.

These are acknowledged, not bugs to be fixed by bending the bar.

### 12.8 Add/prune asymmetry (editorial)

- **Add PRs get a liberal bar.** A wrong `[emerging]` entry = one noisy Watchlist line you later prune. Bias toward proposing.
- **Prune PRs get a strict bar.** Removing a valid entry deletes information the community relied on. Require explicit cited evidence + the 7-day last-call window. Never skip the window, even when the evidence feels airtight.

### 12.9 Launch waves

| Wave | What ships |
|---|---|
| v0 | Manual Watchlist: per-category `watchlist.md`, entry bar documented in `CONTRIBUTING.md`, quarterly human review cadence. No agent. |
| v0.5 | Agent produces a weekly scouting digest as a single GitHub issue. Maintainer triages into Watchlist manually. |
| v1 | Full agent-PR loop: Add / Graduation / Prune PRs. Close-reason labels feed back into scouting. Rate-limited at 5 open. |
| v2 | Agent auto-merges only the lowest-blast-radius Prune PR class (per §9.2 graduation ladder). Everything else stays human-merged. |
| *never* | Full autonomy. The human seat is part of the trust story. |

This spec covers v1 onward. v0 and v0.5 do not require agent PRs against this spec.
