---
title: "Hierarchical Token Generation"
type: method
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, generation, speech-tokenization, codec]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Hierarchical Token Generation

## Definition

Hierarchical token generation covers decoding strategies for speech representations with multiple granularities, such as coarse phonetic tokens and finer audio codec tokens.

## Strategies

- Coarse first, then fine-grained: generate coarse tokens first, then condition finer speech tokens on them.
- Interleaved coarse and fine tokens: generate aligned token types within each time step.
- Temporal generation plus depth generation: use one model for inter-frame temporal structure and another head or model for intra-frame token depth.
- Delay pattern: delay fine-token prediction so the model can use look-ahead from future coarse tokens.

## Trade-Offs

Multi-stage prediction can improve audio quality and long-term consistency, but it increases decoding complexity and latency. This makes the method important but potentially difficult for low-latency full-duplex assistants.

## Research Questions

- Which hierarchy best balances quality, latency, and controllability?
- Can a hierarchy preserve prosody and speaker style while supporting semantic reasoning?
- How should hierarchical decoding interact with interruption handling and streaming generation?
- Can codec design reduce the need for multi-stage decoding?

## Related Pages

- [[methods/slm-generation-and-training-strategies]]
- [[topics/pure-speech-language-models]]
- [[topics/speech-text-language-models]]
- [[topics/full-duplex-voice-assistants]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
