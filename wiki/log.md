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
