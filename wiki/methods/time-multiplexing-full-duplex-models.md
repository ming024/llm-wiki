---
title: "Time-Multiplexing Full-Duplex Models"
type: method
status: seed
created: 2026-05-04
updated: 2026-05-04
tags: [full-duplex, voice-assistants, spoken-language-models, turn-taking]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Time-Multiplexing Full-Duplex Models

## Definition

Time-multiplexing full-duplex models use one channel and switch between listening and speaking modes. The switch can be fixed by time slices or learned through special control tokens such as speak/listen markers.

## Why It Matters

Time multiplexing can preserve compatibility with decoder-only LLM-style backbones, making it attractive for voice assistants that want to reuse text LLM reasoning and instruction-following. The central challenge is the speaking/listening policy: when to start, continue, pause, interrupt, retrieve, call tools, or return to listening.

This approach is closely tied to assistant intelligence because mode-switching decisions affect latency, conversational naturalness, tool-use timing, and whether the model can adapt while the user continues speaking.

## Research Questions

- Should switching be fixed, learned, or controlled by a separate policy?
- Can RL improve speak/listen decisions compared with supervised turn-taking data?
- How should retrieval, text injection, and tool calls fit into the listening/speaking schedule?
- How should interruption handling be evaluated when users continue speaking during assistant output?

## Related Pages

- [[topics/full-duplex-voice-assistants]]
- [[methods/dual-channel-full-duplex-models]]
- [[topics/spoken-language-models]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
