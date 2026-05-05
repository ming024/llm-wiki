---
title: "Text-Speech Hybrid Generation"
type: method
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, generation, speech-text, voice-assistants]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Text-Speech Hybrid Generation

## Definition

Text-speech hybrid generation uses text tokens together with speech tokens during generation. The goal is to leverage text LM knowledge for factuality and linguistic quality while still producing spoken output.

## Strategies

- Text sequence first, then speech tokens, similar to text-to-speech.
- Fixed padding to align text and speech token rates.
- Dynamic padding learned from time-aligned speech-text pairs.
- Single-channel interleaving text and speech tokens in a single sequence using precomputed alignments.

## Trade-Offs

Hybrid generation can make generated speech more semantically grounded and easier to evaluate, because the text stream can expose content. The central difficulty is synchronization: text and speech tokens operate at different rates and lengths, so alignment choices affect latency, quality, and interaction.

## Research Questions

- How should text-side reasoning, retrieval, and tool calls be synchronized with speech token generation?
- Which hybrid generation strategy is most suitable for streaming and full-duplex assistants?
- Can text tokens improve factuality without making speech output feel delayed or TTS-like?
- How should evaluations separate content correctness from acoustic quality and interaction timing?

## Related Pages

- [[methods/slm-generation-and-training-strategies]]
- [[topics/speech-text-language-models]]
- [[topics/speech-aware-text-language-models]]
- [[topics/full-duplex-voice-assistants]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
