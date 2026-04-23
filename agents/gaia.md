# GAIA: General AI Assistant benchmark `[paper]`

## One-sentence pitch

A benchmark of 466 real-world questions that require multi-step tool use, multimodal reasoning, and web navigation — designed so the answers are trivially verifiable, unambiguously correct, and hard for current agents. The go-to general-assistant eval.

## Evidence

- **Primary citation:** Mialon, G., Fourrier, C., Swift, C., Wolf, T., LeCun, Y., & Scialom, T. (2023). *GAIA: a benchmark for General AI Assistants.* [arxiv.org/abs/2311.12983](https://arxiv.org/abs/2311.12983)
- **Leaderboard:** [HuggingFace GAIA leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard).

## The design

GAIA problems are **easy for humans, hard for AI**:
- ~92% human solve rate on the three difficulty tiers.
- At benchmark release, frontier LLMs solved ~15% even with tool access and web browsing.
- Each question has a **short, unambiguous answer** (a number, a name, a date) — graded by exact-match, so there's no room for partial credit or interpretation gaming.

## Three difficulty levels

- **Level 1** — answerable with a single tool + simple reasoning (e.g., reading one webpage).
- **Level 2** — requires multiple tools, often chained (web + calculator + calendar + table parsing).
- **Level 3** — long-horizon task with many steps, frequently requiring multimodal inputs (images, videos, PDFs).

## Why it matters

Benchmarks like SWE-Bench isolate a single skill (code). GAIA grades the whole **agent stack**: the model's reasoning, the tool inventory, the web-navigation scaffold, error recovery, multimodal handling. A low GAIA score with a strong base model usually points to the scaffold, not the model.

## What results actually tell you

- **Level 1 pass rate** — is your agent competent at single-hop tool use?
- **Level 2 pass rate** — can it chain tools without losing state?
- **Level 3 pass rate** — does it survive long horizons? Most agents fall off a cliff here.

Compare agent scaffolds against the same base model: often, the difference between a 40% GAIA score and a 60% one is entirely scaffold, not model.

## Related entries

- `agents/swe-bench.md` — the coding-specific analog.
- `agents/react.md` — the loop pattern most GAIA scaffolds use.

## Status

`[paper]`.
