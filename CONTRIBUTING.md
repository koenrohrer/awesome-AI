# Contributing

Thank you for considering a contribution. This list has an opinionated editorial bar. Entries that don't clear the bar get closed, not merged — please read this document before opening a PR.

## The core rule

**Every entry carries a badge. No entry is bare.**

If you're submitting something that can't carry one of the badges below, this isn't the right list for it.

## Badges and their requirements

### `[paper]`
Peer-reviewed paper, arxiv preprint, or official provider research post (Anthropic, OpenAI, Google DeepMind, Meta AI, etc.).
- **Required:** Full citation *and* a direct link.
- **Required:** One-sentence summary of what the paper shows.
- **Rejected:** Blog posts that merely describe a paper. Link to the paper directly.

### `[provider-doc]`
Official provider documentation.
- **Required:** Link to the official doc (e.g., `docs.anthropic.com`, `platform.openai.com/docs`, `ai.google.dev`).
- **Rejected:** Third-party tutorials, even accurate ones.

### `[tested]`
A maintainer ran it and recorded before/after output.
- **Required:** Before/after files in `<category>/tests/<slug>/`.
- **Required:** The prompt, model, and full output for both arms. Redact nothing material.
- **Required:** A short `README.md` in the test directory stating what the test measures.
- Only maintainers can grant this badge for now. Community-run tests can become `[tested]` after a maintainer reproduces them.

### `[vetted-tool]`
A tool that meets **all three**:
1. **Maintained** — at least one commit in the last 90 days.
2. **Used** — the submitter has actually run it on a real task, not just read the README. Describe the task briefly.
3. **Scope-fit** — the submission names one specific problem it solves well. "General purpose" is not a scope.

### `[sourced]`
A hardware claim (spec, benchmark, compatibility note) with a named third-party source.
- **Required:** The source — Apple spec sheet, NVIDIA whitepaper, a specific YouTube benchmark video with creator name, HuggingFace leaderboard entry, etc.
- **Rejected:** "I heard that…", "Reddit says…", unnamed forum posts.

## How to submit

1. Open an issue using the template matching your track:
   - **Technique** → [Suggest a technique](.github/ISSUE_TEMPLATE/suggest-technique.yml)
   - **Provider page / provider surface** → use the Technique template for now (until a dedicated provider template exists)
   - **Tool** → [Suggest a tool](.github/ISSUE_TEMPLATE/suggest-tool.yml)
   - **Hardware** → [Suggest a hardware entry](.github/ISSUE_TEMPLATE/suggest-hardware.yml)
2. If the issue passes review, open a PR adding the entry. Use [PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md).
3. CI must pass: `awesome-lint`, `markdown-link-check`, and the custom "every entry has a badge" check.

## Entry format

```markdown
- **[Name](link)** `[badge]` — one sentence: what it is + who it's for.
  - *Evidence:* citation, doc URL, or path to the test directory (as required by the badge).
```

Keep the one-sentence pitch under 140 characters. If you need more, write a subpage in the category's directory and link to it from the bullet.

## What doesn't belong

- **Un-evidenced tips.** "I find X works well" without a paper, doc, or test.
- **Link dumps.** Bulk submissions of many links at once without per-entry justification.
- **Self-promotion with no track record.** New tools with no adoption and no tests.
- **Vibes-based model rankings.** "Kimi is better than Claude for writing" — unless you cite an eval, it's out.
- **Anything that duplicates an existing entry.** Improve the existing entry instead.

## Staleness

We run a monthly CI check that flags entries where:
- A tool has had no commits in >90 days (moves from `[vetted-tool]` to re-review).
- A link has been broken for >7 days (removed).
- A `[paper]` or `[provider-doc]` points to a page that 404s or changed URL.

If you notice an entry has gone stale, open an issue — don't wait for the cron.

## Review bar

Maintainers review for:
1. Does it carry a valid badge?
2. Does the evidence actually support the one-sentence pitch?
3. Is it a duplicate?
4. Does it fit the category?

We aim to review within a week. Lack of response isn't rejection — ping the issue politely after two weeks.

## License

By contributing, you agree that your contributions are licensed under [CC0 1.0 Universal](LICENSE). You confirm you have the right to contribute the content.
