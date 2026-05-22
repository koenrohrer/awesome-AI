# How to think about local AI

## The Short Version

Local AI is a deployment choice, not a virtue by itself. It can help when you need local control, offline operation, private data handling, custom runners, or predictable experiments. It also moves model selection, runtime support, memory limits, updates, and hardware tradeoffs onto you.

This repository's self-hosted section is still scaffolded. The runners, workflows, and hardware pages define the planned evidence bar, but there are not yet mature sourced runner comparisons or tested local workflows.

Use architecture entries to frame the decisions before buying hardware or committing to a runner. KV cache explains why long context stresses memory. Tokenization explains why prompts consume capacity unevenly. MoE explains why total parameters can mislead. Fine-tuning and LoRA explain when local adaptation is different from retrieval or prompting.

## Use This Guide When

Use this guide when you are deciding whether to run models on your own machine or infrastructure, choosing a local runner, planning a local-first workflow, or trying to understand which architecture concepts affect local inference.

## Fast Path

- **[Self-hosted](../self-hosted/README.md)** — start with the section status and evidence rules.
- **[Local LLM runners](../self-hosted/runners/README.md)** — runner comparison is planned; no curated runner entries yet.
- **[Self-hosted workflows](../self-hosted/workflows/README.md)** — tested local workflows are planned; no curated entries yet.
- **[Hardware](../self-hosted/hardware/README.md)** — planned section; hardware claims will require named third-party sources.
- **[KV cache and PagedAttention](../learning/architecture/kv-cache.md)** `[paper]` — read before judging long-context memory claims.
- **[Tokenization: BPE and SentencePiece](../learning/architecture/tokenization.md)** `[paper]` — read before estimating context and prompt cost.
- **[Fine-tuning and LoRA](../learning/architecture/fine-tuning-lora.md)** `[paper]` — read before deciding whether local adaptation is worth it.

## Decision Points

Decide whether local is required or merely preferred. Privacy, offline use, reproducibility, latency, cost control, and experimentation are different requirements.

Decide whether you need inference, retrieval, fine-tuning, or an agent workflow. Each stresses the system differently, and a runner that is comfortable for chat may not be the right choice for serving, batching, adapters, or tool loops.

Decide what evidence you will accept for hardware. This repo requires `[sourced]` hardware claims, so treat unsourced throughput and compatibility numbers as candidates, not guidance.

## Field Notes

Memory is the recurring constraint. Model weights matter, but KV cache can dominate as context length, batch size, and parallel sampling grow.

Runner support is practical evidence. File formats, GPU backends, quantization support, batching, adapter handling, and server APIs matter more than a generic "runs locally" claim.

MoE models need careful reading. Total parameters, active parameters, memory residency, and routing overhead are different concerns.

Fine-tuning is not the first answer to changing facts. If the problem is updateable knowledge, retrieval is usually the architecture to evaluate first.

## What To Avoid

Avoid buying hardware from unsourced tokens-per-second claims.

Avoid treating the self-hosted section as complete. It is a scaffold with planned runner, workflow, and hardware coverage.

Avoid comparing local and hosted setups on a single dimension. Control, maintenance burden, latency, privacy, eval reproducibility, and operational skill all matter.

Avoid assuming a smaller local model plus a larger prompt will behave like a hosted frontier model. Test the actual task.

## Evidence Library

- **[Self-hosted](../self-hosted/README.md)**
- **[Local LLM runners](../self-hosted/runners/README.md)**
- **[Self-hosted workflows](../self-hosted/workflows/README.md)**
- **[Hardware](../self-hosted/hardware/README.md)**
- **[KV cache and PagedAttention](../learning/architecture/kv-cache.md)** `[paper]`
- **[Mixture-of-experts (MoE)](../learning/architecture/mixture-of-experts.md)** `[paper]`
- **[Fine-tuning and LoRA](../learning/architecture/fine-tuning-lora.md)** `[paper]`
- **[Tokenization: BPE and SentencePiece](../learning/architecture/tokenization.md)** `[paper]`
- **[Retrieval-augmented generation (RAG)](../learning/architecture/rag.md)** `[paper]`
- **[TurboQuant](../learning/architecture/turboquant.md)** `[paper]`
- **[Hermes Agent](../tools/candidates/hermes-agent.md)** `[vetted-tool]`
- **[OpenClaw](../tools/candidates/openclaw.md)** `[vetted-tool]`
- **[OpenShell](../tools/candidates/openshell.md)** `[vetted-tool]`
- **[Pi Agent](../tools/candidates/pi-agent.md)** `[vetted-tool]`
