# Fine-tuning and LoRA `[paper]`

## One-sentence TL;DR

Fine-tuning adapts a pretrained model by training on task or domain examples; LoRA makes that adaptation cheaper by training small low-rank matrices while freezing the base weights.

## Citation

Hu, E. J., Shen, Y., Wallis, P., Allen-Zhu, Z., Li, Y., Wang, S., Wang, L., & Chen, W. (2021). *LoRA: Low-Rank Adaptation of Large Language Models.* [arxiv.org/abs/2106.09685](https://arxiv.org/abs/2106.09685)

## What fine-tuning changes

Fine-tuning changes model behavior by updating weights with examples of the target behavior. It is the right lever when the desired behavior is stable, repeated, and hard to express reliably with prompt context alone.

It is the wrong first lever when the problem is missing factual knowledge that changes often. That is usually a retrieval problem.

## What LoRA changes

Full fine-tuning updates all model parameters. LoRA freezes the base model and inserts trainable low-rank matrices into transformer layers. At inference time, those learned adapters can be merged or applied with little overhead.

The architectural idea is that task adaptation often lives in a low-dimensional update. You do not need to copy or retrain the whole model to shift behavior for many downstream tasks.

## Why it matters

- Full fine-tuning can be expensive, brittle, and hard to serve across many tasks.
- LoRA and related PEFT methods make many domain adaptations practical on smaller hardware.
- Adapter management becomes a product and infra problem: which base model, which adapter, which evaluation set, and how to prevent regressions.

## Read it when

- You are deciding between prompt engineering, RAG, and fine-tuning.
- You need to adapt tone, format, classification boundaries, or domain-specific behavior.
- You are evaluating claims about "custom models" that may only be adapters.

## Related entries

- `learning/architecture/rag.md` — prefer retrieval when the problem is changing knowledge.
- `learning/papers/instructgpt.md` — instruction tuning and RLHF are alignment-stage training, not just app-level fine-tuning.
- `prompting/few-shot.md` — examples in context are the lightest-weight adaptation path.

## Status

`[paper]`.
