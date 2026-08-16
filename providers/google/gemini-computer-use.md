# Gemini Computer Use `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

| Field | Value |
|---|---|
| Product shape | Preview tool capability on general Gemini models, plus one legacy standalone model ID |
| Models listed in the guide | `gemini-3.6-flash`, `gemini-3.5-flash`, `gemini-3.5-flash-lite`, `gemini-3-flash-preview`, and `gemini-2.5-computer-use-preview-10-2025` |
| Recommended model | `gemini-3.6-flash` |
| Legacy standalone model | `gemini-2.5-computer-use-preview-10-2025`, described as a legacy preview model for browser-based computer use |
| Environments | Browser, mobile, and desktop |
| Client responsibility | Execute actions, capture screenshots, enforce permissions, and terminate the loop |

## What it is

Computer Use lets supported Gemini models inspect screenshots and propose UI actions such as clicks, scrolling, and typing. Gemini 3.x responses add action intents, configurable safety policies, and optional prompt-injection detection.

There is no callable model named “Gemini 3.5 Computer Use.” On the Gemini 3.x models, enable the `computer_use` tool on a supported model. The one exception is the legacy `gemini-2.5-computer-use-preview-10-2025` ID above. Google recommends Gemini 3.6 Flash for new Computer Use integrations.

Two Google pages disagree as of the review date: the [Gemini 3.7 Flash model page](https://ai.google.dev/gemini-api/docs/models/gemini-3.7-flash) marks computer use as a supported preview capability, while the [Computer Use guide](https://ai.google.dev/gemini-api/docs/computer-use) neither lists 3.7 Flash among its models nor changes its 3.6 Flash recommendation. Verify against the guide before targeting 3.7 Flash for this workload.

## Safety boundary

Google labels Computer Use as preview and warns that it can make errors or expose security vulnerabilities. Run the action handler in an isolated environment, supervise important tasks, require confirmation for consequential actions, and avoid critical decisions or sensitive data.

## Links

- [Computer Use guide](https://ai.google.dev/gemini-api/docs/computer-use)
- [Gemini models](https://ai.google.dev/gemini-api/docs/models)

## Status

`[provider-doc]`.
