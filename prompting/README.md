# Prompting

Evidence-backed prompting techniques. Every entry carries `[paper]`, `[provider-doc]`, or `[tested]`. If a claim can't be backed by one of those, it doesn't belong here.

This is the flagship section of the repo. It's where vague folk wisdom gets filtered against the research and provider documentation that actually supports it.

## Techniques

- **[Chain-of-thought prompting](chain-of-thought.md)** `[paper]` — "Let's think step by step" lifts reasoning accuracy on multi-step tasks by a double-digit margin on published benchmarks.
- **[Few-shot prompting](few-shot.md)** `[paper]` — In-context examples outperform zero-shot on most tasks; diminishing returns past ~8 examples on many benchmarks.
- **[Prompt caching](prompt-caching.md)** `[provider-doc]` — Reuse a static prefix across requests to cut input-token cost ~90% and reduce latency materially.
- **[Structured output (JSON mode)](structured-output.md)** `[provider-doc]` — Schema-constrained generation eliminates parsing errors and reduces hallucinated fields.

## How `[tested]` works here

When a technique moves from `[paper]` to `[tested]`, we add:

```
prompting/tests/<slug>/
├── README.md      # what the test measures, which model(s), which prompt
├── baseline.md    # the prompt + full output without the technique
└── treatment.md   # the prompt + full output with the technique
```

The point is not rigor in the academic sense — it's showing our work so you can reproduce.

## What doesn't belong in this section

- "I found this prompt works well on Twitter" — no citation, out.
- Long prompt libraries with no evidence — link out to them, don't absorb them.
- Model-specific lore ("Claude loves XML tags") — goes in `models/claude.md` with its own citation, not here.
