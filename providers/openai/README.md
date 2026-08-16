# OpenAI `[provider-doc]`

*Last reviewed: 2026-08-16. GPT-5.6 is generally available across the OpenAI API, ChatGPT, and Codex. Verify exact access and pricing against the live [models page](https://developers.openai.com/api/docs/models) before deployment.*

## Product surfaces

- **[Codex](codex.md)** — OpenAI's coding-agent surface for parallel software-engineering work and automations.
- **[ChatGPT Desktop](chatgpt-desktop.md)** — desktop app surface for local workflows, screenshots, files, and IDE-connected chat.
- **[Image generation](image-generation.md)** — GPT Image and related image-generation APIs/tools.

## Model pages

- [GPT-5.6 Sol](models/gpt-5-6-sol.md)
- [GPT-5.6 Terra](models/gpt-5-6-terra.md)
- [GPT-5.6 Luna](models/gpt-5-6-luna.md)
- [GPT-5.6 Cyber](models/gpt-5-6-cyber.md) — gated Daybreak cybersecurity tier
- [GPT-5.5](models/gpt-5-5.md)
- [GPT-5.5 Pro](models/gpt-5-5-pro.md)
- [GPT-5.4](models/gpt-5-4.md)
- [GPT-5.4 Pro](models/gpt-5-4-pro.md)
- [GPT-5.4 mini](models/gpt-5-4-mini.md)
- [GPT-5.4 nano](models/gpt-5-4-nano.md)
- [GPT-5.3 Instant](models/gpt-5-3-instant.md) — API access retired
- [GPT-5.3-Codex](models/gpt-5-3-codex.md)
- [GPT-5-Codex](models/gpt-5-codex.md) — retired
- [codex-mini-latest](models/codex-mini-latest.md) — retired

## Current model lines

| Line | API ID | Role | Input / output per 1M tokens |
|---|---|---|---|
| GPT-5.6 Sol | `gpt-5.6-sol` (`gpt-5.6` alias) | Flagship tier for complex reasoning and coding | $5 / $30 |
| GPT-5.6 Terra | `gpt-5.6-terra` | Balanced capability-and-cost tier | $2 / $12 |
| GPT-5.6 Luna | `gpt-5.6-luna` | Cost-sensitive, high-volume tier | $0.20 / $1.20 |
| GPT-5.5 | `gpt-5.5` | Previous frontier tier; active for pinned workloads | $5 / $30 |
| GPT-5.5 Pro | `gpt-5.5-pro` | Previous higher-compute tier; active for pinned workloads | $30 / $180 |
| GPT-5.4 family | `gpt-5.4*` | Older main, Pro, mini, and nano tiers | See each model page |
| GPT-5.3-Codex | `gpt-5.3-codex` | Coding-specialized model; Responses API only | $1.75 / $14 |
| `chat-latest` | `chat-latest` | Pointer to the Instant model currently used in ChatGPT | $5 / $30 |

The three GPT-5.6 API models support text and image input, text output, a 1.05M-token context window, 922K maximum input tokens, 128K-token output, and reasoning efforts from `none` through `max`. Their per-model pages list the same broad Responses API tool set and a February 16, 2026 knowledge cutoff. OpenAI's current model pages are authoritative when launch-post prices or capabilities differ. [Models page](https://developers.openai.com/api/docs/models).

## Specialized models

OpenAI keeps a separate specialized catalog for cybersecurity, image, realtime, speech, and transcription work. These lines are documented here as rows rather than pages, except GPT-5.6 Cyber. Every row below is taken from the [models page](https://developers.openai.com/api/docs/models) and the linked per-model page.

### Cybersecurity (Daybreak)

Added August 7, 2026. All three require separate approval and provisioning through the Daybreak program, and all three are Responses-only. [Changelog](https://developers.openai.com/api/docs/changelog).

| Model | API ID | Role | Price per 1M tokens |
|---|---|---|---|
| [GPT-5.6 Cyber](models/gpt-5-6-cyber.md) | `gpt-5.6-cyber` | Purpose-trained model for authorized vulnerability research and security testing | $12.50 / $75 |
| Daybreak Red | `daybreak-red-latest` | Alias; default snapshot `gpt-5.6-cyber` | See [model page](https://developers.openai.com/api/docs/models/daybreak-red-latest) |
| Daybreak Blue | `daybreak-blue-latest` | Alias for frontier general-purpose models with defensive-cyber safeguards; default snapshot `gpt-5.6-sol` | See [model page](https://developers.openai.com/api/docs/models/daybreak-blue-latest) |

### Realtime and speech

| Model | API ID | Endpoint | Price |
|---|---|---|---|
| [GPT-Realtime-2.1](https://developers.openai.com/api/docs/models/gpt-realtime-2.1) | `gpt-realtime-2.1` | `v1/realtime` | Text $4 / $24; audio $32 / $64 per 1M tokens |
| [GPT-Realtime-2.1 mini](https://developers.openai.com/api/docs/models/gpt-realtime-2.1-mini) | `gpt-realtime-2.1-mini` | `v1/realtime` | Text $0.60 / $2.40; audio $10 / $20 per 1M tokens |
| [GPT-Realtime-2](https://developers.openai.com/api/docs/models/gpt-realtime-2) | `gpt-realtime-2` | `v1/realtime` | Text $4 / $24; audio $32 / $64 per 1M tokens |
| [GPT-Realtime-Translate](https://developers.openai.com/api/docs/models/gpt-realtime-translate) | `gpt-realtime-translate` | `v1/realtime/translations` | $0.034 per minute of audio |
| [GPT-Realtime-1.5](https://developers.openai.com/api/docs/models/gpt-realtime-1.5) | `gpt-realtime-1.5` | `v1/realtime` | Text $4 / $16; audio $32 / $64 per 1M tokens |
| [GPT-Realtime mini](https://developers.openai.com/api/docs/models/gpt-realtime-mini) | `gpt-realtime-mini` | `v1/realtime` | Deprecated; shutdown January 20, 2027 |
| [GPT-4o mini TTS](https://developers.openai.com/api/docs/models/gpt-4o-mini-tts) | `gpt-4o-mini-tts` | `v1/audio/speech` | $0.60 text input / $12 audio output per 1M tokens |

The `gpt-realtime-2.1` line carries a 128K context window and 32K maximum output; `gpt-realtime-1.5` carries 32K context and 4,096 maximum output. `gpt-realtime-translate` is audio-in, audio-and-text-out with a 16K context, and is billed by audio duration rather than tokens.

### Transcription

| Model | API ID | Endpoint | Price |
|---|---|---|---|
| [GPT Transcribe](https://developers.openai.com/api/docs/models/gpt-transcribe) | `gpt-transcribe` | `v1/audio/transcriptions`, `v1/realtime/transcription_sessions` | $0.0045 per minute of audio |
| [GPT Live Transcribe](https://developers.openai.com/api/docs/models/gpt-live-transcribe) | `gpt-live-transcribe` | `v1/realtime/transcription_sessions` | $0.017 per minute of audio |
| [GPT-Realtime-Whisper](https://developers.openai.com/api/docs/models/gpt-realtime-whisper) | `gpt-realtime-whisper` | `v1/realtime/transcription_sessions` | $0.017 per minute of audio |
| [GPT-4o Transcribe](https://developers.openai.com/api/docs/models/gpt-4o-transcribe) | `gpt-4o-transcribe` | `v1/audio/transcriptions`, `v1/realtime` | $2.50 / $10 per 1M tokens |
| [GPT-4o mini Transcribe](https://developers.openai.com/api/docs/models/gpt-4o-mini-transcribe) | `gpt-4o-mini-transcribe` | `v1/audio/transcriptions`, `v1/realtime` | See model page |

GPT Transcribe and GPT Live Transcribe shipped July 28, 2026. Both accept free-form transcription context, keyword hints, and multiple expected input languages. [Changelog](https://developers.openai.com/api/docs/changelog).

### Image

| Model | API ID | Endpoint | Notes |
|---|---|---|---|
| [GPT Image 2](https://developers.openai.com/api/docs/models/gpt-image-2) | `gpt-image-2` | `v1/images/generations`, `v1/images/edits`, `v1/batch` | Text and image input, image output; supports inpainting |

## Retired and deprecated IDs

Taken from the [deprecations page](https://developers.openai.com/api/docs/deprecations). Shutdown dates in the past mean the ID no longer serves requests.

| Model / snapshot | Shutdown | Replacement OpenAI names |
|---|---|---|
| `codex-mini-latest` | February 12, 2026 | `gpt-5-codex-mini` |
| `gpt-5-codex`, `gpt-5.1-codex`, `gpt-5.1-codex-max`, `gpt-5.1-codex-mini`, `gpt-5.2-codex`, `gpt-5-chat-latest`, `gpt-5.1-chat-latest`, `computer-use-preview` | July 23, 2026 | `gpt-5.6-sol`; `gpt-5.6-terra` for `gpt-5.1-codex-mini` and the preview tiers |
| `gpt-5.2-chat-latest`, `gpt-5.3-chat-latest` | August 10, 2026 | `gpt-5.6-sol` |
| Assistants API | August 26, 2026 | Responses API and Conversations API |
| `sora-2`, `sora-2-pro`, Videos API | September 24, 2026 | None listed |
| `gpt-image-1`, `o1`, `o1-pro`, `o3-mini`, `o4-mini`, `gpt-4-turbo`, `gpt-4.1-nano`, `gpt-3.5-turbo-0125` and related legacy snapshots | October 23, 2026 | `gpt-image-2`; `gpt-5.6-sol`, `gpt-5.6-terra`, or `gpt-5.6-luna` by tier |
| `gpt-image-1.5`, `gpt-image-1-mini`, `chatgpt-image-latest` | December 1, 2026 | `gpt-image-2` |
| `gpt-5-2025-08-07`, `gpt-5-mini-2025-08-07`, `gpt-5-nano-2025-08-07`, `gpt-5-pro-2025-10-06`, `o3-2025-04-16`, `o3-pro-2025-06-10` | December 11, 2026 | GPT-5.6 family; the Pro snapshots map to `gpt-5.6-sol` with `reasoning.mode: pro` |
| `gpt-realtime`, `gpt-realtime-mini`, `gpt-4o-realtime`, `gpt-4o-mini-realtime`, `gpt-audio`, `gpt-audio-mini`, `gpt-4o-audio`, `gpt-4o-mini-audio` | January 20, 2027 | `gpt-realtime-2.1`, `gpt-realtime-2.1-mini`, `gpt-audio-1.5` |

## System cards

- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.5 system card](https://openai.com/index/gpt-5-5-system-card/)
- [GPT-5.4 Thinking system card](https://openai.com/index/gpt-5-4-thinking-system-card)
- [GPT-5.3 Instant system card](https://openai.com/index/gpt-5-3-instant-system-card/)
- [GPT-5.3-Codex system card](https://openai.com/index/gpt-5-3-codex-system-card/)
- [Addendum to GPT-5 system card: GPT-5-Codex](https://openai.com/index/gpt-5-system-card-addendum-gpt-5-codex/)

OpenAI publishes family-level system cards rather than a separate card for every API alias. Read the current family card with the per-model catalog page. The GPT-5.6 system card was published July 9, 2026 and covers Sol, Terra, and Luna; it predates the August 7, 2026 Daybreak tiers and does not cover GPT-5.6 Cyber.

## Strengths (cited)

- **Broad hosted tool surface.** GPT-5.6 supports web search, file search, code interpreter, hosted shell, apply patch, computer use, MCP, and related Responses API tools. [GPT-5.6 Sol model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol).
- **Three current cost tiers.** Sol, Terra, and Luna share the core GPT-5.6 context, modality, and tool surface while exposing different prices and rate limits. [Models page](https://developers.openai.com/api/docs/models).
- **Product/API availability.** OpenAI launched GPT-5.6 across ChatGPT, Codex, and the API on July 9, 2026. [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/).
- **Latency is a purchasable dimension.** Fast mode replaced Priority Processing on July 30, 2026, and was extended to prompts above 272K tokens on August 5, 2026. OpenAI announced Ultrafast mode for GPT-5.6 Sol on August 13, 2026 as a limited preview for selected customers. [Changelog](https://developers.openai.com/api/docs/changelog).

## Weaknesses (cited)

- **Catalog breadth.** OpenAI maintains overlapping general, Pro, Codex, image, realtime, transcription, and cybersecurity lines. Confirm the exact alias on the [models page](https://developers.openai.com/api/docs/models).
- **Feature support varies by alias.** GPT-5.5 Pro, for example, omits streaming and several tools supported by base GPT-5.5. Compare their [model pages](https://developers.openai.com/api/docs/models/compare).
- **Long-context pricing changes above a threshold.** GPT-5.6 prompts above 272K input tokens are billed at 2x input and 1.5x output for the whole request. [GPT-5.6 Sol model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol).
- **Retirement pace.** Shutdown waves run from February 2026 through January 2027 and cover the whole pre-5.3 Codex line, the `chat-latest` version snapshots, the Assistants API, and the legacy audio and realtime families. Pin snapshots and read the [deprecations page](https://developers.openai.com/api/docs/deprecations) before committing to an ID.
- **The cyber tier is not self-serve.** GPT-5.6 Cyber, Daybreak Red, and Daybreak Blue require separate approval and provisioning, and are Responses-only. [GPT-5.6 Cyber model page](https://developers.openai.com/api/docs/models/gpt-5.6-cyber).

## Fits

- Multimodal agent workflows that need hosted tools
- Coding agents that combine planning, computer use, and repository edits
- Knowledge-work automation across documents, spreadsheets, and presentations
- Mixed-model systems that route work among Sol, Terra, and Luna by task value
- Speech-to-speech and streaming-transcription products built on the realtime endpoints
- Authorized defensive security work, where the Daybreak tiers gate the higher-risk capability

## Provider-specific quirks

- **Responses API is the primary surface.** OpenAI's [GPT-5.6 guidance](https://developers.openai.com/api/docs/guides/latest-model) directs reasoning, tool-calling, and multi-turn workflows there.
- **`gpt-5.6` routes to Sol.** Use the suffixed Terra and Luna IDs when you want those tiers.
- **GPT-5.6 cache writes are billed.** Cache writes cost 1.25 times uncached input; cache reads receive the discount listed on each [model page](https://developers.openai.com/api/docs/models/gpt-5.6-sol).
- **`chat-latest` is a moving target.** It points to the Instant model currently used in ChatGPT and is re-pointed without a version bump; OpenAI recommends GPT-5.6 Sol for production. [Changelog](https://developers.openai.com/api/docs/changelog).
- **Pro compute is now a request parameter.** OpenAI's deprecation table maps `gpt-5-pro`, `o3-pro`, and `o1-pro` to `gpt-5.6-sol` with `reasoning.mode: pro` rather than to a separate Pro ID. [Deprecations](https://developers.openai.com/api/docs/deprecations).
- **Specialized models are endpoint-locked.** Realtime, translation, and transcription models serve only their own endpoints, and the Daybreak models serve only `v1/responses`.

## Official docs

- [Models](https://developers.openai.com/api/docs/models)
- [Model comparison](https://developers.openai.com/api/docs/models/compare)
- [Deprecations](https://developers.openai.com/api/docs/deprecations)
- [API changelog](https://developers.openai.com/api/docs/changelog)
- [GPT-5.6 model guidance](https://developers.openai.com/api/docs/guides/latest-model)
- [GPT-5.6 launch post](https://openai.com/index/gpt-5-6/)
- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)
- [GPT-5.5 model page](https://developers.openai.com/api/docs/models/gpt-5.5)
- [GPT-5.5 Pro model page](https://developers.openai.com/api/docs/models/gpt-5.5-pro)

## Status

`[provider-doc]`. GPT-5.6 is generally available; GPT-5.5 and the GPT-5.4 family remain available for evaluated or pinned workloads. The GPT-5.6 Cyber tier is gated behind Daybreak approval. `gpt-5-codex` and `codex-mini-latest` are retired; `gpt-5.3-codex` is the current coding-specialized ID.
