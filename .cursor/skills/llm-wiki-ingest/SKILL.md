---
name: llm-wiki-ingest
description: Ingest research sources into the LLM Wiki by reading raw materials, creating paper digests or source summaries, updating related wiki pages, and logging changes. Use when the user asks to ingest, process, summarize, digest, add, or integrate papers, web clips, notes, experiment artifacts, or other sources into the wiki.
---

# LLM Wiki Ingest

## Required Context

Before ingesting, read `AGENTS.md`, `wiki/index.md`, and `wiki/log.md`.

## Workflow

1. Identify the source under `raw/inbox/`, `raw/papers/`, `raw/web/`, `raw/notes/`, `raw/experiments/`, or `raw/assets/`.
2. Read the source carefully. Inspect referenced assets when useful.
3. Prefer one-source-at-a-time ingest. Discusses key takeaways with the human. Ask what the human wants emphasized and what mattered. Summarize the key information before making broad wiki updates.
4. Create or update a paper digest in `wiki/papers/` for academic papers. Use `wiki/sources/` for non-paper source summaries.
5. Update relevant pages in `wiki/topics/`, `wiki/syntheses/`, `wiki/ideas/`, `wiki/methods/`, `wiki/tools/`, `wiki/experiments/`, `wiki/projects/`, and `wiki/entities/`.
6. Add cross-links and source citations using relative paths.
7. Update `wiki/index.md`.
8. Append an `ingest` entry to `wiki/log.md`.

## Output

Report the source processed, pages created or changed, unresolved uncertainties, and any suggested follow-up questions or sources.
