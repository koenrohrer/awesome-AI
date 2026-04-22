# Awesome AI

> A curated, **evidence-backed** guide to the AI landscape — prompting, agents, tool extensions, models, self-hosted setups, integrations, and education. Every entry carries a badge showing the evidence behind it. Nothing unlabeled.

Most "awesome AI" lists are vibes-based link dumps. This one isn't. If a technique claims to improve outputs, there's a paper, an official provider doc, or a maintainer-run test backing it. If a tool is listed, it's maintained, used, and fits a specific problem. If a hardware spec is quoted, it cites a third-party source by name.

## Contents

- [Badge legend](#badge-legend)
- [Prompting](#prompting) — evidence-backed techniques
- [Agents](#agents) — building autonomous agents
- [Extensions](#extensions) — skills, hooks, plugins, MCP servers, subagents
- [Models](#models) — per-provider deep dives
- [Self-hosted](#self-hosted) — runners, workflows, hardware
- [Integrations](#integrations) — AI + non-AI (shell, CI/CD, no-code)
- [Learning](#learning) — papers, courses, architecture, safety
- [Tools](#tools) — standalone AI apps
- [Contributing](#contributing)

## Badge legend

| Badge | Meaning |
|---|---|
| `[paper]` | Peer-reviewed paper, arxiv preprint, or official provider research post |
| `[provider-doc]` | Official provider documentation |
| `[tested]` | Maintainer ran it; before/after output lives in `<category>/tests/` |
| `[vetted-tool]` | Maintained (commit within 90 days) + used + scope-fit |
| `[sourced]` | Hardware claim with a named third-party source |

No entry is bare. If something doesn't carry a badge, it doesn't belong.

---

## Prompting

Evidence-backed prompting techniques. This is the flagship section — see [prompting/README.md](prompting/README.md) for the full list and [prompting/tests/](prompting/tests/) for reproducible before/after comparisons.

- **[Chain-of-thought prompting](prompting/chain-of-thought.md)** `[paper]` — "Let's think step by step" lifts reasoning accuracy on multi-step tasks by a double-digit margin on published benchmarks.
- **[Few-shot prompting](prompting/few-shot.md)** `[paper]` — In-context examples outperform zero-shot on most tasks; example count has diminishing returns past ~8.
- **[Self-consistency](prompting/self-consistency.md)** `[paper]` — Sample multiple CoT paths and take the majority vote; beats single-sample CoT on reasoning benchmarks.
- **[Self-refine](prompting/self-refine.md)** `[paper]` — Generate → critique → revise in three phases; improves quality where the model can recognize its own errors.
- **[Extended thinking / reasoning modes](prompting/extended-thinking.md)** `[provider-doc]` — Provider-native "think longer before answering" budgets on Claude, OpenAI o-series, and Gemini.
- **[Prompt caching](prompting/prompt-caching.md)** `[provider-doc]` — Reuse a static prefix across requests to cut cost ~90% and latency materially on repeated long-context calls.
- **[Structured output](prompting/structured-output.md)** `[provider-doc]` — JSON-schema-constrained generation eliminates parsing errors and reduces hallucinated fields.

## Agents

Building agents — not using them. See [agents/README.md](agents/README.md).

- **[ReAct: Reasoning + Acting](agents/react.md)** `[paper]` — Interleave Thought/Action/Observation; the pattern underlying most modern tool-using agents.
- **[Toolformer](agents/toolformer.md)** `[paper]` — Train tool-calling into the model via self-supervised filtering; the training-time complement to ReAct.
- **[Reflexion](agents/reflexion.md)** `[paper]` — After a failed attempt, generate a verbal self-reflection and retry with it in context.
- **[SWE-Bench](agents/swe-bench.md)** `[paper]` — The benchmark to cite when evaluating code-operating agents on real GitHub issues.
- **[Tool use (Anthropic / Claude)](agents/tool-use-anthropic.md)** `[provider-doc]` — Claude's structured tool-use API: schemas, `tool_use` blocks, parallel calls.
- **[Tool use (OpenAI)](agents/tool-use-openai.md)** `[provider-doc]` — OpenAI function calling + hosted tools (`web_search`, `code_interpreter`, etc.).

## Extensions

Make your existing AI tool do more. Each extension type is its own curated list:

- **[Skills](extensions/skills/)** — Claude Agent SDK skills and equivalents
- **[Hooks](extensions/hooks/)** — lifecycle hooks in Claude Code and similar tools
- **[Plugins](extensions/plugins/)** — tool-level plugins and addons
- **[MCP Servers](extensions/mcp-servers/)** — Model Context Protocol servers
- **[Subagents](extensions/subagents/)** — specialized agent configurations
- **[Slash commands](extensions/slash-commands/)** — custom commands

*Seeding in v0.2.*

## Models

Per-provider deep dives: available models, context windows, pricing, strengths/weaknesses (cited), best-fit tasks. See [models/README.md](models/README.md).

- **[Claude (Anthropic)](models/claude.md)** `[provider-doc]` — Opus/Sonnet/Haiku tiers, extended thinking, 90%-off prompt caching, strict tool use, long-context coding.
- **[GPT (OpenAI)](models/gpt.md)** `[provider-doc]` — Broad multimodality, hosted tools (`web_search`, `code_interpreter`), o-series reasoning, Batch API discount.
- **[Gemini (Google)](models/gemini.md)** `[provider-doc]` — 1M-token context, native multimodality (video/audio), explicit context caching, thinking budget control.
- **[Kimi (Moonshot AI)](models/kimi.md)** `[provider-doc]` — MoE flagship with long-context focus; selected releases published as open weights.
- **[Qwen (Alibaba)](models/qwen.md)** `[provider-doc]` — The most consistently open-weight frontier-adjacent family; strong specialist variants (Coder, VL, Math, Audio).
- **[DeepSeek](models/deepseek.md)** `[provider-doc]` — MoE + open-weight reasoning (R1); aggressive hosted-API pricing.

More providers (Grok, Llama, Mistral, Phi) land in a later wave.

## Self-hosted

Running models locally.

- **[Runners](self-hosted/runners/)** — ollama, LMStudio, llama.cpp, vLLM comparisons
- **[Workflows](self-hosted/workflows/)** — local-first setups that work end-to-end
- **[Hardware](self-hosted/hardware/)** — sourced hardware guides, `[sourced]` only

*Seeding in v0.2.*

## Integrations

**AI glued to non-AI systems.** This section is a genuine gap in the ecosystem — most lists stop at "here are 50 AI tools." This one shows you how to wire AI into what you already use.

- **[CI/CD](integrations/ci-cd/)** — PR review bots, test generation, release-note automation
- **[Shell](integrations/shell/)** — AI in shell scripts, git hooks, cron jobs
- **[No-code](integrations/no-code/)** — n8n, Zapier, Make, and similar

*Seeding in v0.2.*

## Learning

Foundations, not tips. Subsections: [papers](learning/papers/), [courses](learning/courses/), [architecture explainers](learning/architecture/), [safety](learning/safety/).

### Papers — foundational

- **[Attention Is All You Need](learning/papers/attention-is-all-you-need.md)** `[paper]` — Vaswani et al. 2017. The Transformer paper. The architecture underlying every modern LLM.
- **[Scaling laws (Kaplan + Chinchilla)](learning/papers/scaling-laws.md)** `[paper]` — Kaplan 2020 + Hoffmann 2022. Why bigger works, and what ratio of parameters to data is actually compute-optimal.
- **[InstructGPT / RLHF](learning/papers/instructgpt.md)** `[paper]` — Ouyang et al. 2022. The three-stage recipe (SFT → reward model → PPO) that made ChatGPT possible.
- **[Direct Preference Optimization (DPO)](learning/papers/dpo.md)** `[paper]` — Rafailov et al. 2023. Closed-form alignment from preference data without the RL loop.
- **[Constitutional AI](learning/papers/constitutional-ai.md)** `[paper]` — Bai et al. 2022. Replace human labelers with model self-critique against a constitution — the foundation of scalable alignment.

### Safety — prompt injection, jailbreaks, red-teaming

- **[Indirect Prompt Injection](learning/safety/indirect-prompt-injection.md)** `[paper]` — Greshake et al. 2023. The foundational framing of the injection threat when agents read untrusted content.
- **[GCG: Universal Adversarial Attacks](learning/safety/gcg-attack.md)** `[paper]` — Zou et al. 2023. Automated jailbreak discovery; suffixes transfer across models.
- **[Jailbroken: How Does LLM Safety Training Fail?](learning/safety/jailbreak-failure-modes.md)** `[paper]` — Wei et al. 2023. The framework for understanding *why* jailbreaks work (competing objectives, mismatched generalization).

## Tools

Standalone AI apps that don't fit a category. See [tools/README.md](tools/README.md).

*Seeding in v0.2.*

## Contributing

Every contribution goes through a template that enforces the evidence bar for its track. Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a PR.

Tracks and bars:

- **Techniques** (`prompting/`, `agents/`) — `[paper]`, `[provider-doc]`, or `[tested]` only.
- **Tools** (`extensions/`, `tools/`) — maintained + used + scope-fit.
- **Hardware** (`self-hosted/hardware/`) — third-party source cited by name.

## License

[CC0 1.0 Universal](LICENSE) — public domain dedication. Fork it, copy entries, build on it.
