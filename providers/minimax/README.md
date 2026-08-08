# MiniMax `[provider-doc]`

*Last reviewed: 2026-08-06. MiniMax's public platform now places M3 above the M2.7 and legacy M2.x text tiers, alongside separate audio, video, image, and music stacks. This catalog is date-stamped, not a ranking; verify availability against the live [API overview](https://platform.minimax.io/docs/api-reference/api-overview).*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| MiniMax M3 | Current top M-series model | 1M context, native text/image/video input, tool use, hosted API and open weights |
| MiniMax M2.7 / M2.7-highspeed | Previous text tier | 204,800-token limit; standard and faster hosted variants |
| MiniMax M2.5 / M2.5-highspeed | Legacy hosted tier | 204,800-token limit; standard and faster variants |
| MiniMax M2.1 / M2.1-highspeed | Legacy coding-focused tier | 204,800-token limit; standard and faster variants |
| MiniMax M2 | Older agent/coding text tier | Positioned for efficient coding and agent workflows |
| MiniMax M1 | Open-weight reasoning model | 1M-context open-source reasoning release |
| MiniMax M2-her | Roleplay / long-turn specialized tier | Distinct long-turn multi-character surface on the platform overview |

MiniMax's public overview mixes hosted product cards and API docs, so treat the overview page as the lineup source and the API pages as the implementation source.

## Model pages

- [MiniMax M3](models/minimax-m3.md)
- [MiniMax M2.7](models/minimax-m2-7.md)
- [MiniMax M2.5](models/minimax-m2-5.md)
- [MiniMax M2.5-highspeed](models/minimax-m2-5-highspeed.md)
- [MiniMax M2.1](models/minimax-m2-1.md)
- [MiniMax M1](models/minimax-m1.md)

## Model docs

- [Platform overview](https://platform.minimax.io/)
- [API overview](https://platform.minimax.io/docs/api-reference/api-overview)
- [Model release notes](https://platform.minimax.io/docs/release-notes/models)
- [MiniMax M3 model page](https://www.minimax.io/models/text/m3)
- [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1)

MiniMax does not currently publish a public system-card hub in the Anthropic/OpenAI pattern. The overview pages, release notes, and individual announcements are the practical primary sources.

## Strengths (cited)

- **Current text lineup is broad.** MiniMax documents M3, M2.7, M2.5, M2.1, and older M2 tiers. [API overview](https://platform.minimax.io/docs/api-reference/api-overview).
- **Coding and agent coverage.** The API docs frame M3 and the M2.x text models around coding, tool calling, and agent workflows. [API overview](https://platform.minimax.io/docs/api-reference/api-overview).
- **Open-weight deployment path exists.** MiniMax publishes M3 weights under the MiniMax Community License and retains the M1 open-weight release. [M3 model card](https://huggingface.co/MiniMaxAI/MiniMax-M3), [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1).
- **Broader multimodal platform coverage.** MiniMax also runs first-party speech, video, image, and music model surfaces, even though this page focuses on text.

## Weaknesses (cited)

- **Long-context pricing steps up.** M3 requests above 512K input tokens cost twice the standard under-512K rate. [Pay-as-you-go pricing](https://platform.minimax.io/docs/guides/pricing-paygo).
- **Open weights use a custom license.** M3's model card names the MiniMax Community License; review it before redistribution or commercial deployment. [M3 model card](https://huggingface.co/MiniMaxAI/MiniMax-M3).
- **The platform has distinct modality APIs.** Text, speech, video, image, and music use separate models and operational surfaces. [API overview](https://platform.minimax.io/docs/api-reference/api-overview).

## Fits

- Coding and agent workflows where MiniMax's text tiers are cost-competitive
- Multilingual development workloads
- Teams interested in both hosted APIs and open-weight deployment
- Builders already considering MiniMax's speech/video stack alongside text models

## Provider-specific quirks

- **Use the API docs for callable model names.** The marketing overview and API pages surface slightly different labels.
- **Highspeed variants matter.** MiniMax documents separate faster variants rather than hiding latency tradeoffs behind one alias.
- **The platform is broader than text.** If you are evaluating MiniMax seriously, speech and video surfaces are part of the provider story.

## Official docs

- [Platform overview](https://platform.minimax.io/)
- [API overview](https://platform.minimax.io/docs/api-reference/api-overview)
- [Model release notes](https://platform.minimax.io/docs/release-notes/models)
- [Pricing overview](https://platform.minimax.io/docs/pricing/overview)
- [MiniMax M3](https://www.minimax.io/models/text/m3)
- [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1)

## Status

`[provider-doc]`. MiniMax M3 is covered as the current hosted and open-weight text/multimodal line; earlier model pages remain for migration and historical context.
