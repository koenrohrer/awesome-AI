# Prompting

Evidence-backed prompting techniques. Every entry carries `[paper]`, `[provider-doc]`, or `[tested]`. Claims stay only when a paper, provider doc, or maintainer-run test supports them.

## Techniques

- **[Chain-of-thought prompting](chain-of-thought.md)** `[paper]` — Step-by-step reasoning improves accuracy on multi-step benchmarks, with added token cost.
- **[Few-shot prompting](few-shot.md)** `[paper]` — In-context examples steer task format and behavior; gains flatten after enough representative examples.
- **[Self-consistency](self-consistency.md)** `[paper]` — Sample multiple CoT paths and majority-vote the answer on discrete-answer reasoning tasks.
- **[Self-refine](self-refine.md)** `[paper]` — Generate, critique, and revise where the task has recognizable failure modes.
- **[Tree of Thoughts](tree-of-thoughts.md)** `[paper]` — CoT generalized to a tree with search; for problems where one reasoning path isn't enough.
- **[Least-to-most prompting](least-to-most.md)** `[paper]` — Decompose to subproblems, solve sequentially with accumulating context.
- **[Prompt chaining](prompt-chaining.md)** `[provider-doc]` — Break complex tasks into multiple focused prompts with explicit intermediate outputs.
- **[Extended thinking / reasoning modes](extended-thinking.md)** `[provider-doc]` — Provider-native reasoning-token budgets on Claude, OpenAI o-series, and Gemini.
- **[Prompt caching](prompt-caching.md)** `[provider-doc]` — Reuse a static prefix across requests to cut input-token cost ~90% and reduce latency materially.
- **[Structured output (JSON mode)](structured-output.md)** `[provider-doc]` — Schema-constrained generation reduces malformed JSON and unsupported fields.

## How `[tested]` works here

When a technique moves from `[paper]` to `[tested]`, we add:

```
prompting/tests/<slug>/
├── README.md      # what the test measures, which model(s), which prompt
├── baseline.md    # the prompt + full output without the technique
└── treatment.md   # the prompt + full output with the technique
```

The point is reproducibility: prompts, outputs, model details, and caveats stay visible.

## What doesn't belong in this section

- "I found this prompt works well on Twitter" — no citation, out.
- Long prompt libraries with no evidence — link out to them, don't absorb them.
- Model-specific lore ("Claude loves XML tags") — goes in `providers/anthropic/README.md` with its own citation, not here.
