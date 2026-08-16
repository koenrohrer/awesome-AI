# Meta Model API and Muse Spark 1.2 `[provider-doc]`

*Last reviewed: 2026-08-16.*

## At a glance

- Provider: Meta
- Product surface: Meta Model API
- Current hosted model: Muse Spark 1.2
- Availability: Public preview, described by Meta as "now available with expanded global access"
- Context window: 1,048,576 tokens
- Base URL: `https://api.meta.ai/v1`, drop-in compatible with the OpenAI SDK
- Official docs: [Meta Model API](https://developer.meta.com/ai/products/meta-model-api/)

## What it is

The Meta Model API is Meta's first-party hosted developer surface for the Muse Spark models. Muse Spark 1.2 is the current release, announced on 2026-08-05 alongside the [Muse Code](muse-code.md) agent. Meta describes 1.2 as "optimized for real coding workflows, with higher first-attempt accuracy and more reliable tool calling." [Muse Spark 1.2 model page](https://developer.meta.com/ai/models/muse-spark/).

The launch post describes 1.2 as trained on whole-repository generation and other long-running tasks, co-trained with the Muse Code harness so tool calls and plans execute cleanly, and using planning, goal conditioning, and context compaction to hold direction across long sessions. [Meet Muse Spark 1.2 and Muse Code](https://developer.meta.com/ai/resources/blog/build-with-muse-code/).

This hosted surface is distinct from Meta's downloadable weights. Meta distributes Llama under the Llama Community License and [Muse Glimmer 30B](models/muse-glimmer-30b.md) under Apache 2.0, but has not announced downloadable Muse Spark 1.1 or 1.2 weights.

## Models and pricing

Meta lists three model IDs, all at a 1,048,576-token context window:

| Model ID | Input | Cached input | Output | Data use |
|---|---|---|---|---|
| `muse-spark-1.2` | $1.25/Mtok | $0.15/Mtok | $4.25/Mtok | "Not used to improve our products." |
| `muse-spark-1.2-contributor` | $0.10/Mtok | $0.002/Mtok | $0.20/Mtok | "Used to improve our products." |
| `muse-spark-1.1` | $1.25/Mtok | $0.15/Mtok | $4.25/Mtok | — |

The contributor tier is roughly a 12x input and 21x output discount in exchange for Meta using the traffic to improve its products. Treat that as a data-governance decision, not a pricing decision. [Meta Model API pricing](https://developer.meta.com/ai/products/meta-model-api/).

Muse Spark 1.1 is still served, so 1.2 is an addition rather than a forced migration as reviewed on 2026-08-16.

## Capabilities

Meta's API docs list all three model IDs as accepting text, image, video, and PDF input, with tool calling, structured output, and search grounding. [Model reference](https://ai.developer.meta.com/docs/models/). Muse Spark also powers Thinking mode in the Meta AI app and on `meta.ai`.

## Evidence gaps

- Meta published an evaluation report stamped to Muse Spark 1.1 and a Safety & Preparedness Report covering Muse Spark as the model underlying Meta AI. Neither is version-stamped to 1.2, and as reviewed on 2026-08-16 no 1.2-specific report exists.
- The 1.2 launch post names TerminalBench, DeepSWE, Meta Internal Code Bench, and GDPVAL as evaluation targets without a published harness. Those numbers are not reproduced here.
- The API remains labelled public preview. Meta publishes no general-availability date, deprecation policy, or rate-limit commitment, so recheck the docs before pinning production assumptions.

## Links

- [Meta Model API](https://developer.meta.com/ai/products/meta-model-api/)
- [Muse Spark model page and pricing](https://developer.meta.com/ai/models/muse-spark/)
- [Meet Muse Spark 1.2 and Muse Code](https://developer.meta.com/ai/resources/blog/build-with-muse-code/)
- [Model API quickstart](https://ai.developer.meta.com/docs/quickstart/)
- [Introducing Muse Spark 1.1](https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/)
- [Muse Spark 1.1 Evaluation Report](https://ai.meta.com/static-resource/muse-spark-1-1-evaluation-report)
- [Muse Spark Safety & Preparedness Report](https://ai.meta.com/static-resource/muse-spark-safety-and-preparedness-report/)

## Status

`[provider-doc]`. Public-preview hosted API. Muse Spark is not an open-weight release; the open-weight Muse model is [Muse Glimmer 30B](models/muse-glimmer-30b.md).
