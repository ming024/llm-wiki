---
name: llm-wiki-ingest
description: Ingest research sources into the LLM Wiki by reading raw materials, creating paper digests or source summaries, updating related wiki pages, and logging changes. Use when the user asks to ingest, process, summarize, digest, add, or integrate papers, web clips, notes, experiment artifacts, or other sources into the wiki.
---

# LLM Wiki Ingest

## Required Context

Before ingesting, read `AGENTS.md`, `wiki/index.md`, and `wiki/log.md`.

## Source Intake

Ingest requests may start from a committed raw file, a `raw/**/*.source.md` pointer, any local filesystem path, or an `http://` or `https://` URL.

When the source is not already under `raw/`, classify it before ingesting:

- Papers, academic PDFs, citation exports, and supplements -> `raw/papers`
- Articles, documentation, blog posts, and ordinary web URLs -> `raw/web`
- Personal notes, meeting notes, and scratch notes -> `raw/notes`
- Experiment logs, outputs, screenshots, results, and artifacts -> `raw/experiments`
- Images and attachments used by sources -> `raw/assets`
- Unclear or mixed material -> `raw/inbox`

After choosing the category, run:

```sh
scripts/drive-source-intake <raw/category> <path-or-url> [title]
```

When ingesting a URL or a local file with a generic filename, pass a descriptive title when one is available so the generated raw file or pointer has a durable, human-readable name.

Continue from the path reported by intake. If it prints `Raw file:`, cite and read that direct raw file. If it prints `Pointer:`, cite the generated `raw/**/*.source.md` pointer. For ordinary web pages, the pointer may use `storage: url` and should be cited directly. For Drive-backed blobs, fetch the local working copy with `scripts/drive-source-fetch` when the source content must be read.

File storage is type-and-size based. Small text-like files at or below 1 MB are copied directly into `raw/<category>/`. Larger files and binary/heavy formats such as PDFs, images, media, archives, and office documents are uploaded to Google Drive and represented by sidecar pointers. Obvious file URLs are downloaded first, then evaluated with the same policy. Ordinary web pages become `raw/web/*.source.md` URL pointers unless the human asks for a downloaded snapshot.

## Workflow

1. Identify the source under `raw/inbox/`, `raw/papers/`, `raw/web/`, `raw/notes/`, `raw/experiments/`, or `raw/assets/`.
2. If the request started from an outside path or URL, first run the Source Intake workflow above and continue from the reported `Raw file:` or `Pointer:` path.
3. Read the source carefully. Inspect referenced assets when useful.
4. Stop for a human checkpoint before writing or updating wiki pages. Report the source path, source type, key takeaways, likely wiki pages to create or update, and ask what the human wants emphasized or what mattered.
5. Wait for the human response. Do not create or update `wiki/` pages, `wiki/index.md`, or `wiki/log.md` before this response. Discusses key takeaways with the human.
6. After the human responds, summarize the key information. Create or update a paper digest in `wiki/papers/` for academic papers. Use `wiki/sources/` for non-paper source summaries.
7. Update relevant pages in `wiki/topics/`, `wiki/syntheses/`, `wiki/ideas/`, `wiki/methods/`, `wiki/tools/`, `wiki/experiments/`, `wiki/projects/`, and `wiki/entities/`.
8. Add cross-links and source citations using relative paths.
9. Update `wiki/index.md`.
10. Append an `ingest` entry to `wiki/log.md`.

## Human Checkpoint

This checkpoint is mandatory. Source intake and source reading may happen before the checkpoint; durable wiki edits may not. The checkpoint question should be specific to the source, not a generic "anything else?" prompt.

## Output

Report the source processed, pages created or changed, unresolved uncertainties, and any suggested follow-up questions or sources.
