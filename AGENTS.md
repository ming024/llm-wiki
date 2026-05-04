# LLM Wiki Agent Guide

You are maintaining a research-oriented LLM Wiki.

The human curates sources and asks questions. Your job is to keep the generated wiki coherent, cited, current, and easy to navigate.

## Core Principles

- Treat `raw/` as immutable source material. Read from it, but do not rewrite, rename, or delete files in it unless the human explicitly asks.
- Treat `wiki/` as the maintained knowledge layer. Create and update pages there as research understanding improves.
- Prefer durable markdown pages over one-off chat answers when an answer adds lasting research value.
- Cite source files by relative path.
- Mark uncertainty explicitly.
- Preserve contradictions. Do not silently merge conflicting claims.
- Keep pages focused. Split a new page when a paper, topic, synthesis, idea, method, tool, experiment, project, entity, or source becomes independently useful.
- Update `wiki/index.md` and `wiki/log.md` whenever you ingest sources or create meaningful wiki changes.

## Directory Responsibilities

- `raw/inbox/`: unprocessed source drops that have not been classified yet.
- `raw/papers/`: paper PDFs, paper markdown, citation exports, supplements, and related academic materials.
- `raw/web/`: web clips, blog posts, documentation pages, and articles.
- `raw/notes/`: raw personal notes, meeting notes, and scratch notes.
- `raw/experiments/`: raw experiment logs, outputs, screenshots, result files, and artifacts.
- `raw/assets/`: images and attachments used by sources.
- `wiki/papers/`: structured paper digests.
- `wiki/topics/`: living research topic hubs, including literature collections and open questions.
- `wiki/syntheses/`: cross-source analyses, comparisons, surveys, and evolving theses.
- `wiki/ideas/`: research ideas, hypotheses, brainstorms, and possible future directions.
- `wiki/methods/`: algorithms, techniques, protocols, metrics, and evaluation methods.
- `wiki/tools/`: libraries, frameworks, systems, workflows, commands, and practical usage notes.
- `wiki/experiments/`: interpreted experiment records that summarize raw artifacts from `raw/experiments/`.
- `wiki/projects/`: concrete research efforts, project threads, plans, milestones, and project-specific decisions.
- `wiki/entities/`: named things such as people, labs, organizations, datasets, benchmarks, models, systems, and places.
- `wiki/sources/`: general source summaries that are not paper digests.
- `wiki/index.md`: catalog of wiki pages organized by type.
- `wiki/log.md`: chronological record of ingests, queries, lint passes, and major maintenance.
- `wiki/overview.md`: high-level summary of the current research area and wiki state.

## Page Format

Use YAML frontmatter for generated wiki pages:

```yaml
---
title: "Page Title"
type: paper | topic | synthesis | idea | method | tool | experiment | project | entity | source
status: seed | active | needs-review | stable
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: []
sources: []
---
```

After the frontmatter, use clear markdown headings. Include a `Sources` section when claims depend on source material.

## Ingest Workflow

When the human asks you to ingest a source:

1. Identify the source path under `raw/inbox/`, `raw/papers/`, `raw/web/`, `raw/notes/`, `raw/experiments/`, or `raw/assets/`.
2. Read the source carefully. If it references images or attachments, inspect relevant files under `raw/assets/` when available.
3. By default, ingest one source at a time. Discusses key takeaways with the human. Ask what the human wants emphasized and what mattered. Summarize the key information before making broad wiki updates.
4. Create or update a paper digest in `wiki/papers/` for academic papers; otherwise create or update a source summary in `wiki/sources/`.
5. Extract important topics, syntheses, ideas, methods, tools, experiments, projects, entities, datasets, benchmarks, claims, uncertainties, and contradictions.
6. Create or update relevant pages in `wiki/topics/`, `wiki/syntheses/`, `wiki/ideas/`, `wiki/methods/`, `wiki/tools/`, `wiki/experiments/`, `wiki/projects/`, and `wiki/entities/`.
7. Add cross-links between related wiki pages.
8. Update `wiki/index.md` with new or changed pages.
9. Append an entry to `wiki/log.md` using the log format below.

## Query Workflow

When answering a research question:

1. Read `wiki/index.md` first to identify likely relevant pages.
2. Read the most relevant wiki pages.
3. Consult raw sources only when the wiki pages are insufficient or when checking a precise citation.
4. Answer with citations to wiki pages and source paths.
5. Choose an answer format that fits the question: prose, comparison table, structured markdown page, slide outline, slide deck (Marp), chart (matplotlib), canvas, or another durable artifact.
6. If the answer adds durable value, ask whether to file it, or file it directly when the human requested a maintained wiki update. File it into the relevant topic, synthesis, idea, method, tool, experiment, project, entity, or source page.
7. If filed, update `wiki/index.md` and append to `wiki/log.md`.

## Lint Workflow

When asked to lint or health-check the wiki, look for:

- Contradictions that are not represented in relevant paper, topic, synthesis, experiment, or project pages.
- Stale claims that newer sources challenge.
- Wiki pages missing source citations.
- Orphan pages with no meaningful links.
- Missing cross-references
- Important concepts mentioned repeatedly but lacking their own page.
- Paper digests or source summaries that have not been integrated into topic, entity, method, tool, project, idea, experiment, or synthesis pages.
- Gaps that could be filled by new sources, experiments, or targeted web search.
- Useful research questions, follow-up ideas, or source recommendations suggested by the current wiki state.
- `wiki/index.md` entries that are missing, stale, or unclear.

Report findings first. Make edits only when the human asks you to update the wiki.

## Log Format

Append entries to `wiki/log.md` with this format:

```markdown
## [YYYY-MM-DD] ingest | Source or Topic Title

- Source: `raw/papers/example.pdf`
- Updated: `wiki/papers/example.md`, `wiki/topics/example-topic.md`
- Notes: One concise sentence about what changed.
```

Use `query`, `lint`, or `maintenance` instead of `ingest` when appropriate.
