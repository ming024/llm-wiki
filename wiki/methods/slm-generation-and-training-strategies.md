---
title: "SLM Generation And Training Strategies"
type: method
status: active
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, training, generation, speech-tokenization]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# SLM Generation And Training Strategies

## Purpose

This page tracks recurring design methods for spoken language models, especially those that affect intelligent voice assistants and full-duplex systems.

## Hierarchical Token Generation

See [[methods/hierarchical-token-generation]] for strategies such as coarse-to-fine generation, interleaving, temporal-plus-depth generation, and delay patterns.

## Text And Speech Hybrid Generation

See [[methods/text-speech-hybrid-generation]] for approaches that combine text tokens and speech tokens to improve factuality, linguistic quality, and spoken output generation.

## Training Strategies

The survey organizes training into pre-training and post-training:

Pre-training covers objectives that build general speech, text, or speech-text modeling capacity before the model is explicitly optimized for broad downstream assistant behavior. Common forms include:

- Pure speech modeling: tokenize speech and train a model of speech token sequences, often with next-token prediction.
- Joint speech-text modeling: train on aligned speech and text to model their joint distribution, either by interleaving modalities or using multi-channel representations.
- Continual pre-training from text LMs: start from a text LM and continue training on speech or speech-text data to adapt the model to the speech modality.
- Conditional speech-to-text pre-training: initialize from models such as ASR, speech translation, or Whisper-like systems that already align speech to text.
- Speech-text alignment: train adapters or representations so speech inputs can be consumed by a text LM or shared sequence model.

Post-training covers objectives that make the model useful for tasks, instructions, dialogue, and assistant behavior. Common forms include:

- Task-specific training: fine-tune on a predefined set of speech tasks, often with task specifiers.
- Instruction tuning: convert speech tasks into natural-language instructions so the model learns to follow spoken or written prompts.
- Chat SLM training: train on conversational speech or speech-converted dialogue data so the model behaves like an interactive assistant.
- Progressive fine-tuning: start with content-heavy tasks such as ASR, then move toward tasks involving semantics, paralinguistics, or composed instructions.
- Experience replay: mix pre-training data into post-training to reduce catastrophic forgetting of text reasoning or speech generation skills.
- Preference optimization: optimize outputs with human or AI feedback, potentially extending RLHF-style methods to speech quality, helpfulness, turn-taking, and interaction.

For the wiki's voice assistant focus, the most important unresolved question is how these training strategies affect general assistant intelligence, tool-use reliability, retrieval use, turn-taking, interruption handling, and spoken social behavior.

## Open Questions

- Which token generation strategy best supports low-latency full-duplex assistants?
- How should speech token generation interact with text-side reasoning, retrieved context, and tool calls?
- Can preference optimization or RL improve speaking/listening policy rather than only answer quality?
- How should training preserve text LLM reasoning while adding speech input/output?

## Related Pages

- [[topics/spoken-language-models]]
- [[topics/full-duplex-voice-assistants]]
- [[methods/hierarchical-token-generation]]
- [[methods/text-speech-hybrid-generation]]
- [[papers/on-the-landscape-of-spoken-language-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
