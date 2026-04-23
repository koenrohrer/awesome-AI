# Agent Guide: Providers

This directory contains per-provider ecosystems: provider overviews, current model-line pages, and product surfaces owned by the provider.

## Evidence Bar

- Use `[provider-doc]` for provider and model facts.
- Verify model names, context windows, pricing, modalities, deprecations, and feature support against official docs before editing.
- Keep `Last reviewed: YYYY-MM-DD` lines accurate when touching date-sensitive facts.
- Do not add grand provider rankings. If a benchmark compares providers, cite the benchmark with date and methodology.

## Placement

- Provider overview facts belong in `providers/<provider>/README.md`.
- Individual current model lines belong in `providers/<provider>/models/*.md`.
- Product surfaces belong under the provider that owns them when the surface is operationally distinct enough to deserve a page.
