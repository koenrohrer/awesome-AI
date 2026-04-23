# Agent Guide: Prompting Tests

This directory stores maintainer-run material for `[tested]` prompting entries.

## Required Shape

Each test should live in `prompting/tests/<slug>/` and include:

- `README.md`: what was tested, model and version, run date, result, and caveats.
- `baseline.md`: exact prompt and full output without the technique.
- `treatment.md`: exact prompt and full output with the technique.

## Rules

- Do not summarize away material outputs.
- Do not call a single example a benchmark.
- Redact only sensitive material and state that a redaction happened.
