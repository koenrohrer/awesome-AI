# Providers

Per-provider deep dives. Each provider gets a folder, not a single flat file: start with the provider overview, then drill into product surfaces when the vendor has multiple distinct apps, runtimes, or workflows.

## Folder structure

```text
providers/
  <provider>/
    README.md      # provider overview: model lines, strengths/weaknesses, docs
    <surface>.md   # optional product-specific page (desktop app, coding agent, image stack, etc.)
```

## Providers

### Closed frontier

- **[Anthropic](anthropic/)** `[provider-doc]` — Claude model families plus Anthropic-specific product surfaces like Claude Code, Claude Desktop, and Claude Design.
- **[OpenAI](openai/)** `[provider-doc]` — GPT and o-series model lines plus Codex, ChatGPT Desktop, and image-generation surfaces.
- **[Google](google/)** `[provider-doc]` — Gemini models, long-context API guidance, and Google-specific deployment surfaces.
- **[xAI](xai/)** `[provider-doc]` — Grok models, consumer/API split, and live-data positioning.

### Open-weight and Chinese labs

- **[Moonshot AI](moonshot/)** `[provider-doc]` — Kimi long-context models and open-weight releases.
- **[Alibaba](alibaba/)** `[provider-doc]` — Qwen general and specialist variants.
- **[DeepSeek](deepseek/)** `[provider-doc]` — V3, R1, Coder, and open-weight reasoning.
- **[Meta](meta/)** `[provider-doc]` — Llama-family open weights and adjacent safety surfaces.
- **[Mistral](mistral/)** `[provider-doc]` — proprietary platform + open-weight dual track.

More providers (Phi, Command R, Yi) land in a later wave.

## Editorial rules

- Provider overview pages stay comparable across vendors: current model lines, strengths, weaknesses, best-fit tasks, quirks, docs.
- Product-specific subpages exist only when the surface is operationally different enough to deserve its own curation track.
- Every concrete strength/weakness claim still needs a citation. Product pages can start as primers, then accumulate cited entries.
- No grand provider rankings. If a benchmark compares providers, link the benchmark with its date and methodology.
