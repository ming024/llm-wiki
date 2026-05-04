---
name: llm-wiki-query
description: Answer research questions against the LLM Wiki by consulting the index, reading relevant pages, citing sources, and optionally filing durable answers back into the wiki. Use when the user asks questions about the wiki, requests comparisons, syntheses, literature summaries, topic reminders, or research brainstorming based on existing wiki knowledge.
---

# LLM Wiki Query

## Required Context

Before answering, read `AGENTS.md` and `wiki/index.md`. Read `wiki/log.md` when recent activity may matter.

## Workflow

1. Use `wiki/index.md` to identify relevant paper, topic, synthesis, idea, method, tool, experiment, project, entity, or source pages.
2. Read the most relevant wiki pages before consulting raw sources.
3. Consult raw files only when the wiki is incomplete or a precise citation needs checking.
4. Answer with citations to wiki pages and source paths.
5. Choose the answer format that fits the question: prose, comparison table, structured markdown page, slide outline, slide deck (Marp), chart (matplotlib), canvas, or another durable artifact.
6. If the answer adds lasting value, ask whether to file it, or file it directly when the user requested a maintained wiki update.
7. If filed, update the relevant wiki page, `wiki/index.md`, and append a `query` entry to `wiki/log.md`.

## Output

Lead with the answer. Then list cited pages or sources, durable wiki updates made, and any remaining uncertainty.
