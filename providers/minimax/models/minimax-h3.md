# MiniMax H3 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| API model ID | `MiniMax-H3` |
| Lifecycle | Listed as the video model on the MiniMax API overview |
| Deployment | Hosted API and open weights |
| Modalities | Text, image, video, and audio input; video with stereo audio output |
| Resolutions | `768P`, `2K` |
| Duration | 4–15 seconds, integer values |
| Aspect ratios | `adaptive` (default), `21:9`, `16:9`, `4:3`, `1:1`, `3:4`, `9:16` |
| Weight license | MiniMax H3 Community License Agreement |

## What it is

MiniMax H3 is MiniMax's video generation model. The API overview describes it as a "Multimodal video generation model supporting text / image / first-and-last-frame / reference input". The video generation guide documents three input modes on one model ID: text-to-video, first/last-frame image-to-video, and reference generation from images, videos, or audio. [API overview](https://platform.minimax.io/docs/api-reference/api-overview), [Video generation guide](https://platform.minimax.io/docs/guides/video-generation).

The release post says H3 generates audio jointly with video rather than as a separate pass, with "no separation between voice, sound effects, and music", and outputs "native stereo sound, up to 15 seconds at 2K resolution". [Release post](https://www.minimax.io/blog/minimax-h3).

MiniMax announced H3 on July 31, 2026 and published weights on August 3, 2026. [Model release notes](https://platform.minimax.io/docs/release-notes/models), [Open-source announcement](https://www.minimax.io/news/minimax-h3-open-source).

## API surface

H3 uses a task-based video API rather than a chat completion. Video generation is asynchronous: create a task, then poll it.

| Endpoint | Purpose |
|---|---|
| [Create Video Generation Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-create) | Submit a text, first/last-frame, or reference generation job |
| [Create H3-Context-IR Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-h3-context-ir) | Return an enriched prompt from multimodal context; generates no video |
| [Create Video Regeneration Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-regeneration) | Regenerate from an existing result |
| [Query Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-query) | Poll task status and fetch output |
| [List Tasks](https://platform.minimax.io/docs/api-reference/video-generation-v2-list) | Enumerate submitted tasks |
| [Cancel or Delete Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-delete) | Cancel or remove a task |

Documented request limits, as reviewed: text prompt items up to 7,000 characters; images up to 30 MB each, 256–5760 px per side, aspect ratio 0.4–2.5; up to 3 reference video clips at 50 MB and 2–15 seconds each; up to 3 reference audio clips at 15 MB and 2–15 seconds each; total request body up to 64 MB. [Create Video Generation Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-create).

## Open weights

MiniMax publishes two task-specific checkpoints, "MiniMax-H3 Base FL2VA" for text-to-video and first/last-frame modes and "MiniMax-H3 Base Ref2VA" for reference-to-video with multimodal inputs, under the MiniMax H3 Community License Agreement. The H3-Context-IR prompt-enrichment stage and the H3-Regenerate-2K upscaling module are not part of the weight release; both are reachable only through the API. [Open-source announcement](https://www.minimax.io/news/minimax-h3-open-source), [Official model card](https://huggingface.co/MiniMaxAI/MiniMax-H3).

Review the license before redistribution or commercial deployment. Self-hosting the weights does not reproduce the hosted pipeline, because two documented stages are withheld.

## Pricing

As reviewed, MiniMax bills H3 by output second:

| Item | Rate |
|---|---:|
| Output, 2K | $0.13 / second |
| Output, 768P | $0.08 / second |
| Input images | First 5 free, then $0.04 per image |

Check the live page before budgeting. [Pay-as-you-go pricing](https://platform.minimax.io/docs/guides/pricing-paygo).

## Links

- [API overview](https://platform.minimax.io/docs/api-reference/api-overview)
- [Video generation guide](https://platform.minimax.io/docs/guides/video-generation)
- [Create Video Generation Task](https://platform.minimax.io/docs/api-reference/video-generation-v2-create)
- [Release post](https://www.minimax.io/blog/minimax-h3)
- [Open-source announcement](https://www.minimax.io/news/minimax-h3-open-source)
- [Official model repository](https://github.com/MiniMax-H3/MiniMax-H3)
- [Official model card](https://huggingface.co/MiniMaxAI/MiniMax-H3)
- [Pricing](https://platform.minimax.io/docs/guides/pricing-paygo)

## Status

`[provider-doc]`. The release post says a full H3 technical report is not published yet, so architecture details here stay limited to what the model card and announcements state.
