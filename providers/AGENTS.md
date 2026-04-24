# Agent Guide: Providers

This directory contains per-provider ecosystems: provider overviews, current model-line pages, and product surfaces owned by the provider.

## Evidence Bar

- Use `[provider-doc]` for provider and model facts.
- Verify model names, context windows, pricing, modalities, deprecations, and feature support against official docs before editing.
- Keep `Last reviewed: YYYY-MM-DD` lines accurate when touching date-sensitive facts.
- Use tables by default for model comparisons. Prefer compact rows for model ID, role, context, modalities, tools, pricing/status, and links over paragraph-only summaries.
- Include benchmark columns or benchmark tables where applicable, but only for named benchmarks with a date, source, and methodology link. Do not mix benchmark scores from incompatible dates or settings without saying so.
- Do not add grand provider rankings. If a benchmark compares providers, cite the benchmark with date and methodology.

## Placement

- Provider overview facts belong in `providers/<provider>/README.md`.
- Individual current model lines belong in `providers/<provider>/models/*.md`.
- Product surfaces belong under the provider that owns them when the surface is operationally distinct enough to deserve a page.

## Model Page Shape

- Start model pages with an "At a glance" table or compact bullet block, then use tables for comparable facts.
- Use prose for interpretation, caveats, and integration notes, not as the only way to present comparable model facts.
- Benchmark sections should name the benchmark, task/domain, reported score, date/source, and whether the result is provider-reported or independently reported.
