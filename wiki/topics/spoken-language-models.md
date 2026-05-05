---
title: "Spoken Language Models"
type: topic
status: active
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, speech-language-models, voice-assistants]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Spoken Language Models

## Scope

Spoken language models (SLMs) are speech-capable language models that move beyond task-specific speech systems toward more general speech processing systems. In this wiki, SLMs are a core research area because they connect directly to intelligent voice assistants, full-duplex interaction, tool use, retrieval augmentation, and speech-first agent behavior.

## Working Taxonomy

Use the taxonomy from [[papers/on-the-landscape-of-spoken-language-models]] as the default map:

- [[topics/pure-speech-language-models]]: models of speech token distributions, often trained on tokenized speech with next-token prediction.
- [[topics/speech-aware-text-language-models]]: text LMs augmented with speech encoders, usually producing text conditioned on speech and instructions.
- [[topics/speech-text-language-models]]: models that jointly represent or generate speech and text.

## Research Threads

- How to improve the general intelligence of speech assistants rather than only task-specific ASR, TTS, or spoken QA performance.
- How to combine speech and text representations without losing paralinguistic information such as prosody, emotion, speaker traits, timing, and interruptions.
- How to use text injection, retrieval-augmented generation, and tool use in speech-first assistants.
- How to evaluate SLMs across semantics, acoustics, interaction, latency, trustworthiness, and assistant usefulness.

## Open Questions

- Which SLM family is the best foundation for general-purpose voice assistants?
- When is a cascaded ASR -> LLM -> TTS system sufficient, and when does an end-to-end SLM matter?
- Which benchmarks predict real voice assistant quality?
- How should SLMs expose or consume tool calls, retrieved context, and external memory?
- How do RL-based tool use and preference optimization change speech assistant behavior compared with text-only agents?

## Related Pages

- [[papers/on-the-landscape-of-spoken-language-models]]
- [[topics/pure-speech-language-models]]
- [[topics/speech-aware-text-language-models]]
- [[topics/speech-text-language-models]]
- [[topics/full-duplex-voice-assistants]]
- [[methods/slm-generation-and-training-strategies]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
