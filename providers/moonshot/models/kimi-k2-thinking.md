# Kimi K2 Thinking `[provider-doc]`

*Last reviewed: 2026-08-16. Discontinued on the hosted platform.*

## At a glance

- Provider: Moonshot AI
- Model IDs: `kimi-k2-thinking`, `kimi-k2-thinking-turbo`
- Hosted status: Deprecated. The platform model list states the `kimi-k2` series was officially discontinued on May 25, 2026
- Official docs: [model list](https://platform.kimi.ai/docs/models)

## What it was

Kimi K2 Thinking was Moonshot's dedicated reasoning path for multi-step tool use, separate from the base K2 line. Both IDs now appear only in the deprecated section of the platform model list. [Model list](https://platform.kimi.ai/docs/models).

## Migration

The current hosted paths that always reason are `kimi-k3`, which takes a `low`/`high`/`max` reasoning effort, and `kimi-k2.7-code`, which forces thinking on. See [Kimi K3](kimi-k3.md) and [Kimi K2.7 Code](kimi-k2-7-code.md). `kimi-k2.6` keeps a toggleable thinking mode.

Deprecation applies to the hosted API IDs. Open-weight K2 artifacts on [Moonshot's Hugging Face org](https://huggingface.co/moonshotai) are a separate surface and are not withdrawn by a hosted deprecation; check the individual model card and license.

## Public system card availability

Moonshot does not publish a public system-card page for these models.

## Links

- [Model list](https://platform.kimi.ai/docs/models)
- [Docs overview](https://platform.kimi.ai/docs/overview)
- [Moonshot on Hugging Face](https://huggingface.co/moonshotai)

## Status

`[provider-doc]`. Retained as a deprecation record, not a current option.
