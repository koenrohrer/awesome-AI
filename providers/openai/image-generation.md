# Image generation

OpenAI's image-generation surface spans GPT Image models, the Image API, and the image-generation tool in the Responses API. This page exists separately from the OpenAI provider overview because image work has its own models, cost model, prompt patterns, and editing workflow.

*Last reviewed: 2026-08-16.*

## Current model

`gpt-image-2` is the only image model in OpenAI's current catalog. It takes text and image input, returns images, supports inpainting, and serves `v1/images/generations`, `v1/images/edits`, and `v1/batch`. [GPT Image 2 model page](https://developers.openai.com/api/docs/models/gpt-image-2).

The earlier models are gone or going: `dall-e-2` and `dall-e-3` were removed on May 12, 2026, `gpt-image-1` is scheduled for shutdown on October 23, 2026, and `gpt-image-1.5`, `gpt-image-1-mini`, and `chatgpt-image-latest` on December 1, 2026. OpenAI names `gpt-image-2` as the replacement in every case. [Deprecations](https://developers.openai.com/api/docs/deprecations).

## What belongs here

- GPT Image references
- Image-generation and image-editing workflows
- Guidance on when to use the Image API versus the Responses API tool surface

## Official docs

- [GPT Image 2 model page](https://developers.openai.com/api/docs/models/gpt-image-2)
- [Image generation guide](https://developers.openai.com/api/docs/guides/image-generation)
- [Image generation tool](https://developers.openai.com/api/docs/guides/tools-image-generation)

## Related sections

- [Tools](../../tools/README.md)
- [Prompting](../../prompting/README.md)

## Status

Introduced in v0.4. Primer page exists; curated entries are still being seeded.
