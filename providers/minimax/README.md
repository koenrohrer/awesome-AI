# MiniMax `[provider-doc]`

*Last reviewed: 2026-08-16. MiniMax's public platform places M3 above the M2.7 and legacy M2.x text tiers, and runs separate video, speech, image, and music stacks with their own model IDs. This catalog is date-stamped, not a ranking; verify availability against the live [API overview](https://platform.minimax.io/docs/api-reference/api-overview).*

## Text models

| Model ID | Role | Notable feature |
|---|---|---|
| `MiniMax-M3` | Current top M-series model | 1,000,000-token context, text/image/video input, tool use, hosted API and open weights |
| `MiniMax-M2.7` / `MiniMax-M2.7-highspeed` | Previous text tier | 204,800-token limit; the highspeed card lists about 100 output tokens/second |
| `MiniMax-M2.5` / `MiniMax-M2.5-highspeed` | Legacy hosted tier | 204,800-token limit; standard and faster variants |
| `MiniMax-M2.1` / `MiniMax-M2.1-highspeed` | Legacy coding-focused tier | 204,800-token limit; standard and faster variants |
| `MiniMax-M2` | Older agent/coding text tier | 204,800-token limit; documented for agentic use and reasoning |

All eight IDs above are listed on the [API overview](https://platform.minimax.io/docs/api-reference/api-overview). MiniMax M1 is an open-weight release and is not on the current API overview; the page below is kept for historical context.

## Video models

| Model ID | Status | Evidence |
|---|---|---|
| `MiniMax-H3` | Full page: [MiniMax H3](models/minimax-h3.md) | `[provider-doc]` [API overview](https://platform.minimax.io/docs/api-reference/api-overview), [Video generation guide](https://platform.minimax.io/docs/guides/video-generation) |

`MiniMax-H3` is the only model ID the video generation API accepts as reviewed. The platform overview also shows Hailuo 2.3, Hailuo 2.3Fast, and Hailuo 02 product cards, but the documented video endpoints do not list them as callable model values. [Create Video Generation Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-create).

## Speech models

| Model ID | Status | Evidence |
|---|---|---|
| `speech-2.8-hd` | Docs only; supports sound tags such as `(sighs)` and `(laughs)` | `[provider-doc]` [HTTP T2A API](https://platform.minimax.io/docs/api-reference/speech-t2a-http) |
| `speech-2.8-turbo` | Docs only; low-latency variant, also supports sound tags | `[provider-doc]` [HTTP T2A API](https://platform.minimax.io/docs/api-reference/speech-t2a-http) |
| `speech-2.6-hd` | Docs only; previous quality tier | `[provider-doc]` [API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| `speech-2.6-turbo` | Docs only; card lists 40 languages | `[provider-doc]` [API overview](https://platform.minimax.io/docs/api-reference/api-overview) |
| `speech-02-hd`, `speech-02-turbo` | Docs only; older tier | `[provider-doc]` [HTTP T2A API](https://platform.minimax.io/docs/api-reference/speech-t2a-http) |
| `speech-01-hd`, `speech-01-turbo` | Docs only; accepted by the T2A API but absent from the overview cards | `[provider-doc]` [HTTP T2A API](https://platform.minimax.io/docs/api-reference/speech-t2a-http) |

The speech stack also documents [WebSocket T2A](https://platform.minimax.io/docs/api-reference/speech-t2a-websocket), an [async task API](https://platform.minimax.io/docs/api-reference/speech-t2a-async-create), [voice cloning](https://platform.minimax.io/docs/api-reference/voice-cloning-clone), and [voice design](https://platform.minimax.io/docs/api-reference/voice-design-design). Input text must be under 10,000 characters. [HTTP T2A API](https://platform.minimax.io/docs/api-reference/speech-t2a-http).

## Image models

| Model ID | Status | Evidence |
|---|---|---|
| `image-01` | Docs only; the only model value the image APIs accept | `[provider-doc]` [Text to Image](https://platform.minimax.io/docs/api-reference/image-generation-t2i), [Image to Image](https://platform.minimax.io/docs/api-reference/image-generation-i2i) |

Documented limits: prompts up to 1,500 characters, 1–9 images per request, preset aspect ratios from 21:9 to 9:16, and custom sizes from 512 to 2,048 px divisible by 8. [Text to Image](https://platform.minimax.io/docs/api-reference/image-generation-t2i).

## Music models

| Model ID | Status | Evidence |
|---|---|---|
| `music-3.0` | Docs only; marked recommended in the API reference | `[provider-doc]` [Music Generation API](https://platform.minimax.io/docs/api-reference/music-generation) |
| `music-2.6` | Docs only; previous generation | `[provider-doc]` [Music Generation API](https://platform.minimax.io/docs/api-reference/music-generation) |
| `music-cover` | Docs only; cover mode, takes 6-second to 6-minute reference audio | `[provider-doc]` [Music Generation API](https://platform.minimax.io/docs/api-reference/music-generation) |
| `music-3.0-free`, `music-2.6-free`, `music-cover-free` | Docs only; free-tier model values | `[provider-doc]` [Music Generation API](https://platform.minimax.io/docs/api-reference/music-generation) |

Lyrics run 1–3,500 characters for text-to-music and 10–1,000 characters for cover models. [Music Generation API](https://platform.minimax.io/docs/api-reference/music-generation).

## Model pages

- [MiniMax M3](models/minimax-m3.md)
- [MiniMax M2.7](models/minimax-m2-7.md)
- [MiniMax M2.5](models/minimax-m2-5.md)
- [MiniMax M2.5-highspeed](models/minimax-m2-5-highspeed.md)
- [MiniMax M2.1](models/minimax-m2-1.md)
- [MiniMax M1](models/minimax-m1.md)
- [MiniMax H3](models/minimax-h3.md)

## Model docs

- [Platform overview](https://platform.minimax.io/)
- [API overview](https://platform.minimax.io/docs/api-reference/api-overview)
- [Model release notes](https://platform.minimax.io/docs/release-notes/models)
- [MiniMax M3 model page](https://www.minimax.io/models/text/m3)
- [MiniMax H3 release post](https://www.minimax.io/blog/minimax-h3)
- [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1)

MiniMax does not currently publish a public system-card hub in the Anthropic/OpenAI pattern. The overview pages, release notes, and individual announcements are the practical primary sources.

## Strengths (cited)

- **Current text lineup is broad.** The API overview lists M3, M2.7, M2.5, M2.1, and M2, each with a highspeed variant below M3. [API overview](https://platform.minimax.io/docs/api-reference/api-overview).
- **Coding and agent coverage.** The API docs frame M3 and the M2.x text models around coding, tool calling, and agent workflows. [API overview](https://platform.minimax.io/docs/api-reference/api-overview).
- **Open-weight deployment path exists across modalities.** MiniMax publishes M3 weights under the MiniMax Community License and H3 weights under the MiniMax H3 Community License Agreement, and retains the M1 open-weight release. [M3 model card](https://huggingface.co/MiniMaxAI/MiniMax-M3), [H3 open-source announcement](https://www.minimax.io/news/minimax-h3-open-source), [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1).
- **Video generation is one model with several input modes.** H3 accepts text, first/last-frame, and reference input on a single model ID and emits video with stereo audio. [Video generation guide](https://platform.minimax.io/docs/guides/video-generation).

## Weaknesses (cited)

- **Long-context pricing steps up.** M3 requests above 512K input tokens cost twice the standard under-512K rate. [Pay-as-you-go pricing](https://platform.minimax.io/docs/guides/pricing-paygo).
- **Open weights use custom licenses.** M3 and H3 each ship under a MiniMax-specific community license; review the terms before redistribution or commercial deployment. [M3 model card](https://huggingface.co/MiniMaxAI/MiniMax-M3), [H3 model card](https://huggingface.co/MiniMaxAI/MiniMax-H3).
- **The H3 weight release is partial.** The H3-Context-IR prompt stage and the H3-Regenerate-2K upscaler stay API-only, so self-hosting does not reproduce the hosted pipeline. [Open-source announcement](https://www.minimax.io/news/minimax-h3-open-source).
- **The platform has distinct modality APIs.** Text, video, speech, image, and music use separate models, separate endpoints, and in the video case an asynchronous task model rather than a request/response call. [API overview](https://platform.minimax.io/docs/api-reference/api-overview).
- **Product cards and callable IDs diverge.** The platform overview lists Hailuo video cards that the documented video endpoints do not accept as model values. [Create Video Generation Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-create).

## Fits

- Coding and agent workflows where MiniMax's text tiers are cost-competitive
- Multilingual development workloads
- Teams interested in both hosted APIs and open-weight deployment
- Video, speech, or music generation work that can accept per-modality APIs and asynchronous task polling

## Provider-specific quirks

- **Use the API docs for callable model names.** The marketing overview and API pages surface different labels, and the video stack is the clearest case.
- **Highspeed variants matter.** MiniMax documents separate faster variants rather than hiding latency tradeoffs behind one alias.
- **Video billing is per output second, not per token.** H3 charges by second at each resolution, plus a per-image charge past the first five input images. [Pay-as-you-go pricing](https://platform.minimax.io/docs/guides/pricing-paygo).

## Official docs

- [Platform overview](https://platform.minimax.io/)
- [API overview](https://platform.minimax.io/docs/api-reference/api-overview)
- [Model release notes](https://platform.minimax.io/docs/release-notes/models)
- [Pricing overview](https://platform.minimax.io/docs/pricing/overview)
- [Pay-as-you-go pricing](https://platform.minimax.io/docs/guides/pricing-paygo)
- [Video generation guide](https://platform.minimax.io/docs/guides/video-generation)
- [MiniMax M3](https://www.minimax.io/models/text/m3)
- [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1)

## Status

`[provider-doc]`. MiniMax M3 is covered as the current hosted and open-weight text line, and MiniMax H3 as the current video line; earlier text model pages remain for migration and historical context. Speech, image, and music models are covered as cited rows against their API reference pages rather than dedicated pages.
