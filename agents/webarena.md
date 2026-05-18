---
title: "WebArena"
badge: paper
evidence_url: https://arxiv.org/abs/2307.13854
evidence_summary: "WebArena evaluates web agents on reproducible tasks across fully functional sites."
last_verified: 2026-05-18
stale_after_days: 45
arxiv_id: "2307.13854"
paper_venue: "arXiv 2023"
authored_by_agent: true
agent_model: "gpt-5-codex"
agent_run_id: "2026-05-18T08:27:33Z-awesome-ai-topic-scout-pr"
---

# WebArena `[paper]`

## One-sentence pitch

A benchmark environment for web agents where success is measured by completing natural-language tasks in reproducible, functional websites rather than answering static questions.

## Evidence

- **Primary citation:** Zhou, S., Xu, F. F., Zhu, H., Zhou, X., Lo, R., Sridhar, A., Cheng, X., Ou, T., Bisk, Y., Fried, D., Alon, U., & Neubig, G. (2023). *WebArena: A Realistic Web Environment for Building Autonomous Agents.* arXiv:2307.13854. [arxiv.org/abs/2307.13854](https://arxiv.org/abs/2307.13854)

## What the benchmark tests

WebArena evaluates agents that operate websites, not just agents that answer questions about webpages. The paper defines a reproducible environment spanning e-commerce, social forum, software-development, and content-management tasks, with external tools and knowledge sources available where the task design needs them.

The grading target is functional correctness: did the agent complete the requested web task, including the state changes the task required?

## Why it matters

GAIA grades broad assistant behavior, and SWE-Bench grades code patches. WebArena isolates the browser-agent layer: navigation, form filling, multi-step state tracking, tool observation handling, and recovery from web UI mistakes.

## Baseline context

The paper reports a best GPT-4-based baseline at 14.41% end-to-end task success, compared with 78.24% human performance. Treat that as a historical baseline from the paper, not a current leaderboard claim.

## Use it when

- You are comparing browser-agent scaffolds against the same base model.
- You need reproducible site state instead of public webpages that change under test.
- You want failures that expose planning, observation, and UI-control problems separately from raw model knowledge.

## Related entries

- `agents/gaia.md` — broad general-assistant evaluation.
- `agents/swe-bench.md` — codebase-operating agent evaluation.
- `agents/react.md` — the tool-use loop pattern many web-agent baselines start from.

## Status

`[paper]`. Last source check: 2026-05-18.
