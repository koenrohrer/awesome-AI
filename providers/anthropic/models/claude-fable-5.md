# Claude Fable 5 `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Provider | Anthropic |
| Model ID | `claude-fable-5` |
| Availability | Generally available in the Claude API and supported cloud platforms; available in Claude products through usage credits |
| Context / max output | 1M / 128K tokens |
| Modalities | Text and image input; text output |
| Thinking | Adaptive thinking always on; raw thinking is not returned |
| API price per 1M tokens | $10 input, $50 output |

## What it is

Claude Fable 5 is Anthropic's widely released Mythos-class model for demanding reasoning and long-horizon agentic work.

## Integration notes

- Safety classifiers can return `stop_reason: "refusal"` in a successful HTTP 200 response. Integrations must handle refusal and fallback explicitly.
- Fable 5 and Mythos 5 have 30-day data retention and are not available under zero data retention.
- Supported launch features include effort, task budgets in beta, memory, code execution, programmatic tool calling, compaction, and vision.
- Access was suspended on June 12 and restored globally on July 1, 2026. Current docs list the API model as active.

## Links

- [Models overview](https://platform.claude.com/docs/en/about-claude/models/overview)
- [Fable 5 and Mythos 5 API guide](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5)
- [Launch announcement](https://www.anthropic.com/news/claude-fable-5-mythos-5)
- [Redeployment update](https://www.anthropic.com/news/redeploying-fable-5)
- [System card](https://www-cdn.anthropic.com/2f9323abbcc4abe219577539efe19a623c9ca2bd/Claude%20Fable%205%20%26%20Claude%20Mythos%205%20System%20Card.pdf)

## Status

`[provider-doc]`. Generally available with model-specific refusal, fallback, billing, and retention behavior.
