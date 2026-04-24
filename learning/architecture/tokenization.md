# Tokenization: BPE and SentencePiece `[paper]`

## One-sentence TL;DR

Tokenization maps raw text into model vocabulary IDs; subword tokenizers make open-vocabulary language modeling practical while shaping cost, context length, and failure modes.

## Citations

- Sennrich, R., Haddow, B., & Birch, A. (2016). *Neural Machine Translation of Rare Words with Subword Units.* ACL 2016. [arxiv.org/abs/1508.07909](https://arxiv.org/abs/1508.07909)
- Kudo, T., & Richardson, J. (2018). *SentencePiece: A simple and language independent subword tokenizer and detokenizer for Neural Text Processing.* EMNLP 2018 demo. [arxiv.org/abs/1808.06226](https://arxiv.org/abs/1808.06226)

## What tokenization does

LLMs do not see raw strings. They see integer token IDs. A tokenizer defines how text is split, normalized, encoded, and later decoded.

Subword tokenization sits between character-level and word-level modeling. It can represent rare words, names, compounds, misspellings, and multiple languages without needing a vocabulary entry for every whole word.

## Why BPE and SentencePiece matter

Byte pair encoding (BPE) made subword units a practical default for neural sequence models. SentencePiece made tokenization more language-independent by training directly from raw text instead of assuming pre-tokenized word boundaries.

Modern LLM tokenizers vary by provider and model family, but the core tradeoff remains: vocabulary size, compression ratio, multilingual fairness, byte fallback, normalization behavior, and how many tokens a user's text consumes.

## Why it matters

- Token counts determine context-window usage and API cost.
- Tokenization can make some languages and scripts more expensive than others.
- Formatting tricks, whitespace, JSON, code, emojis, and rare symbols can change token counts sharply.
- A model cannot generate a string directly if its tokenizer cannot represent it cleanly.

## Read it when

- You are counting context budget or pricing long prompts.
- You are building multilingual or code-heavy applications.
- You are debugging weird failures around spacing, casing, emojis, or structured output.

## Related entries

- `prompting/structured-output.md` — tokenization affects JSON and schema reliability.
- `prompting/prompt-caching.md` — static prefixes only help after tokenization.
- `learning/papers/attention-is-all-you-need.md` — transformers operate on token embeddings, not raw text.

## Status

`[paper]`.
