# Get better LLM outputs

## The Short Version

Start with the smallest intervention that matches the failure mode.

Use structured output when parsing or field reliability matters. Use prompt chaining when one prompt is doing several jobs. Add few-shot examples when the model needs to imitate a task format or label boundary. Use chain-of-thought, self-consistency, or extended thinking only for multi-step reasoning.

Retrieval-augmented generation belongs here only when the problem is missing, stale, or private context. It is an architecture choice, not a prompt-only fix. Prompt caching is an efficiency tool for repeated long prefixes, not a quality technique.

## Use This Guide When

Use this when a model is almost useful but its answers are inconsistent, malformed, under-specified, or weak on multi-step tasks. The goal is to pick one evidence-backed improvement at a time instead of stacking every prompting technique into one expensive prompt.

## Fast Path

- **[Structured output](../prompting/structured-output.md)** `[provider-doc]` — start here if downstream code needs reliable JSON or constrained fields.
- **[Prompt chaining](../prompting/prompt-chaining.md)** `[provider-doc]` — split extract, analyze, and format steps when one prompt is carrying too many responsibilities.
- **[Few-shot prompting](../prompting/few-shot.md)** `[paper]` — add examples when the model needs to copy a format, boundary, or task pattern.
- **[Chain-of-thought prompting](../prompting/chain-of-thought.md)** `[paper]` — use visible step-by-step reasoning for multi-step tasks where latency and token cost are acceptable.
- **[Extended thinking / reasoning modes](../prompting/extended-thinking.md)** `[provider-doc]` — use provider-native reasoning budgets when the task is hard enough to justify higher cost and latency.
- **[Self-consistency](../prompting/self-consistency.md)** `[paper]` — sample and vote when answers are discrete and the extra calls are acceptable.
- **[Retrieval-augmented generation](../learning/architecture/rag.md)** `[paper]` — add retrieval when the model needs external evidence, private documents, or updateable knowledge.

## Decision Points

- If the output must be machine-read, prefer structured output before adding examples or reasoning.
- If the task has separate stages, chain the stages and validate between them.
- If the model misunderstands labels, formats, or edge cases, use a small set of representative examples.
- If the model fails because it lacks the facts, use retrieval rather than more elaborate prompting.
- If the model fails on reasoning, choose either visible chain-of-thought, provider reasoning mode, or self-consistency; do not assume all three stack well.
- If repeated calls share a long prefix, add prompt caching after the prompt shape is stable.

## Field Notes

Structured output reduces parser failures, but it does not make the judgment correct. Chaining makes failures easier to locate, but each link adds latency and a handoff point.

Few-shot examples are sensitive to order and label balance. Chain-of-thought and self-consistency spend more tokens to improve reasoning. That tradeoff is poor for simple extraction, classification, or formatting work.

RAG shifts the hard part from "ask better" to "retrieve better." Bad chunks, stale indexes, missing provenance, or untrusted retrieved text can still produce bad answers. Treat retrieval as a system design decision with its own evaluation surface.

## What To Avoid

- Do not turn every prompt into a long chain when one constrained call works.
- Do not use reasoning modes for rigid JSON extraction unless testing shows a benefit.
- Do not use RAG as a substitute for clear task instructions or schema validation.
- Do not cite prompt caching as a quality improvement; it is a cost and latency pattern.
- Do not combine many techniques at once and then claim you know which one helped.

## Evidence Library

- **[Structured output](../prompting/structured-output.md)** `[provider-doc]`
- **[Prompt chaining](../prompting/prompt-chaining.md)** `[provider-doc]`
- **[Few-shot prompting](../prompting/few-shot.md)** `[paper]`
- **[Chain-of-thought prompting](../prompting/chain-of-thought.md)** `[paper]`
- **[Self-consistency](../prompting/self-consistency.md)** `[paper]`
- **[Extended thinking / reasoning modes](../prompting/extended-thinking.md)** `[provider-doc]`
- **[Prompt caching](../prompting/prompt-caching.md)** `[provider-doc]`
- **[Retrieval-augmented generation](../learning/architecture/rag.md)** `[paper]`
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]`
