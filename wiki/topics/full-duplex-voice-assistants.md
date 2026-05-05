---
title: "Full-Duplex Voice Assistants"
type: topic
status: active
created: 2026-05-04
updated: 2026-05-04
tags: [voice-assistants, full-duplex, spoken-language-models, dialogue]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# Full-Duplex Voice Assistants

## Scope

Full-duplex voice assistants can listen and speak in overlapping time, rather than forcing a strict user-turn then assistant-turn interaction. This topic is central for research on natural speech assistants because real spoken dialogue includes interruptions, backchannels, pauses, laughter, turn-taking uncertainty, and simultaneous listening/speaking behavior.

## Why Full-Duplex Matters

Text dialogue is naturally turn-based, but speech dialogue is not. A voice assistant must decide when to begin speaking, when to continue listening, how to backchannel, how to recover from interruption, and how to adapt while it is already generating speech.

For intelligent assistants, full-duplex behavior is not only a speech synthesis problem. It affects reasoning, retrieval timing, tool-use timing, latency, interruption handling, user intent tracking, and whether the assistant feels collaborative.

## Main Modeling Approaches

The SLM survey highlights two major approaches:

- [[methods/dual-channel-full-duplex-models]] maintain separate listening and speaking channels. This lets the model receive user input while tracking its own output, but often requires specialized architecture.
- [[methods/time-multiplexing-full-duplex-models]] use one channel and switch between listening and speaking modes. This can preserve compatibility with decoder-only LLM-style backbones, but makes mode-switching policy central.

In time-multiplexing approaches, switching may be fixed by time slices or controlled by learned tokens such as speak/listen markers. Learned switching is especially relevant for interruption handling.

## Research Questions

- How should a voice assistant decide when to retrieve, reason, call tools, speak, or keep listening?
- Can RL train better speaking/listening policies than supervised turn-taking data alone?
- How can text injection and RAG be inserted without creating awkward latency or stale responses?
- What is the right evaluation protocol for interruption handling, backchanneling, latency, and conversational smoothness?
- How should full-duplex systems balance semantic intelligence with acoustic and social timing?

## Related Pages

- [[topics/spoken-language-models]]
- [[methods/dual-channel-full-duplex-models]]
- [[methods/time-multiplexing-full-duplex-models]]
- [[methods/slm-generation-and-training-strategies]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
