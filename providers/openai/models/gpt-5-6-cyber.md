# GPT-5.6 Cyber `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Provider | OpenAI |
| Model ID | `gpt-5.6-cyber` |
| Alias | `daybreak-red-latest` (default snapshot `gpt-5.6-cyber`) |
| Availability | Gated. OpenAI requires separate approval and provisioning through the Daybreak program |
| Context / max input / max output | 400,000 / 272,000 / 128,000 tokens |
| Modalities | Text input/output; image input |
| Knowledge cutoff | February 16, 2026 |
| API price per 1M tokens | $12.50 input, $1.25 cached input, $75 output |
| Endpoints | `v1/responses` only |

## What it is

GPT-5.6 Cyber is OpenAI's purpose-trained cybersecurity model. The model page scopes it to approved defenders doing authorized vulnerability research, exploit validation, and security testing, and states that the model requires separate approval and provisioning. [GPT-5.6 Cyber model page](https://developers.openai.com/api/docs/models/gpt-5.6-cyber).

It is not part of the self-serve catalog. Without Daybreak provisioning the ID is not callable.

## Daybreak access tiers

OpenAI added two Daybreak access tiers on August 7, 2026. Each tier is exposed as a `-latest` alias that resolves to an existing model. [Changelog](https://developers.openai.com/api/docs/changelog).

| Alias | Default snapshot | Context / max input / max output | Scope stated in the docs |
|---|---|---|---|
| `daybreak-red-latest` | `gpt-5.6-cyber` | 400,000 / 272,000 / 128,000 | "advanced cybersecurity models for authorized vulnerability research and security testing" |
| `daybreak-blue-latest` | `gpt-5.6-sol` | 1,050,000 / 922,000 / 128,000 | "frontier general-purpose models, with safeguards calibrated for defensive cybersecurity work" |

The changelog directs defensive work — vulnerability discovery, secure code review, detection engineering, incident response, malware analysis, patch validation — to Daybreak Blue, and reserves Daybreak Red for authorized vulnerability reproduction, exploit validation, penetration testing, red teaming, and complex system analysis. [Daybreak Red model page](https://developers.openai.com/api/docs/models/daybreak-red-latest), [Daybreak Blue model page](https://developers.openai.com/api/docs/models/daybreak-blue-latest).

Both aliases are Responses-only, so a Chat Completions integration cannot call them without migration.

## API and tool support

The model page lists streaming, structured outputs, function calling, file search, image input, web search, and prompt caching. Its tool list matches the GPT-5.6 family: web search, file search, image generation, code interpreter, hosted shell, apply patch, skills, computer use, MCP, and tool search.

Rate limits are tier-scaled and listed on the model page. [GPT-5.6 Cyber model page](https://developers.openai.com/api/docs/models/gpt-5.6-cyber).

## Access, policy, and safety context

- Access is identity-gated. The GPT-5.6 system card describes Trusted Access for Cyber as "an identity-gated access pathway that provides higher-risk dual-use cyber capabilities to enterprise customers, verified defenders, and other legitimate users". Individual members must enable Advanced Account Security to retain access, and OpenAI states it restricts access for high-risk entities and jurisdictions. [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6).
- Under the Preparedness Framework, OpenAI treats GPT-5.6 Sol, Terra, and Luna as High capability in Cybersecurity and in Biological and Chemical risk, and says none reach the High threshold in AI Self-Improvement. [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6).
- OpenAI has not published a system card specific to GPT-5.6 Cyber as of this review. The GPT-5.6 system card was published July 9, 2026 and covers Sol, Terra, and Luna; the Daybreak tiers shipped a month later. Read the family card as background, not as coverage of this model.
- Engagement authorization is the gating constraint, not model capability. The docs scope both tiers to explicitly authorized work.

## Links

- [Model page](https://developers.openai.com/api/docs/models/gpt-5.6-cyber)
- [Daybreak Red model page](https://developers.openai.com/api/docs/models/daybreak-red-latest)
- [Daybreak Blue model page](https://developers.openai.com/api/docs/models/daybreak-blue-latest)
- [API changelog](https://developers.openai.com/api/docs/changelog)
- [GPT-5.6 system card](https://deploymentsafety.openai.com/gpt-5-6)

## Status

`[provider-doc]`. Available only to approved Daybreak participants. Not callable from a standard API account.
