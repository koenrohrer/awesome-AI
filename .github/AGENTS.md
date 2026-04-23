# Agent Guide: GitHub Metadata

This directory defines the contribution funnel and automated checks. Changes here affect how contributors enter the project.

## Rules

- Keep issue templates aligned with `CONTRIBUTING.md` and the badge vocabulary in the root `AGENTS.md`.
- Do not loosen required evidence fields unless the root contribution bar changes first.
- Keep PR checklist language direct and enforceable.
- Workflows should validate repository rules, not introduce unrelated automation.

## When Editing

- For issue templates, make required fields match the track bar: technique, tool, hardware.
- For CI, prefer simple checks that fail loudly and explain the missing evidence.
- Update `CONTRIBUTING.md` if a template or workflow changes contributor expectations.
