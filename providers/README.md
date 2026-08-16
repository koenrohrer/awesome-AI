# Providers

Per-provider deep dives. Each provider gets a folder, not a single flat file: start with the provider overview, use the [model directory](models/) for cross-provider discovery, then drill into product surfaces when the vendor has multiple distinct apps, runtimes, or workflows.

## Folder structure

```text
providers/
  models/          # cross-provider index linking seeded model pages
  <provider>/
    README.md      # provider overview: model lines, strengths/weaknesses, docs
    models/        # one file per current first-class model line where useful
    <surface>.md   # optional product-specific page (desktop app, coding agent, image stack, etc.)
```

## Model directory

- **[Provider model directory](models/)** `[provider-doc]` — date-stamped, cross-provider map of full model pages and docs-only releases.

## Providers

### Closed frontier

- **[Anthropic](anthropic/)** `[provider-doc]` — Fable, Opus, Sonnet, and Haiku models, limited-access Mythos, and Claude product surfaces.
- **[OpenAI](openai/)** `[provider-doc]` — GPT-5.6 and maintained older model lines plus Codex, ChatGPT Desktop, and image generation.
- **[Google](google/)** `[provider-doc]` — Gemini/Gemma models, preview Computer Use, and product surfaces such as Antigravity and Stitch.
- **[xAI](xai/)** `[provider-doc]` — Grok 4.5, Grok Build, first-party server tools, and historical migration coverage.

### Open-weight and Chinese labs

- **[Moonshot AI](moonshot/)** `[provider-doc]` — Kimi K3 hosted/open-weight flagship plus earlier K2 lines.
- **[Alibaba](alibaba/)** `[provider-doc]` — Hosted Qwen 3.7/3.8 Model Studio tiers plus Qwen 3.8 open weights in two sizes and earlier open-weight families.
- **[DeepSeek](deepseek/)** `[provider-doc]` — V4 hosted/open-weight models and retired legacy aliases.
- **[MiniMax](minimax/)** `[provider-doc]` — M3, maintained M2.x tiers, and broader multimodal platform surfaces.
- **[Meta](meta/)** `[provider-doc]` — Llama open weights plus hosted Muse model and media surfaces.
- **[Mistral](mistral/)** `[provider-doc]` — Hosted/open-weight general models plus OCR, formal-proof, and robotics specialists.

More providers (Phi, Command R, Yi) land in a later wave.

## Editorial rules

- Provider overview pages stay comparable across vendors: current model lines, strengths, weaknesses, fit guidance, quirks, docs.
- When a provider has enough active model surface area to justify it, add `models/*.md` pages for individual model lines and link them from the provider README.
- Product-specific subpages exist only when the surface is operationally different enough to deserve its own curation track.
- Every concrete strength/weakness claim still needs a citation. Product pages can start as primers, then accumulate cited entries.
- No grand provider rankings. If a benchmark compares providers, link the benchmark with its date and methodology.
