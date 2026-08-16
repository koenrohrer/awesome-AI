# DeepSeek `[provider-doc]`

*Last reviewed: 2026-08-16. DeepSeek-V4-Pro reached GA on 2026-08-13 as DeepSeek-V4-Pro-0813. Peak/off-peak API pricing took effect at 16:00 UTC on 2026-08-16. DeepSeek-V4-Flash-0731 remains the hosted V4-Flash version; the `deepseek-chat` and `deepseek-reasoner` aliases passed their retirement cutoff and are no longer listed on the pricing page.*

## Current model lines

| Surface | Backing model | Role | Notable feature |
|---|---|---|---|
| `deepseek-v4-pro` | DeepSeek-V4-Pro-0813 | GA hosted + open-weight model | 1.6T total / 49B active params; 1M context |
| `deepseek-v4-flash` | DeepSeek-V4-Flash-0731 | Hosted API, announced as public beta | 284B total / 13B active architecture; 1M context |
| `deepseek-chat` | Final mapping was V4-Flash non-thinking | Retired historical alias | Inaccessible after July 24, 2026 at 15:59 UTC |
| `deepseek-reasoner` | Final mapping was V4-Flash thinking | Retired historical alias | Inaccessible after July 24, 2026 at 15:59 UTC |
| DeepSeek-V3.2 | Prior open-weight top tier | General + agent use | Superseded by V4 |
| DeepSeek-R1 | Open-weight reasoning family | Reasoning | First major open-weight reasoning breakout |

DeepSeek's API docs list `deepseek-v4-pro` and `deepseek-v4-flash` as the current model IDs. The older `deepseek-chat` and `deepseek-reasoner` names are historical only; migrate integrations to `deepseek-v4-flash` and select thinking mode explicitly.

## Model pages

- [DeepSeek-V4-Pro](models/deepseek-v4-pro.md)
- [DeepSeek-V4-Flash](models/deepseek-v4-flash.md)
- [deepseek-chat](models/deepseek-chat.md)
- [deepseek-reasoner](models/deepseek-reasoner.md)
- [DeepSeek-V3.2](models/deepseek-v3-2.md)
- [DeepSeek-R1](models/deepseek-r1.md)

## Model docs

- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Change log](https://api-docs.deepseek.com/updates/)
- [DeepSeek-V4-Pro GA release](https://api-docs.deepseek.com/news/news260813)
- [DeepSeek V4 Preview release](https://api-docs.deepseek.com/news/news260424)
- [Thinking mode](https://api-docs.deepseek.com/guides/thinking_mode)
- [Codex integration](https://api-docs.deepseek.com/quick_start/agent_integrations/codex)
- [DeepSeek V4 open weights](https://huggingface.co/collections/deepseek-ai/deepseek-v4)
- [DeepSeek V4 technical report](https://arxiv.org/abs/2606.19348)
- [DeepSeek-V3.2 release](https://api-docs.deepseek.com/news/news251201)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)

DeepSeek does not currently publish public “system cards” in the same style as Anthropic/OpenAI. The release notes, pricing docs, papers, and Hugging Face model cards are the practical equivalents.

## Strengths (cited)

- **Large open-weight V4 release.** V4-Pro is documented at 1.6T total / 49B active parameters, while V4-Flash is documented at 284B total / 13B active parameters. [DeepSeek V4 Preview release](https://api-docs.deepseek.com/news/news260424).
- **GA weights track the hosted models.** MIT-licensed weights for both current hosted versions are published: [DeepSeek-V4-Pro-0813](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813) and [DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731).
- **1M-token context on current hosted IDs.** The pricing page lists 1M context length and a 384K maximum output for both `deepseek-v4-pro` and `deepseek-v4-flash`. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Three thinking effort levels.** Since the 2026-08-13 update, thinking mode on both V4 IDs accepts `low`, `high`, and `max`, with `high` as the default. [Change log](https://api-docs.deepseek.com/updates/), [thinking mode](https://api-docs.deepseek.com/guides/thinking_mode).
- **Responses API on both V4 IDs.** The pricing page marks the Responses API supported for `deepseek-v4-pro` and `deepseek-v4-flash`. DeepSeek describes the format as natively supported and specifically adapted for Codex. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/), [Codex integration](https://api-docs.deepseek.com/quick_start/agent_integrations/codex).
- **Multiple API surfaces.** Both V4 IDs support JSON output, tool calls, chat prefix completion (beta), non-thinking FIM completion (beta), and OpenAI- and Anthropic-format base URLs. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Low published prices.** As listed on 2026-08-16, `deepseek-v4-flash` off-peak output is $0.66 per 1M tokens and `deepseek-v4-pro` off-peak output is $1.98 per 1M tokens. Recheck before relying on these; DeepSeek states prices may vary. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

## Weaknesses (cited)

- **Prices now depend on wall-clock time.** Peak rates are twice off-peak, and peak hours are 01:00-04:00 and 06:00-10:00 UTC. Cost estimates that ignore scheduling will be wrong by up to 2x. Verified on the pricing page on 2026-08-16; recheck the hours and rates before budgeting. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/), [change log](https://api-docs.deepseek.com/updates/).
- **Model IDs are mutable.** `deepseek-v4-pro` moved from the April preview to DeepSeek-V4-Pro-0813 at GA with no ID change, so pinned integrations changed behavior and cost without a code change. [Change log](https://api-docs.deepseek.com/updates/).
- **Legacy aliases are retired.** DeepSeek documented both aliases as inaccessible after July 24, 2026 at 15:59 UTC, and neither appears on the current pricing page. [V4 Preview release](https://api-docs.deepseek.com/news/news260424), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).
- **Benchmark claims are vendor self-reported.** The GA agent scores come from DeepSeek's own change log and model card, evaluated with DeepSeek Harness at `max` effort, and two of the named sets are internal. No third-party reproduction is published. [Change log](https://api-docs.deepseek.com/updates/), [DeepSeek-V4-Pro-0813 model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813).
- **Documentation depth still lags the Western incumbents.** Advanced agent/framework details remain thinner.
- **Policy and deployment constraints matter.** Some teams will prefer self-hosting or third-party hosting for governance reasons rather than calling DeepSeek directly.

## Fits

- Cost-sensitive hosted inference, especially batch work that can be scheduled into off-peak hours
- Open-weight reasoning and research workloads
- Long-context agent workloads that can use the 1M-token V4 context window
- Codex-style agent clients that speak the Responses API
- Benchmarks and experiments where open release artifacts matter

## Provider-specific quirks

- **Use the V4 IDs for all active integrations.** `deepseek-chat` and `deepseek-reasoner` are retired, not fallback compatibility names.
- **The model ID does not encode the version.** Read the pricing page's model-version row (`DeepSeek-V4-Pro-0813`, `DeepSeek-V4-Flash-0731`) to know what a request actually hits.
- **Thinking is mode-controlled, and effort is separate.** `thinking` toggles it; `reasoning_effort` sets `low`/`high`/`max`. Requested `medium` and `xhigh` both map to `high`. Thinking mode ignores `temperature`, `top_p`, `presence_penalty`, and `frequency_penalty` without erroring. [Thinking mode](https://api-docs.deepseek.com/guides/thinking_mode).
- **Weights are published without a change-log announcement.** The 2026-07-31 V4-Flash change-log entry does not mention weights, but `DeepSeek-V4-Flash-0731` was published on Hugging Face the same day. Watch the Hugging Face organization as well as the change log.
- **Release notes matter.** DeepSeek changes what the IDs point to and how they are priced; monitor the [change log](https://api-docs.deepseek.com/updates/).

## Official docs

- [Platform](https://platform.deepseek.com/)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Change log](https://api-docs.deepseek.com/updates/)
- [List models API](https://api-docs.deepseek.com/api/list-models)
- [DeepSeek on Hugging Face](https://huggingface.co/deepseek-ai)
- [DeepSeek on GitHub](https://github.com/deepseek-ai)

## Status

`[provider-doc]`. Reviewed 2026-08-16 against the change log and pricing page. Reflects the 2026-08-13 DeepSeek-V4-Pro GA release, three thinking effort levels on both V4 IDs, native Responses API support on both V4 IDs, the peak/off-peak pricing effective 16:00 UTC 2026-08-16, the unchanged V4-Flash-0731 hosted version, and completed retirement of the legacy aliases. Pricing is date-sensitive and must be rechecked against the pricing page.
