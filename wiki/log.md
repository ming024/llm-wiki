---
title: "Log"
type: overview
status: active
created: 2026-05-02
updated: 2026-05-04
tags: [log]
sources: []
---

# Log

Chronological record of wiki ingests, queries, lint passes, and maintenance.

## [2026-05-02] maintenance | Initial scaffold

- Source: none
- Updated: `README.md`, `AGENTS.md`, `wiki/index.md`, `wiki/log.md`, `wiki/overview.md`
- Notes: Created the initial LLM Wiki scaffold for mixed research materials.

## [2026-05-02] maintenance | Research structure revision

- Source: none
- Updated: `README.md`, `AGENTS.md`, `wiki/index.md`, `wiki/overview.md`
- Notes: Revised the vault structure for paper digestion, research topics, syntheses, ideas, methods, tools, experiments, projects, entities, and classified raw sources.

## [2026-05-04] maintenance | Google Drive source storage

- Source: none
- Updated: `README.md`, `AGENTS.md`, `wiki/tools/google-drive-source-storage.md`, `wiki/index.md`, `wiki/log.md`
- Notes: Added an `rclone`-based workflow for storing large source blobs in Google Drive while tracking sidecar pointers in `raw/`.

## [2026-05-04] maintenance | Automatic source intake

- Source: none
- Updated: `.cursor/skills/llm-wiki-ingest/SKILL.md`, `scripts/drive-source-intake`, `README.md`, `AGENTS.md`, `wiki/tools/google-drive-source-storage.md`, `wiki/log.md`
- Notes: Added agent-driven intake for arbitrary local paths and URLs with automatic sidecar creation.

## [2026-05-04] maintenance | Raw file storage policy

- Source: none
- Updated: `scripts/drive-source-intake`, `.cursor/skills/llm-wiki-ingest/SKILL.md`, `README.md`, `AGENTS.md`, `wiki/tools/google-drive-source-storage.md`, `wiki/log.md`
- Notes: Added a type-and-size policy so small text-like files stay directly in `raw/` while large or binary files use Drive-backed sidecars.

## [2026-05-04] maintenance | Ingest checkpoint requirement

- Source: none
- Updated: `.cursor/skills/llm-wiki-ingest/SKILL.md`, `AGENTS.md`, `wiki/log.md`
- Notes: Made the human discussion checkpoint mandatory before durable wiki edits during source ingest.

## [2026-05-04] ingest | On The Landscape of Spoken Language Models

- Source: `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
- Updated: `wiki/papers/on-the-landscape-of-spoken-language-models.md`, `wiki/topics/spoken-language-models.md`, `wiki/topics/full-duplex-voice-assistants.md`, `wiki/methods/slm-generation-and-training-strategies.md`, `wiki/index.md`, `wiki/log.md`
- Notes: Ingested the SLM survey as a core pivot reference for spoken language models, full-duplex voice assistants, generation/training strategies, and voice assistant intelligence.

## [2026-05-04] maintenance | SLM taxonomy topic split

- Source: `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
- Updated: `wiki/topics/spoken-language-models.md`, `wiki/topics/pure-speech-language-models.md`, `wiki/topics/speech-aware-text-language-models.md`, `wiki/topics/speech-text-language-models.md`, `wiki/index.md`, `wiki/log.md`
- Notes: Split the three main SLM families into dedicated topic pages for future paper ingestion and synthesis.

## [2026-05-04] maintenance | Full-duplex modeling topic split

- Source: `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
- Updated: `wiki/topics/full-duplex-voice-assistants.md`, `wiki/topics/dual-channel-full-duplex-models.md`, `wiki/topics/time-multiplexing-full-duplex-models.md`, `wiki/index.md`, `wiki/log.md`
- Notes: Split dual-channel and time-multiplexing full-duplex approaches into dedicated topic pages.

## [2026-05-04] maintenance | Full-duplex methods reclassification

- Source: `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
- Updated: `wiki/topics/full-duplex-voice-assistants.md`, `wiki/methods/dual-channel-full-duplex-models.md`, `wiki/methods/time-multiplexing-full-duplex-models.md`, `wiki/index.md`, `wiki/log.md`
- Notes: Reclassified dual-channel and time-multiplexing full-duplex approaches from topics to methods.

## [2026-05-04] maintenance | SLM generation method split

- Source: `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
- Updated: `wiki/methods/slm-generation-and-training-strategies.md`, `wiki/methods/hierarchical-token-generation.md`, `wiki/methods/text-speech-hybrid-generation.md`, `wiki/index.md`, `wiki/log.md`
- Notes: Split hierarchical token generation and text-speech hybrid generation into dedicated method pages.

## [2026-05-04] lint | SLM survey cleanup

- Source: `raw/papers/on-the-landscape-of-spoken-language-models-a-comprehensive-survey.source.md`
- Updated: `wiki/papers/on-the-landscape-of-spoken-language-models.md`, `wiki/log.md`
- Notes: Removed duplicate paper digest content, fixed stale source references, and added missing pivot links to derived SLM pages.
