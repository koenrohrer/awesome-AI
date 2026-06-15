# GAIA: General AI Assistant benchmark `[paper]`

## One-sentence pitch

A benchmark of 466 real-world questions requiring multi-step tool use, multimodal inputs, and web navigation. Answers are short and verifiable, which makes GAIA useful for evaluating general-assistant scaffolds.

## Evidence

- **Primary citation:** Mialon, G., Fourrier, C., Swift, C., Wolf, T., LeCun, Y., & Scialom, T. (2023). *GAIA: a benchmark for General AI Assistants.* [arxiv.org/abs/2311.12983](https://arxiv.org/abs/2311.12983)
- **Leaderboard:** [HuggingFace GAIA leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard).

## The design

GAIA problems are designed to be easy for humans and hard for AI systems:
- ~92% human solve rate on the three difficulty tiers.
- At benchmark release, frontier LLMs solved ~15% even with tool access and web browsing.
- Each question has a **short, unambiguous answer** (a number, a name, a date) and is graded by exact match.

## Three difficulty levels

- **Level 1** — answerable with a single tool + simple reasoning (e.g., reading one webpage).
- **Level 2** — requires multiple tools, often chained (web + calculator + calendar + table parsing).
- **Level 3** — long-horizon task with many steps, frequently requiring multimodal inputs (images, videos, PDFs).

## Why it matters

SWE-Bench isolates code repair. GAIA evaluates the model, tool inventory, web-navigation scaffold, error recovery, and multimodal handling together. A low GAIA score with a strong base model can point to scaffold problems.

## How to read results

- **Level 1 pass rate** — is your agent competent at single-hop tool use?
- **Level 2 pass rate** — can it chain tools without losing state?
- **Level 3 pass rate** — can it complete long-horizon tasks with many dependent steps?

Compare agent scaffolds against the same base model. Otherwise model quality and scaffold quality are hard to separate.

## Related entries

- `agents/swe-bench.md` — the coding-specific analog.
- `agents/react.md` — the loop pattern most GAIA scaffolds use.

## Status

`[paper]`.
