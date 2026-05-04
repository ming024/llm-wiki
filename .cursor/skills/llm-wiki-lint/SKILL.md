---
name: llm-wiki-lint
description: Health-check the LLM Wiki for contradictions, stale claims, missing citations, orphan pages, missing cross-references, unintegrated source summaries, data gaps, and follow-up research opportunities. Use when the user asks to lint, audit, clean up, check, review, or maintain the wiki.
---

# LLM Wiki Lint

## Required Context

Before linting, read `AGENTS.md`, `wiki/index.md`, and `wiki/log.md`.

## Workflow

1. Check whether important pages are represented in `wiki/index.md`.
2. Look for contradictions across paper, topic, synthesis, experiment, and project pages.
3. Identify stale claims that newer sources or experiment records challenge.
4. Find pages missing source citations or clear links to supporting raw files.
5. Find orphan pages, missing cross-references, and repeated concepts that deserve their own pages.
6. Fix missing cross-references.
7. Check whether paper digests or source summaries have been integrated into topics, entities, methods, tools, projects, ideas, experiments, or syntheses.
8. Identify data gaps that could be filled by new sources, experiments, or targeted web search.
9. Suggest useful research questions, follow-up ideas, and source recommendations.

## Editing Rules

Report findings first. Make edits only when the user asks you to update the wiki.

When edits are made, update `wiki/index.md` and append a `lint` or `maintenance` entry to `wiki/log.md`.

## Output

Order findings by importance. For each finding, include the affected page, the issue, and the recommended fix.
