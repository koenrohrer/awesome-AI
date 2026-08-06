# AI landscape refresh evidence record — 2026-08-06

This is the audit record for the August 6, 2026 catalog refresh. It records what was checked, what was published, and what remained outside the live indexes. It is not a ranking or an endorsement list.

## Evidence rules

- **Review cutoff:** 2026-08-06 in America/New_York.
- **Availability:** API, product, preview, limited-access, open-weight, and retired states are recorded separately.
- **Sources:** live entries require a primary paper, official provider documentation, an official repository, or a maintainer-run test under the repository's existing badge rules.
- **Benchmarks:** vendor and author results remain attributed; this refresh constructs no cross-provider ranking.
- **Catalog scope:** no taxonomy, badge, schema, CI, dependency, or directory contract changed.

## Provider and product dispositions

### OpenAI and Anthropic

| Item | Official evidence | State on review date | Intended placement | Disposition |
|---|---|---|---|---|
| GPT-5.6 Sol | [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol) | Generally available in API, ChatGPT, and Codex | `providers/openai/models/` | Public dedicated page |
| GPT-5.6 Terra | [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-terra) | Generally available in API and available in ChatGPT Work/Codex | `providers/openai/models/` | Public dedicated page |
| GPT-5.6 Luna | [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-luna) | Generally available in API and available in ChatGPT Work/Codex | `providers/openai/models/` | Public dedicated page |
| GPT-5.5 / GPT-5.5 Pro | [Model catalog](https://developers.openai.com/api/docs/models) | Active API models; the old “API soon” description was false | Existing OpenAI pages | Existing-page correction |
| Claude Opus 5 | [Model overview](https://platform.claude.com/docs/en/about-claude/models/overview) | Generally available through API/cloud partners and paid Claude plans | `providers/anthropic/models/` | Public dedicated page |
| Claude Sonnet 5 | [Model overview](https://platform.claude.com/docs/en/about-claude/models/overview) | Generally available; introductory pricing is time-limited | `providers/anthropic/models/` | Public dedicated page |
| Claude Fable 5 | [Fable and Mythos guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5) | Generally available; product use is credit-metered | `providers/anthropic/models/` | Public dedicated page |
| Claude Mythos 5 | [Fable and Mythos guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5) | Limited Project Glasswing access, not general API availability | `providers/anthropic/models/` | Public dedicated page with limitation |

### Meta, Moonshot, DeepSeek, and Z.ai

| Item | Official evidence | State on review date | Intended placement | Disposition |
|---|---|---|---|---|
| Muse Model API / Spark 1.1 | [Meta announcement](https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/) | First-party hosted model API; distinct from Llama open weights | `providers/meta/` | Public product page; stale hosting claim corrected |
| Muse Image / Muse Video | [Meta announcement](https://ai.meta.com/blog/introducing-muse-image-muse-video-msl/) | Meta product surfaces; availability documented on page | `providers/meta/` | Public product page |
| “Muse Code” | Meta's official Muse sources above | No official standalone product or model source found | None | Excluded as unverified terminology |
| Kimi K3 | [Official repository](https://github.com/MoonshotAI/Kimi-K3), [Kimi platform](https://platform.kimi.ai/) | Hosted API and open weights; technical report is separate evidence | `providers/moonshot/models/` | Public dedicated page |
| DeepSeek V4 Flash July update | [Official API updates](https://api-docs.deepseek.com/updates/) | July snapshot incorporated into the V4 Flash page | Existing DeepSeek pages | Existing-page update |
| `deepseek-chat` / `deepseek-reasoner` | [V4 release note](https://api-docs.deepseek.com/news/news260424/) | Legacy aliases retired after 2026-07-24; historical pages retained | Existing DeepSeek pages | Existing-page correction, no deletion |
| GLM-5.2 | [Official model page](https://docs.z.ai/guides/llm/glm-5.2) | Hosted API model `glm-5.2`; text input/output, 1M context, 128K max output | Cross-provider directory | Docs-only row; no new provider folder |

### Google and xAI

| Item | Official evidence | State on review date | Intended placement | Disposition |
|---|---|---|---|---|
| Gemini 3.6 Flash | [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.6-flash) | Stable API model | `providers/google/models/` | Public dedicated page |
| Gemini 3.5 Flash-Lite | [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.5-flash-lite) | Stable API model | `providers/google/models/` | Public dedicated page |
| Gemini Computer Use | [Computer Use docs](https://ai.google.dev/gemini-api/docs/computer-use) | Preview tool capability with supported Gemini 3.5 IDs; not a standalone model ID | `providers/google/` | Public dedicated capability page |
| Gemini Omni Flash | [Model page](https://ai.google.dev/gemini-api/docs/models/gemini-omni-flash) | API model; modality and pricing documented separately | `providers/google/models/` | Public dedicated page |
| Gemini 3.5 Cyber | [Current model catalog](https://ai.google.dev/gemini-api/docs/models) | No current official model or product source found | None | Excluded as unverified terminology |
| Grok 4.5 | [Model page](https://docs.x.ai/developers/models/grok-4.5) | API model | `providers/xai/models/` | Public dedicated page |
| Grok Build | [Product overview](https://docs.x.ai/build/overview) | Product surface, not a model ID | `providers/xai/` | Public product page |

### Alibaba, Mistral, and MiniMax

| Item | Official evidence | State on review date | Intended placement | Disposition |
|---|---|---|---|---|
| Qwen 3.7 Max / Plus | [Model Studio catalog](https://help.aliyun.com/en/model-studio/text-generation-model/) | Plus is current; Max is supported legacy; no weight availability inferred | `providers/alibaba/README.md` | Docs-only rows |
| Qwen 3.8 Preview | [Model Studio catalog](https://help.aliyun.com/en/model-studio/text-generation-model/) | Preview ID offline and redirected to current `qwen3.8-max` | `providers/alibaba/README.md` | Superseded; current Max recorded, no preview row |
| Mistral OCR 4 | [Model card](https://docs.mistral.ai/models/model-cards/ocr-4-0) | Hosted specialist document service | `providers/mistral/README.md` | Docs-only row |
| Leanstral 1.5 | [Model card](https://docs.mistral.ai/models/model-cards/leanstral-1-5) | Labs API and open weights; retirement date recorded | `providers/mistral/README.md` | Docs-only row |
| Robostral Navigate | [Release post](https://mistral.ai/news/robostral-navigate/) | Research release without a documented public API ID | `providers/mistral/README.md` | Docs-only row |
| MiniMax M3 | [Official model page](https://www.minimax.io/models/text/m3), [repository](https://github.com/MiniMax-AI/MiniMax-M3) | Hosted API and open weights | `providers/minimax/models/` | Public dedicated page |

## Existing-tool maintenance review

These are the evidence briefs behind entries that already carried `[vetted-tool]`; this refresh did not perform or infer a new usage test. The 90-day maintenance checks were performed against official repositories on 2026-08-06.

| Tool | Official source | Observed maintenance disposition | Live-index action |
|---|---|---|---|
| Hermes Agent | [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | Evidence brief refreshed from current repository activity | Retain existing live entry and badge |
| OpenClaw | [OpenClaw repository](https://github.com/openclaw/openclaw) | Evidence brief refreshed from current repository activity | Retain existing live entry and badge |
| OpenShell | [NVIDIA/OpenShell](https://github.com/NVIDIA/OpenShell) | Evidence brief refreshed from current repository activity | Retain existing live entry and badge |
| Pi Agent | [earendil-works/pi](https://github.com/earendil-works/pi) | Canonical repository and maintenance date refreshed | Retain existing live entry and badge |

No tool was silently deleted, promoted, or newly assigned `[vetted-tool]` by this review.

## Product and framework evaluation backlog

Promotion requires a maintainer-run real task, current maintenance evidence, narrow scope, and separate approval. The briefs below define tests; they are not endorsements and do not enter live tool indexes.

### AnyDoc

- **Official source:** [firecrawl/anydoc](https://github.com/firecrawl/anydoc); tested npm package `@firecrawl/anydoc@0.1.6`.
- **Claimed scope:** Rust-based conversion of supported documents to GitHub-flavored Markdown; text PDFs are supported, while scanned PDFs require a different OCR path.
- **Maintenance signal:** newly active official repository and package release as of review; maturity remains a risk.
- **Likely placement:** document-conversion tool candidate, only after broader task testing.
- **Security/dependency considerations:** the npm package supplies a native converter; pin artifacts, sandbox untrusted documents, and enforce file-size, decompression, CPU, memory, and output limits.
- **Required evaluation:** convert born-digital, scanned, table-heavy, equation-heavy, and malformed PDFs; compare headings, paragraphs, tables, figures, reading order, failures, resource use, and deterministic output against the originals.
- **Observed trial:** with Node 24.16.0, `npx --yes @firecrawl/anydoc@0.1.6 /tmp/kimi-k3-report.pdf -o /tmp/kimi-k3-report-anydoc.md` converted Moonshot AI's 47-page Kimi K3 report (SHA-256 `1f2978d89a9d7f138f6d6ae5f17fd6890dc673abeaea7fca96c1eca432c75ce8`) into 1,605 lines / 192,679 bytes. Headings, prose, and the architecture table were searchable; title spacing, equations, figures, and multi-column tables were not publication-faithful and required PDF verification.
- **Disposition:** evaluation backlog. The single trial is insufficient for `[tested]` or `[vetted-tool]`.

### Agent frameworks and SDKs

| Candidate | Official docs/repository | Maintenance signal and claimed scope | Security/dependency considerations | Exact real task required for evaluation | Likely placement |
|---|---|---|---|---|---|
| NVIDIA NOOA | [NVIDIA-NeMo/labs-OO-Agents](https://github.com/NVIDIA-NeMo/labs-OO-Agents) | Active NVIDIA research repository for model-agnostic Python OOP agents; explicitly research software | Execute generated/runtime code only in a locked-down sandbox; review model/provider and transitive dependencies | Implement a ticket triage agent with read-only issue retrieval, typed classification, bounded retries, trace export, and hostile issue text | Backlog; possible framework candidate |
| OpenAI Symphony | [Repository](https://github.com/openai/symphony), [specification](https://github.com/openai/symphony/blob/main/SPEC.md) | Official preview for isolated, autonomous ticket-to-patch runs | Trusted environments only; audit credentials, workspace isolation, network access, issue-text injection, and duplicate side effects | Resolve a seeded repository issue in a disposable workspace, stop on policy-gated changes, and reproduce the trace | Backlog; possible coding-agent harness candidate |
| LangGraph | [Docs](https://docs.langchain.com/oss/python/langgraph/overview), [repository](https://github.com/langchain-ai/langgraph) | Maintained graph runtime with persistence, human interrupts, memory, and debugging | Review checkpoint storage, deserialization, tool permissions, provider dependencies, and server exposure | Run a resumable support workflow with fan-out, one injected tool failure, human approval, and exactly-once side effect | Backlog; possible orchestration-framework candidate |
| Microsoft Agent Framework | [Docs](https://learn.microsoft.com/en-gb/agent-framework/), [repository](https://github.com/microsoft/agent-framework) | Official Microsoft agent/workflow framework | Review preview/stability state, telemetry, cloud credentials, connectors, and persistence | Implement the same resumable support workflow and export a complete trace without Azure-only assumptions | Backlog; possible framework candidate |
| OpenAI Agents SDK | [Docs](https://openai.github.io/openai-agents-python/) | Maintained SDK for agents, handoffs, guardrails, sessions, tracing, and evals | Verify guardrail timing, hosted-tool data paths, trace retention, credentials, and provider coupling | Build a two-agent research handoff with schema validation, a denied write, bounded recovery, and trace assertions | Backlog; possible SDK candidate |
| Google ADK | [Documentation](https://adk.dev/), [JavaScript repository](https://github.com/google/adk-js) | Maintained agent development kit with model and deployment integrations | Review cloud/service identities, plugin/tool authority, session storage, telemetry, and runtime dependencies | Run the same research handoff locally and on its documented deployment path with identical graders | Backlog; possible SDK candidate |
| Vercel AI SDK 7 | [Release post](https://vercel.com/blog/ai-sdk-7), [changelog](https://vercel.com/changelog/ai-sdk-7) | Current ESM-only Node 22+ SDK with agent, harness, and observability surfaces | Requires a modern JS runtime; audit provider adapters, telemetry, tool approval, and server/client boundaries | Build a streamed web task with typed tools, approval, abort/resume, usage accounting, and trace export | Backlog; possible TypeScript SDK candidate |
| Claude Agent SDK | [Overview](https://code.claude.com/docs/en/agent-sdk/overview) | Official Python/TypeScript SDK exposing Claude Code's loop, tools, sessions, permissions, and observability | Self-hosted process has filesystem/shell reach; enforce permissions, sandboxing, secrets, and network policy | Repair a seeded bug in a disposable repo with denied out-of-scope edits, resume, and OTel trace verification | Backlog; possible coding-agent SDK candidate |
| PydanticAI | [Docs](https://pydantic.dev/docs/ai/overview/), [repository](https://github.com/pydantic/pydantic-ai) | Maintained typed Python agents with tools, evals, graph, durable execution, and approvals | Audit model adapters, durable-state serialization, instrumentation, tool validation, and optional extras | Build a typed extraction-and-approval workflow with malformed inputs, provider swap, replay, and deterministic graders | Backlog; possible Python SDK candidate |
| CrewAI | [Docs](https://docs.crewai.com/index), [repository](https://github.com/crewAIInc/crewAI) | Maintained crews and flows with state, persistence, and human review | Audit broad integrations, telemetry, code execution, credentials, dependency weight, and delegation loops | Run a three-role content audit with fixed artifacts, no shared hidden state, injected failure, and cost/trace accounting | Backlog; possible orchestration candidate |
| GitHub Agentic Workflows | [Docs](https://docs.github.com/en/copilot/concepts/agents/about-github-agentic-workflows), [repository](https://github.com/github/gh-aw) | Public preview; Markdown compiles to locked workflows with read-only defaults and controlled outputs | GitHub Actions permissions, prompt injection, action pinning, egress, secrets, artifact retention, and billing are material | Triage a hostile test issue in a sandbox repository, produce a proposed patch artifact, and prove no unapproved write occurred | Backlog; possible GitHub workflow candidate |
| AWS AgentCore Harness | [Harness docs](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/harness.html), [release notes](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/release-notes.html) | Generally available managed loop with tools, memory, identity, observability, and per-session microVM isolation | Cloud IAM, service boundary, data residency, network egress, session isolation, logging, and cost require explicit review | Execute a long-running support task with least-privilege IAM, resume after interruption, denied egress, and trace/cost export | Backlog; possible managed-runtime candidate |

## Research promoted into the practical catalog

| Work | Primary evidence | Repository gap filled | Disposition |
|---|---|---|---|
| TraceLab | [Paper](https://arxiv.org/abs/2606.30560), [project](https://tracelab.cs.washington.edu/) | Real agent-trajectory observability and workload characterization | Public page under `agents/` |
| Context Folding | [ICML 2026 paper](https://openreview.net/forum?id=lNRgWoGfYg) | Structured active-context reduction for long-horizon agents | Public architecture explainer |
| GPT-Red | [Paper](https://arxiv.org/abs/2607.26115), [OpenAI report](https://openai.com/index/unlocking-self-improvement-gpt-red/) | Defensive automated prompt-injection evaluation | Public safety page without exploit uplift |
| Kimi K3 architecture | [Technical report](https://github.com/MoonshotAI/Kimi-K3/blob/main/k3_tech_report.pdf) | Current MoE and MTP case study | Existing architecture explainers and model page updated |
| MosaicKV | [Paper](https://arxiv.org/abs/2607.00760) | Two-dimensional KV-cache compression | Existing KV-cache explainer updated |
| SWE-Bench audits | [Verified audit](https://openai.com/index/why-we-no-longer-evaluate-swe-bench-verified/), [Pro audit](https://openai.com/index/separating-signal-from-noise-coding-evaluations/) | Benchmark test-quality and contamination caveats | Existing SWE-Bench page updated |

## Research held from landmark entries

| Work | Primary evidence | Disposition and reason |
|---|---|---|
| NOOA | [Official repository](https://github.com/NVIDIA-NeMo/labs-OO-Agents) | Evaluation backlog only: research software needs a maintainer-run real task and security review |
| LongHorizon-Harness | [Preprint](https://arxiv.org/abs/2608.01964) | Excluded for now: extremely recent preprint without independent replication or established repository fit |
| StructAgent | [Preprint](https://arxiv.org/abs/2607.11388) | Excluded for now: recent, environment-specific computer-use work overlaps the broader harness/state guidance |
| CHILL-Harness | [Preprint](https://arxiv.org/abs/2607.25825) | Excluded for now: recent adaptive-harness result without independent replication |
| Scaffold Effect | [Artifact repository](https://github.com/namanvats/scaffold-effects) | Excluded for now: agent-harness work remains insufficiently established for a landmark entry; disambiguated from the unrelated clinical VLM paper with the same phrase |
| iLLaDA | [Preprint](https://arxiv.org/abs/2606.25331) | Excluded for now: diffusion-language-model research does not yet fill a practical gap in the current architecture index |
| GRAM | [Google DeepMind publication](https://deepmind.google/research/publications/252981/) | Excluded for now: promising sabotage-auditing work needs a safe, reproducible protocol before public promotion |
| Global Workspace | [Anthropic research](https://www.anthropic.com/research/global-workspace), [paper](https://transformer-circuits.pub/2026/workspace/index.html) | Excluded for now: mechanistic-interpretability evidence should not be conflated with agent shared memory or orchestration |

## Rejected update strategies

- Link dumping without a fit decision, availability state, and nearest index.
- Unsupported rankings or comparisons assembled from incompatible provider benchmarks.
- Assigning `[vetted-tool]` to anything not exercised through the repository's maintainer-run bar.
- Adding a new taxonomy, provider folder, badge, schema, dependency, or CI workflow for this refresh.
- Publishing speculative model details, aliases, prices, limits, or modalities.
- Deleting historical provider or candidate pages merely because an alias retired or a maintenance check became stale.

## Acceptance ledger

- Every confirmed release above has a public, existing-page, backlog, superseded, or excluded disposition.
- Dedicated pages must be reachable from both their provider overview and `providers/models/README.md`.
- Product/framework backlog briefs remain outside live tool indexes and carry no endorsement badge.
- All live quantitative claims remain attached to a primary source and, where applicable, labeled provider- or author-reported.
- Automated frontmatter, citation, trailer, and tool-freshness validation remain unavailable because this repository does not implement those checks.
