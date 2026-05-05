---
title: "Dual-Channel Full-Duplex Models"
type: method
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [full-duplex, voice-assistants, spoken-language-models, dialogue]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Dual-Channel Full-Duplex Models

## Definition

Dual-channel full-duplex models maintain separate listening and speaking channels. The listening channel continuously receives user input, while the speaking channel tracks the assistant's own generated speech.

## Why It Matters

This design directly represents simultaneous listening and speaking. It can support interruption handling, backchannels, and self-monitoring because the model can condition on both what the user is saying and what the assistant is currently outputting.

The trade-off is architectural complexity. Dual-channel systems may require specialized input structures or model architectures rather than directly reusing a standard decoder-only LLM backbone.

## Research Questions

- How should information flow between listening and speaking channels?
- Can a dual-channel model learn interruption and backchannel timing without explicit rules?
- How should retrieval or tool calls be scheduled when the model is listening and speaking at the same time?
- What evaluation setup measures whether the assistant uses both channels effectively?

## Related Pages

- [[topics/full-duplex-voice-assistants]]
- [[methods/time-multiplexing-full-duplex-models]]
- [[topics/spoken-language-models]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
