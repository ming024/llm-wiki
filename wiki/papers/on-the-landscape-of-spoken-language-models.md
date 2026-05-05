---
title: "On The Landscape of Spoken Language Models: A Comprehensive Survey"
type: paper
status: active
created: 2026-05-04
updated: 2026-05-04
tags: [spoken-language-models, speech-language-models, voice-assistants, full-duplex, survey]
sources:
  - raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md
---

# On The Landscape of Spoken Language Models: A Comprehensive Survey

## Citation

Siddhant Arora, Kai-Wei Chang, Chung-Ming Chien, Yifan Peng, Haibin Wu, Yossi Adi, Emmanuel Dupoux, Hung-Yi Lee, Karen Livescu, and Shinji Watanabe. "On The Landscape of Spoken Language Models: A Comprehensive Survey." Transactions on Machine Learning Research, 2025.

## Why This Matters Here

This is a core pivot reference for the wiki's speech language model and voice assistant research area. It is especially relevant for work on improving the general intelligence of speech assistants, including full-duplex speech language models, text injection, RL-based tool use, and retrieval-augmented generation.

The paper is also personally central to the research context: it is authored by the wiki owner, advisor Karen Livescu, collaborators from CMU including Shinji Watanabe, NTU collaborators including Hung-Yi Lee, and other collaborators.

## Core Contribution

The survey gives a unifying map of spoken language models (SLMs), a field where terminology and evaluation settings are fragmented. It categorizes SLMs by architecture, components, training choices, evaluation methods, and open challenges.

The paper frames SLMs as steps toward universal speech processing systems: systems that can handle spoken input and output, address arbitrary spoken language tasks, and take natural language prompts or instructions rather than only task specifiers or soft prompts.

## Key Taxonomy

The paper distinguishes three major SLM families:

- Pure speech LMs model speech token sequences directly, often using tokenized speech and next-token prediction.
- Speech-aware text LMs combine speech encoders with text LMs, typically producing text conditioned on speech and text input.
- Speech+text LMs model speech and text jointly and may generate both modalities.

This taxonomy should be used as a default organizing lens when ingesting future papers on SLMs, voice assistants, audio LMs, and speech-capable foundation models.

## Important Technical Axes

- Hierarchical token generation: strategies for generating multiple token granularities, including coarse-to-fine generation, interleaving, temporal-plus-depth generation, and delay patterns.
- Text and speech hybrid generation: methods that use text tokens to improve generated speech factuality and linguistic quality while handling length and synchronization mismatches between text and speech tokens.
- Training strategies: pre-training, conditional pre-training, speech-text alignment, instruction tuning, chat SLM training, progressive fine-tuning, experience replay, and preference optimization.
- Duplex speech dialogue: dual-channel and time-multiplexing approaches for listening and speaking simultaneously or near-simultaneously.
- Evaluation: likelihood-based metrics, generative metrics, interactivity, trustworthiness, and task benchmarks such as Dynamic-SUPERB, AIR-Bench, AudioBench, VoiceBench, and MMAU.

## Open Problems

- The best speech representation for SLMs is still unsettled.
- Speech-text combination methods lack controlled comparison.
- Many SLMs are too large or slow for real-time, on-device, or low-latency assistants.
- Public high-quality instruction and chat-style spoken data is scarce.
- Evaluation remains fragmented, especially for speech generation, latency, turn-taking, and conversational behavior.
- Few SLMs are fully open across code, checkpoints, and training data.
- Inclusiveness and safety need speech-specific treatment, including language/dialect coverage, medical speech, speaker/style bias, deepfakes, and trustworthiness.

## Wiki Connections

- [[topics/spoken-language-models]]
- [[topics/pure-speech-language-models]]
- [[topics/speech-aware-text-language-models]]
- [[topics/speech-text-language-models]]
- [[topics/full-duplex-voice-assistants]]
- [[methods/slm-generation-and-training-strategies]]
- [[methods/hierarchical-token-generation]]
- [[methods/text-speech-hybrid-generation]]
- [[methods/dual-channel-full-duplex-models]]
- [[methods/time-multiplexing-full-duplex-models]]

## Sources

- `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
