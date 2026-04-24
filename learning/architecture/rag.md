# Retrieval-augmented generation (RAG) `[paper]`

## One-sentence TL;DR

RAG combines a pretrained generator with retrieved external documents so answers can use non-parametric memory instead of relying only on facts stored in model weights.

## Citation

Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Kuttler, H., Lewis, M., Yih, W., Rocktaschel, T., Riedel, S., & Kiela, D. (2020). *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.* NeurIPS 2020. [arxiv.org/abs/2005.11401](https://arxiv.org/abs/2005.11401)

## What the architecture does

RAG splits a knowledge-intensive answer into two coupled steps:

- **Retrieve.** A retriever searches an external index for passages likely to contain the needed evidence.
- **Generate.** A seq2seq model conditions on the query plus retrieved passages, then generates the final answer.

The point is not "search plus chatbot" as a product pattern. The architecture is a memory split: model parameters hold general language and task behavior, while the retrieval index holds updateable factual context.

## Why it matters

Pure parametric memory is hard to update, hard to audit, and unreliable for long-tail facts. RAG gives a system a place to put knowledge that can be refreshed without retraining the model, and it gives readers a route to provenance when the retrieved evidence is surfaced.

Modern RAG systems usually add components that are outside the original paper: chunking, embedding models, vector databases, hybrid search, rerankers, citation rendering, and prompt-injection defenses. Those are implementation choices around the core retrieve-then-generate architecture.

## Read it when

- You are designing an app that must answer from private or changing documents.
- You need to decide between fine-tuning and retrieval.
- You are debugging hallucinations caused by missing or poorly ranked context.

## Related entries

- `learning/architecture/fine-tuning-lora.md` — changes the model; RAG changes the context.
- `learning/safety/indirect-prompt-injection.md` — retrieval introduces untrusted text into the model context.
- `prompting/structured-output.md` — useful for constraining RAG answers and citations.

## Status

`[paper]`.
