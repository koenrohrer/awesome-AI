# xAI `[provider-doc]`

*Last reviewed: 2026-04-22. xAI's primary model family is Grok. Verify against [x.ai](https://x.ai/) and the [xAI API docs](https://docs.x.ai/) before building a cost model.*

## Current model lines

| Line | Role | Notable feature |
|---|---|---|
| Grok series | General frontier | Closed API; consumer access via X / grok.com |
| Grok Code | Code | Code-specialized variant |
| Grok Vision | Vision-language | Multimodal input |

Available via [xAI's API](https://docs.x.ai/) and through consumer surfaces ([grok.com](https://grok.com/), X app, Tesla cars). Historically xAI has published select earlier-version weights after successor releases — check the [xAI blog](https://x.ai/news) for the current open-weight status of older Grok versions.

## Strengths (cited)

- **OpenAI-API-compatible endpoint.** xAI exposes a `chat/completions` endpoint compatible with OpenAI client libraries — existing OpenAI code generally works with a base-URL and key change. See the [API docs](https://docs.x.ai/).
- **Real-time web access.** Grok is positioned on integrated live-data access (X platform + web) as a differentiator vs other frontier providers. The specific API-level exposure of this varies — check current docs.
- **Large context windows** on recent releases — verify the exact limit per model on the docs page.

## Weaknesses (cited)

- **Smaller third-party ecosystem** than OpenAI/Anthropic/Google — fewer integrations in mainstream agent frameworks by default, though OpenAI-compatibility smooths most of this.
- **Documentation depth** is thinner than the incumbents for advanced features (prompt caching, complex tool-use orchestration). Community writeups fill some gaps.
- **Alignment / behavior profile** differs from other frontier models — verify on your specific task rather than assuming drop-in parity with an Anthropic/OpenAI baseline.

## Best-fit tasks

- Workflows requiring real-time information access where Grok's live-data integration beats stale training-data cutoffs
- Applications already targeting the X platform or Tesla fleet where Grok is the native integration
- OpenAI-client-based codebases that want to evaluate an additional provider with minimal integration work

## Provider-specific quirks

- **OpenAI-compatible API** is the primary surface — use existing OpenAI SDKs with `base_url="https://api.x.ai/v1"` (or as specified in the current docs).
- **Consumer surfaces differ from API surfaces.** Capabilities available in the Grok web/app UI (realtime data, image generation, specific tools) may not all be exposed in the API — always check API docs.

## Official docs and resources

- [x.ai](https://x.ai/)
- [xAI API docs](https://docs.x.ai/)
- [xAI news / blog](https://x.ai/news)

## Status

`[provider-doc]`. Model lineup, pricing, and open-weight policy rotate; confirm on the docs site before shipping.
