# anydoc candidate brief

## Candidate

- Name: anydoc
- URL: https://github.com/firecrawl/anydoc
- Likely placement: `tools/`
- One-line scope: Converts Word, PowerPoint, Excel, OpenDocument, RTF, EPUB, CSV, and PDF into clean GitHub-Flavored Markdown so agents can read them.

## Evidence snapshot

- Maintenance: Active. The latest default-branch commit was `e754e1d` at `2026-08-13T21:39:50Z`, tagged `v0.1.9`. The GitHub API reports 30 commits in the preceding 90 days and the repository is not archived.
- Usage evidence: Maintainer ran it to convert Office documents to Markdown so coding agents could read them in-context.
- Docs/install: CLI via `npm install -g @firecrawl/anydoc`; Node.js via `npm install @firecrawl/anydoc`; Python via `pip install firecrawl-anydoc`; Rust via `cargo add anydoc`; agent skill via `npx skills add firecrawl/anydoc`.
- License/pricing: MIT. No service dependency — conversion runs locally with no model inference and no network calls.
- Risks or caveats: The repository was created 2026-08-03 and is on a `v0.1.x` line, so the 90-day maintenance bar passes on a short history rather than a long track record. Images and embedded objects render as alt text rather than extracted media.

## Placement note

`tools/README.md` routes anything that extends an agent through a skill to `extensions/`. anydoc does ship an agent skill (`npx skills add firecrawl/anydoc`), but the skill is a packaging layer over a standalone Rust library and CLI with Node, Python, and WebAssembly bindings. The tool stands on its own without any agent, so `tools/` is the closer fit.

## Inclusion decision

- Verdict: Include
- Badge: `[vetted-tool]`
- Rationale: Maintained with a commit three days before review, used by the maintainer to make Office documents readable to agents, and scope-fit to one named problem — document-to-Markdown conversion for agent consumption.

## Maintainer decisions

- Directory: `tools/`
- Supportable claim: anydoc converts 14 document formats to GitHub-Flavored Markdown locally, in Rust, without model inference.
- Entry caveat: Must note the young repository and `v0.1.x` version line.
- Follow-up questions: Which formats were exercised in the maintainer's run, and did any lose structure worth recording as a gotcha?

## Draft entry

- **[anydoc](https://github.com/firecrawl/anydoc)** `[vetted-tool]` — Local Rust converter turning Office, OpenDocument, EPUB, and PDF files into clean Markdown so agents can read them.
  - *Last commit:* 2026-08-13. *Used for:* converting Office documents to Markdown so coding agents could read them in-context. *Scope:* document-to-Markdown conversion for agent consumption.
  - *Gotcha:* Repository created 2026-08-03 and still on `v0.1.x`; images and embedded objects become alt text, not extracted files.

## Sources

- Official repo: https://github.com/firecrawl/anydoc
- Official docs: https://firecrawl.github.io/anydoc/
- GitHub API check: https://api.github.com/repos/firecrawl/anydoc
- Latest verified commit: https://github.com/firecrawl/anydoc/commit/e754e1d33a1a540ebc9226e36f11d3f401852c9e
