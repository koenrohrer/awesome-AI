# Gemini Computer Use `[provider-doc]`

*Last reviewed: 2026-08-06.*

## At a glance

| Field | Value |
|---|---|
| Product shape | Preview tool capability, not a separate model ID |
| Supported 3.5 models | `gemini-3.5-flash`, `gemini-3.5-flash-lite` |
| Current recommended model | `gemini-3.6-flash` |
| Environments | Browser, mobile, and desktop |
| Client responsibility | Execute actions, capture screenshots, enforce permissions, and terminate the loop |

## What it is

Computer Use lets supported Gemini models inspect screenshots and propose UI actions such as clicks, scrolling, and typing. Gemini 3.x responses add action intents, configurable safety policies, and optional prompt-injection detection.

There is no callable model named “Gemini 3.5 Computer Use.” Enable the `computer_use` tool on a supported Gemini model. Google recommends Gemini 3.6 Flash for new Computer Use integrations.

## Safety boundary

Google labels Computer Use as preview and warns that it can make errors or expose security vulnerabilities. Run the action handler in an isolated environment, supervise important tasks, require confirmation for consequential actions, and avoid critical decisions or sensitive data.

## Links

- [Computer Use guide](https://ai.google.dev/gemini-api/docs/computer-use)
- [Gemini models](https://ai.google.dev/gemini-api/docs/models)

## Status

`[provider-doc]`.
