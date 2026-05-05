---
title: "Speech-Aware Text Language Models"
type: topic
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, speech-aware-text-lms, voice-assistants]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Speech-Aware Text Language Models

## Definition

Speech-aware text language models augment a text LM with a speech encoder or audio front end. They typically condition text generation on speech and text inputs, preserving the text LM's instruction-following and reasoning abilities while adding speech understanding.

## Why They Matter

This family is especially relevant for improving the general intelligence of voice assistants because it can reuse strong text LLM reasoning, retrieval, tool use, and instruction following. The main risk is that speech-specific information may be compressed into a representation that loses timing, speaker, prosody, or interaction cues.

## Key Questions

- How should speech representations be aligned with the text LM embedding space?
- Which adapter or alignment method best preserves both semantic and paralinguistic information?
- How can tool use, text injection, and retrieval-augmented generation be added without reducing speech robustness?
- When does this architecture outperform cascaded ASR -> LLM approaches?

## Related Pages

- [[topics/spoken-language-models]]
- [[methods/slm-generation-and-training-strategies]]
- [[topics/full-duplex-voice-assistants]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
