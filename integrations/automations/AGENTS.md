# Agent Guide: Automations

This directory covers recurring or trigger-based AI workflows where the automation itself is the main artifact.

## Rules

- Prefer `[tested]` recipes with trigger conditions, inputs, outputs, run date, and caveats.
- Use `[vetted-tool]` only for productized automation surfaces with a narrow proven scope.
- State what runs automatically, what requires review, and how failures are handled.
- Put shell-first, CI-native, no-code-platform-first, and provider-owned product docs in their more specific directories.
