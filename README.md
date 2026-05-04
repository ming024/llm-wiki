# LLM Wiki

A standalone research knowledge base maintained with help from LLM agents.

This vault follows the LLM Wiki pattern: raw sources stay immutable, while the agent builds and maintains a structured markdown wiki from them. The wiki should become more useful over time as sources are ingested, questions are answered, contradictions are tracked, and syntheses are filed back into the knowledge base.

## Structure

```text
raw/
  inbox/       # Unprocessed source drops.
  papers/      # Paper PDFs, paper markdown, citation exports, and supplements.
  web/         # Web clips, blog posts, documentation, and articles.
  notes/       # Raw personal notes, meeting notes, and scratch notes.
  experiments/ # Raw experiment logs, outputs, screenshots, and result files.
  assets/      # Images, attachments, and other supporting files.
wiki/
  index.md     # Content-oriented catalog of wiki pages.
  log.md       # Chronological record of ingests, queries, and lint passes.
  overview.md
  papers/      # Structured paper digests.
  topics/      # Living research topic hubs.
  syntheses/   # Cross-source analyses, comparisons, and surveys.
  ideas/       # Research ideas, hypotheses, and brainstorms.
  methods/     # Algorithms, techniques, protocols, and evaluation methods.
  tools/       # Libraries, frameworks, systems, and usage notes.
  experiments/ # Interpreted experiment records.
  projects/    # Concrete research efforts and project threads.
  entities/    # Named things such as people, labs, datasets, benchmarks, and models.
  sources/     # General source summaries that are not paper digests.
```

## Getting Started

Start from `wiki/index.md` to see what the wiki already knows, and use `wiki/log.md` to understand recent ingests, queries, and maintenance. Future agents should read `AGENTS.md` before changing the vault.

### 1. Set Up Google Drive Storage

Install `rclone`:

```sh
brew install rclone
```

Configure a Google Drive remote:

```sh
rclone config
```

In the interactive setup:

1. Choose `n` for a new remote.
2. Name it `gdrive`.
3. Choose the Google Drive storage provider.
4. Follow the browser login flow to finish the setup.

Verify the setup:

```sh
scripts/drive-source-check
```

The check creates the `LLM-Wiki` folder in Google Drive if it is missing.

### 2. Use The Skills

This repo includes three project skills under `.cursor/skills/`. You do not need to run them directly; ask the agent in natural language and Cursor will make the relevant skill available.

Use the ingest skill when adding a source:

```text
Ingest raw/papers/paper.source.md into the wiki.
```

Use the query skill when asking research questions:

```text
What does the wiki currently say about evaluation methods?
Compare the papers we have on agent memory.
File this answer as a durable synthesis if it is useful.
```

Use the lint skill for maintenance:

```text
Lint the wiki for stale claims, missing citations, orphan pages, and missing cross-links.
Review unintegrated source summaries and suggest topic pages to update.
```

When a source is ingested or a durable answer is filed, the agent should update `wiki/index.md` and append an entry to `wiki/log.md`.

# External Source Storage

Large source files can live in Google Drive instead of Git. Use `rclone` with a Google Drive remote, keep downloaded working copies under `_external/`, and commit small `*.source.md` pointer files under the appropriate `raw/` category.

Default configuration:

```sh
export LLM_WIKI_RCLONE_REMOTE=gdrive
export LLM_WIKI_DRIVE_ROOT=LLM-Wiki
```

Common commands:

```sh
scripts/drive-source-check
scripts/drive-source-upload raw/papers ./paper.pdf "Paper Title"
scripts/drive-source-fetch raw/papers/paper.source.md
```

The pointer file records the Drive path, original filename, size, and SHA-256 checksum. The downloaded blob remains ignored by Git.

## Agent Instructions

Future LLM agents should read `AGENTS.md` before modifying this vault.
