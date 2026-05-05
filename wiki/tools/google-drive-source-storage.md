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

This workflow keeps large source blobs out of Git while allowing small text-like source files to stay directly in `raw/`.

## Model

- Small text-like files at or below 1 MB can be committed directly in `raw/<category>/`.
- Google Drive stores large files and binary/heavy formats such as PDFs, images, media, archives, and office documents.
- `_external/` stores ignored local working copies fetched on demand.
- `raw/**/*.source.md` stores committed sidecar pointers with Drive path, size, checksum, and retrieval instructions when a file is stored externally.
- Wiki pages cite either the direct raw file or the committed pointer file, not `_external/`.

Example layout:

```text
raw/web/example-article.md
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

Intake a local file or URL:

```sh
scripts/drive-source-intake raw/papers ./paper.pdf "Paper Title"
scripts/drive-source-intake raw/web https://example.com/article "Article Title"
```

For local files and obvious file URLs, intake first applies the raw storage policy. Small text-like files at or below 1 MB are copied directly into `raw/`. Larger or binary/heavy files upload to Google Drive and get a Drive-backed pointer. Ordinary web pages create a `storage: url` pointer under `raw/web` without uploading content to Drive.

Upload a local source directly when you already know it should be Drive-backed:

```sh
scripts/drive-source-upload raw/papers ./paper.pdf "Paper Title"
```

Fetch a local working copy from a pointer:

```sh
scripts/drive-source-fetch raw/papers/paper.source.md
```

## Pointer Format

Drive-backed pointers are small markdown files with YAML frontmatter:

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

Ordinary web URL pointers use `storage: url`:

```markdown
---
title: "Example Article"
type: external-source
storage: url
source_url: "https://example.com/article"
added: "2026-05-04"
---

# Example Article

Source is stored as a URL pointer. Use the `source_url` above when the page content needs to be consulted.
```

## Notes

- Do not commit downloaded source blobs from `_external/`.
- Do not commit rclone credentials or local machine configuration.
- Preserve pointer files as raw source references once they have been cited by wiki pages.
