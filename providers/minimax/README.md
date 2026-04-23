# MiniMax `[provider-doc]`

*Last reviewed: 2026-04-23. MiniMax's public platform now spans a newer M2.7 flagship, multiple M2.x text variants, and separate audio/video/image stacks. Verify current text-model availability against the live [platform overview](https://platform.minimaxi.com/) and [API overview](https://platform.minimaxi.com/docs/api-reference/api-overview).*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| MiniMax M2.7 | Current flagship text model | Newest text release; positioned around self-iteration and stronger general capability |
| MiniMax M2.5 / M2.5-highspeed | Main production text tier | 204,800-token limit, strong coding/tool-use/productivity story |
| MiniMax M2.1 / M2.1-highspeed | Coding-focused text tier | Strong multilingual programming emphasis |
| MiniMax M2 | Older agent/coding text tier | Positioned for efficient coding and agent workflows |
| MiniMax M1 | Open-weight reasoning model | 1M-context open-source reasoning release |
| MiniMax M2-her | Roleplay / long-turn specialized tier | Distinct long-turn multi-character surface on the platform overview |

MiniMax's public overview mixes hosted product cards and API docs, so treat the overview page as the lineup source and the API pages as the implementation source.

## Model pages

- [MiniMax M2.7](models/minimax-m2-7.md)
- [MiniMax M2.5](models/minimax-m2-5.md)
- [MiniMax M2.5-highspeed](models/minimax-m2-5-highspeed.md)
- [MiniMax M2.1](models/minimax-m2-1.md)
- [MiniMax M1](models/minimax-m1.md)

## Model docs

- [Platform overview](https://platform.minimaxi.com/)
- [API overview](https://platform.minimaxi.com/docs/api-reference/api-overview)
- [Model release notes](https://platform.minimaxi.com/docs/release-notes/models)
- [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1)

MiniMax does not currently publish a public system-card hub in the Anthropic/OpenAI pattern. The overview pages, release notes, and individual announcements are the practical primary sources.

## Strengths (cited)

- **Current text lineup is broad.** MiniMax now has M2.7, M2.5, M2.1, and older M2 tiers in public docs, rather than a single flagship. [Platform overview](https://platform.minimaxi.com/), [API overview](https://platform.minimaxi.com/docs/api-reference/api-overview).
- **Strong coding and agent positioning.** The API docs explicitly frame the text models around coding, tool calling, and agent workflows. [API overview](https://platform.minimaxi.com/docs/api-reference/api-overview).
- **Open-weight reasoning side path exists.** MiniMax-M1 gives the provider an open-weight research/deployment story in addition to hosted APIs. [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1).
- **Broader multimodal platform coverage.** MiniMax also runs first-party speech, video, image, and music model surfaces, even though this page focuses on text.

## Weaknesses (cited)

- **English-language documentation is thinner.** The clearest current docs are still often in Chinese, especially for release notes and pricing details.
- **Product and API naming do not map cleanly.** The flagship cards on the overview page and the API-supported names are related but not identical.
- **Western framework mindshare is still limited.** Integration usually happens through compatibility layers rather than first-class framework defaults.

## Best-fit tasks

- Coding and agent workflows where MiniMax's text tiers are cost-competitive
- Multilingual development workloads
- Teams interested in both hosted APIs and an open-weight reasoning release
- Builders already considering MiniMax's speech/video stack alongside text models

## Provider-specific quirks

- **Use the API docs for callable model names.** The marketing overview and API pages surface slightly different labels.
- **Highspeed variants matter.** MiniMax documents separate faster variants rather than hiding latency tradeoffs behind one alias.
- **The platform is broader than text.** If you are evaluating MiniMax seriously, speech and video surfaces are part of the provider story.

## Official docs

- [Platform overview](https://platform.minimaxi.com/)
- [API overview](https://platform.minimaxi.com/docs/api-reference/api-overview)
- [Model release notes](https://platform.minimaxi.com/docs/release-notes/models)
- [Pricing overview](https://platform.minimaxi.com/docs/pricing/overview)
- [MiniMax M1 announcement](https://www.minimax.io/news/minimaxm1)

## Status

`[provider-doc]`. Added in this pass to cover a provider that was missing from the original index but is now relevant to the current model-provider landscape.
