# Self-hosted

Running AI locally or on your own infra.

## Sections

- **[Runners](runners/)** — ollama, LMStudio, llama.cpp, vLLM, Jan, GPT4All. `[vetted-tool]` entries.
- **[Workflows](workflows/)** — local-first setups that work end-to-end (not "here's a docker-compose; good luck"). `[tested]` when a maintainer has run it.
- **[Hardware](hardware/)** — sourced hardware guides. `[sourced]` entries only — every spec cites a named third-party source.

## Hardware rule

The maintainer does not own the hardware benchmarks shown here. **Every hardware claim must cite a named third-party source:**

- An Apple, NVIDIA, AMD, Intel spec sheet (linked).
- A HuggingFace leaderboard entry (dated).
- A named YouTuber's benchmark video (creator + title + timestamp for the number).
- A GitHub issue / discussion with reproducible numbers.

If someone submits "I heard the M4 Max does 40 tok/s," we close the PR. That's the discipline — without it, the section becomes another rumor mill.

## Runner comparison page (planned)

A single `runners/comparison.md` will table-compare ollama vs LMStudio vs llama.cpp vs vLLM across:
- Setup effort
- GPU/CPU support matrix
- Model format support (GGUF, Safetensors, AWQ, GPTQ)
- Performance characteristics (sourced from upstream benchmarks)
- When to pick which

## Status

Scaffolded in v0.4. Section primers exist; sourced/tested entries are still being seeded.
