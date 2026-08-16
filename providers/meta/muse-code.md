# Muse Code `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

- Provider: Meta
- Product surface: terminal coding agent
- Availability: Beta, described in the launch post as "early beta"
- Model: Muse Spark 1.2, co-trained with the harness
- Announced: 2026-08-05
- Official docs: [Muse Code](https://developer.meta.com/ai/products/muse-code/)

## What it is

Muse Code is Meta's terminal coding agent. It gets its own page rather than a section on [Meta Model API and Muse Spark 1.2](muse-model-api.md) because it is a separate product surface: a local CLI on its own beta track and install path, not an API endpoint. Meta describes it as "a purpose-built coding agent optimized for long-horizon, multi-agentic coding workflows." [Meet Muse Spark 1.2 and Muse Code](https://developer.meta.com/ai/resources/blog/build-with-muse-code/).

Install is one command, with browser-based authentication at `dev.meta.ai`:

```
curl -fsSL https://dev.meta.ai/install.sh | bash
```

## Multi-agent execution

Muse Code runs sub-agents concurrently rather than one agent at a time. Meta's product page describes "workers in parallel, reviewers in the background." The concurrency-safety mechanism is named in the launch post: "each child gets its own git worktree, so parallel children never collide on the same files." [Muse Code](https://developer.meta.com/ai/products/muse-code/), [launch post](https://developer.meta.com/ai/resources/blog/build-with-muse-code/).

That worktree-per-child design is the load-bearing detail. It is what makes parallel sub-agents a filesystem-safe pattern instead of a race on a shared checkout.

## Auditability

Meta documents the agent as observable and replayable: "every subagent it spawns, every tool call, every steer and cancel, is observable and replayable." Two behaviors build on that event log:

- **Resume.** If a session is killed or crashes, the next session reads the log and continues from the last recorded step.
- **Goal tracking.** A stated goal is held across the session so the merged result matches what was originally asked for.

[Meet Muse Spark 1.2 and Muse Code](https://developer.meta.com/ai/resources/blog/build-with-muse-code/).

## Caveats

- **Beta.** Meta labels it early beta and publishes no stability, support, or deprecation commitment.
- **Cost flows through the API.** Muse Code runs on Muse Spark 1.2, so the [Meta Model API pricing tiers](muse-model-api.md#models-and-pricing) apply, including the contributor tier whose traffic Meta uses to improve its products.
- **Piped installer.** The documented install path pipes a remote script into a shell. Review it before running on a machine with repository credentials.
- **No published benchmark harness.** The launch post names TerminalBench, DeepSWE, Meta Internal Code Bench, and GDPVAL without a reproducible methodology.

## Links

- [Muse Code product page](https://developer.meta.com/ai/products/muse-code/)
- [Meet Muse Spark 1.2 and Muse Code](https://developer.meta.com/ai/resources/blog/build-with-muse-code/)
- [Meta AI developer products](https://developer.meta.com/ai/)

## Related sections

- [Meta Model API and Muse Spark 1.2](muse-model-api.md)
- [Subagents](../../extensions/subagents/README.md)

## Status

`[provider-doc]`. Beta terminal agent. Product surface, not a model release.
