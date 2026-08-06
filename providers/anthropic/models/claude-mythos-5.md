# Claude Mythos 5 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Provider | Anthropic |
| Model ID | `claude-mythos-5` |
| Availability | Limited release to approved Project Glasswing customers; no self-serve access |
| Context / max output | 1M / 128K tokens |
| Modalities | Text and image input; text output |
| Thinking | Adaptive thinking always on; raw thinking is not returned |
| API price per 1M tokens | $10 input, $50 output |

## What it is

Claude Mythos 5 uses the same underlying model as Fable 5 with selected safety classifiers removed for approved defensive-security partners.

## Integration notes

- Mythos 5 is not a generally available Claude API model. Access requires Project Glasswing approval through an Anthropic or cloud-provider account team.
- It succeeds the deprecated `claude-mythos-preview` model for approved customers.
- Fable 5 and Mythos 5 have 30-day data retention and are not available under zero data retention.
- The model's restricted availability and safeguard profile make it unsuitable as an automatic fallback for general applications.

## Links

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [Fable 5 and Mythos 5 API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5)
- [Project Glasswing](https://www.anthropic.com/project/glasswing)
- [Redeployment update](https://www.anthropic.com/news/redeploying-fable-5)
- [System card](https://www-cdn.anthropic.com/2f9323abbcc4abe219577539efe19a623c9ca2bd/Claude%20Fable%205%20%26%20Claude%20Mythos%205%20System%20Card.pdf)

## Status

`[provider-doc]`. Limited availability; not a public self-serve model.
