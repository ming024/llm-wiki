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

## Basic Workflow

1. Add source material to the appropriate folder under `raw/`, or start with `raw/inbox/`.
2. Ask an LLM agent to ingest the source.
3. Review the generated or updated wiki pages.
4. Ask research questions against the wiki.
5. File valuable answers into the relevant topic, project, idea, experiment, or synthesis page.
6. Periodically ask the agent to lint the wiki for stale claims, missing links, orphan pages, and contradictions.

## Agent Instructions

Future LLM agents should read `AGENTS.md` before modifying this vault.
