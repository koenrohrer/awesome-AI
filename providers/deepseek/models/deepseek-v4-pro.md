# DeepSeek-V4-Pro `[provider-doc]`

*Last reviewed: 2026-08-16. DeepSeek-V4-Pro reached GA on 2026-08-13, replacing the April preview version behind the same model ID.*

## At a glance

- Provider: DeepSeek
- Model ID: `deepseek-v4-pro`
- Hosted model version: DeepSeek-V4-Pro-0813
- Release status: GA on APP, Web, and API since 2026-08-13
- Parameters: 1.6T total / 49B active
- Context window: 1M tokens
- Max output: 384K tokens
- Open weights: [DeepSeek-V4-Pro-0813](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813), MIT license
- Official docs: [GA release note](https://api-docs.deepseek.com/news/news260813), [change log](https://api-docs.deepseek.com/updates/), [models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)

## What it is

DeepSeek-V4-Pro is the larger DeepSeek V4 model, positioned by DeepSeek for long-context, reasoning, and agentic coding workloads. The pricing page lists the model version behind `deepseek-v4-pro` as DeepSeek-V4-Pro-0813 and lists 1M context with a 384K maximum output. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

The 1.6T total / 49B active parameter figures come from the April preview release note. [V4 Preview release](https://api-docs.deepseek.com/news/news260424).

## GA release (2026-08-13)

The change log states that "the GA release of DeepSeek-V4-Pro has been rolled out on the APP, Web, and API" and that "the API calling method remains unchanged — simply set the model name to `deepseek-v4-pro` to use the latest version." On app and web the GA model is reached through "Expert Mode". [Change log](https://api-docs.deepseek.com/updates/), [GA release note](https://api-docs.deepseek.com/news/news260813).

The open-weight card describes DeepSeek-V4-Pro-0813 as built on the DeepSeek-V4-Pro (Preview) structure with a DSpark speculative decoding module attached, and documents vLLM and SGLang flags for that module. [Model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813).

## Thinking effort levels

Thinking mode on `deepseek-v4-pro` now takes three effort levels: `low`, `high`, and `max`. DeepSeek suggests low for simple tasks, high for daily agent tasks, and max for more complex scenarios. [Change log](https://api-docs.deepseek.com/updates/), [thinking mode](https://api-docs.deepseek.com/guides/thinking_mode).

| Surface | Toggle parameter | Effort parameter |
|---|---|---|
| OpenAI format | `{"thinking": {"type": "enabled/disabled"}}` | `{"reasoning_effort": "low/high/max"}` |
| Anthropic format | `{"reasoning": {"effort": "none/low/high/max"}}` (`none` disables thinking) | `{"output_config": {"effort": "low/high/max"}}` |

Documented behavior, from the [thinking mode guide](https://api-docs.deepseek.com/guides/thinking_mode):

- Thinking mode is enabled by default, with default effort `high`.
- Requested `medium` and `xhigh` both map to actual effort `high`; `low` and `max` map directly. The mapping is identical for `deepseek-v4-flash` and `deepseek-v4-pro`.
- Thinking mode ignores `temperature`, `top_p`, `presence_penalty`, and `frequency_penalty`. Setting them raises no error and has no effect.
- Chain-of-thought is returned in `reasoning_content` alongside `content`. It may be dropped from later turns unless the turn contained a tool call, in which case it must be passed back.

## Responses API

The pricing page marks the Responses API as supported for `deepseek-v4-pro`. DeepSeek describes the API as natively supporting the OpenAI Responses API format and as "specifically adapted for Codex", with a one-click configuration script for `~/.codex/models.json` and `~/.codex/config.toml` against `https://api.deepseek.com/`. [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/), [change log](https://api-docs.deepseek.com/updates/), [Codex integration](https://api-docs.deepseek.com/quick_start/agent_integrations/codex).

The change log lists native Responses API support as new in the 2026-08-13 release. The preceding 2026-07-31 entry claimed that support for V4-Flash only. [Change log](https://api-docs.deepseek.com/updates/).

## Pricing

Peak/off-peak pricing took effect at 16:00 UTC on 2026-08-16, per the change log and the GA release note. This page was reviewed at 17:04 UTC on 2026-08-16, after that cutover, and the figures below are what the pricing page listed then.

Prices are USD per 1M tokens, `deepseek-v4-pro`, as listed on 2026-08-16. Recheck before relying on them; DeepSeek states that "product prices may vary and DeepSeek reserves the right to adjust them". [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/).

| Token class | Off-peak | Peak |
|---|---|---|
| Input, cache hit | $0.022 | $0.044 |
| Input, cache miss | $0.66 | $1.32 |
| Output | $1.98 | $3.96 |

- Off-peak rates are half of the peak rates.
- Peak hours are 01:00-04:00 and 06:00-10:00 UTC. All other hours are off-peak.
- Concurrency limit: 500 concurrent requests for `deepseek-v4-pro`.

Billing windows are wall-clock, so a batch job's cost depends on when it runs. Treat both numbers as review-date snapshots.

## Feature support

From the [pricing page](https://api-docs.deepseek.com/quick_start/pricing/), for `deepseek-v4-pro`: JSON output, tool calls, Responses API, Anthropic API, and chat prefix completion (beta) are supported. FIM completion (beta) is supported in non-thinking mode only. Base URLs are `https://api.deepseek.com` for the OpenAI format and `https://api.deepseek.com/anthropic` for the Anthropic format.

## Benchmarks

Vendor self-reported scores, from the DeepSeek-V4-Pro-0813 model card dated 2026-08-13. The same figures appear in the change log entry. Methodology per the card: code-agent tasks among the public benchmarks were evaluated with the minimal mode of DeepSeek Harness as the agent framework, at `max` reasoning effort with `temperature = 1.0, top_p = 0.95`. DeepSeek has not published a reproduction harness for these runs, and the two DSBench rows are internal test sets.

| Benchmark | V4-Pro-0813 | V4-Pro (Preview) |
|---|---|---|
| HLE (wo / w tools) | 42.7 / 60.0 | 37.7 / 48.2 |
| Terminal Bench 2.1 | 87.9 | 72.1 |
| NL2Repo | 61.5 | 38.5 |
| Cybergym | 83.3 | 52.7 |
| DeepSWE | 62.7 | 12.8 |
| Toolathlon-Verified | 74.1 | 55.9 |
| Agents' Last Exam | 25.7 | 16.5 |
| AutomationBench (Public) | 31.8 | 12.8 |
| DSBench-FullStack (internal) | 71.1 | 41.8 |
| DSBench-Hard (internal) | 67.2 | 31.1 |

[Model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813), [change log](https://api-docs.deepseek.com/updates/).

## Notes

- The model ID did not change at GA. Integrations pinned to `deepseek-v4-pro` moved to the 0813 version without a code change, so behavior and cost changed underneath callers who did not follow the change log.
- The GA release note does not mention open weights. The `deepseek-ai/DeepSeek-V4-Pro-0813` repository was published on Hugging Face on 2026-08-13 under the MIT license.
- The 0813 release ships no Jinja chat template. The card provides an `encoding` folder of Python scripts for encoding OpenAI-format messages and parsing model output.
- For local deployment the card recommends `temperature = 1.0`, `top_p = 0.95` for agentic scenarios and `top_p = 1.0` otherwise, and a maximum output length of 384K tokens at `high` and `max` reasoning effort.

## Public system card availability

DeepSeek does not currently publish a public system-card page for V4-Pro. The release notes, pricing page, technical report, and Hugging Face model card are the practical equivalents.

## Links

- [GA release note](https://api-docs.deepseek.com/news/news260813)
- [Change log](https://api-docs.deepseek.com/updates/)
- [V4 Preview release note](https://api-docs.deepseek.com/news/news260424)
- [Models and pricing](https://api-docs.deepseek.com/quick_start/pricing/)
- [Thinking mode](https://api-docs.deepseek.com/guides/thinking_mode)
- [Codex integration](https://api-docs.deepseek.com/quick_start/agent_integrations/codex)
- [DeepSeek-V4-Pro-0813 model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813)
- [DeepSeek-V4-Pro preview model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro)
- [Open weights collection](https://huggingface.co/collections/deepseek-ai/deepseek-v4)
- [Technical report](https://arxiv.org/abs/2606.19348)

## Status

`[provider-doc]`. Reflects the 2026-08-13 GA release, the three thinking effort levels, native Responses API support, and the peak/off-peak pricing that took effect at 16:00 UTC on 2026-08-16.
