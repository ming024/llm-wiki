---
title: "Google Drive Source Storage"
type: tool
status: active
created: 2026-05-04
updated: 2026-05-04
tags: [storage, google-drive, rclone, sources]
sources: []
---

# Google Drive Source Storage

This workflow keeps large source blobs out of Git while preserving durable, readable source references in the repository.

## Model

- Google Drive stores the large source file.
- `_external/` stores ignored local working copies fetched on demand.
- `raw/**/*.source.md` stores committed sidecar pointers with Drive path, size, checksum, and retrieval instructions.
- Wiki pages cite the committed pointer file, not `_external/`.

Example layout:

```text
raw/papers/example-paper.source.md
_external/raw/papers/example-paper.pdf
Google Drive/LLM-Wiki/raw/papers/example-paper.pdf
```

## Configuration

Install and configure `rclone` with a Google Drive remote. The scripts use these environment variables:

```sh
export LLM_WIKI_RCLONE_REMOTE=gdrive
export LLM_WIKI_DRIVE_ROOT=LLM-Wiki
```

If the variables are unset, the scripts use `gdrive` and `LLM-Wiki` as defaults.

## Commands

Check the local setup:

```sh
scripts/drive-source-check
```

Upload a source and create a pointer:

```sh
scripts/drive-source-upload raw/papers ./paper.pdf "Paper Title"
```

Fetch a local working copy from a pointer:

```sh
scripts/drive-source-fetch raw/papers/paper.source.md
```

## Pointer Format

Each pointer is a small markdown file with YAML frontmatter:

```markdown
---
title: "Example Paper"
type: external-source
storage: google-drive
remote: gdrive
remote_path: llm-wiki/raw/papers/example-paper.pdf
original_filename: example-paper.pdf
content_type: application/pdf
sha256: "..."
size_bytes: 123456
added: 2026-05-04
---

# Example Paper

Source file is stored externally in Google Drive. Use `scripts/drive-source-fetch` to restore a local working copy when needed.
```

## Notes

- Do not commit downloaded source blobs from `_external/`.
- Do not commit rclone credentials or local machine configuration.
- Preserve pointer files as raw source references once they have been cited by wiki pages.
