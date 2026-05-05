---
title: "Pure Speech Language Models"
type: topic
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, pure-speech-lms, speech-tokenization]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Pure Speech Language Models

## Definition

Pure speech language models model the distribution of speech itself, often as tokenized speech sequences. In the SLM survey taxonomy, they are analogous to pure text LMs, but their tokens are speech representations rather than text subwords.

## Why They Matter

Pure speech LMs are important for understanding what can be learned directly from speech without routing everything through text. They are especially relevant when the assistant needs to preserve or generate prosody, speaker style, affect, timing, or other acoustic information that a transcript may discard.

## Key Questions

- Which speech tokenization scheme preserves the right balance of linguistic and acoustic information?
- How much can next-token prediction over speech tokens learn about meaning, style, and interaction?
- Can pure speech LMs support general assistant intelligence, or do they need text-side reasoning modules?
- How do hierarchical token generation and codec design affect latency and quality?

## Related Pages

- [[topics/spoken-language-models]]
- [[methods/slm-generation-and-training-strategies]]
- [[topics/full-duplex-voice-assistants]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
