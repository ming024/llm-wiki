---
title: "Speech+Text Language Models"
type: topic
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, speech-text-lms, multimodal-generation]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Speech+Text Language Models

## Definition

Speech+text language models jointly model speech and text. They can represent or generate both modalities, making them a bridge between pure speech modeling and text-LM-centered speech assistants.

## Why They Matter

Speech+text LMs are central for systems that need both linguistic reasoning and spoken output. They are especially relevant to full-duplex assistants because they can support hybrid generation strategies where text tokens improve semantic content while speech tokens carry timing, style, and acoustic realization.

## Key Questions

- What is the best way to synchronize text and speech token streams with different rates and lengths?
- Should text and speech be interleaved, padded, generated in stages, or represented as parallel channels?
- How much text-side reasoning can be preserved while generating natural speech?
- How do hybrid text-speech generation strategies affect latency in interactive assistants?

## Related Pages

- [[topics/spoken-language-models]]
- [[methods/slm-generation-and-training-strategies]]
- [[topics/full-duplex-voice-assistants]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
