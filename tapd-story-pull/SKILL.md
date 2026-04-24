---
name: tapd-story-pull
description: Use when the user wants to pull a TAPD story down to a local Markdown file with the tapd CLI.
---

# TAPD Story Pull

Pull a TAPD story to local Markdown.

## When to use

- The user provides a TAPD story ID
- The user asks to pull, download, or sync a story from TAPD to local files

## Steps

1. Get the TAPD story ID.
2. Run:

```bash
tapd story pull <story-id>
```

3. If the user wants a specific file path:

```bash
tapd story pull <story-id> <output-file>
```

4. Verify:
   - the Markdown file is created
   - images are downloaded into `assets/`

## Notes

- The CLI converts TAPD HTML into Markdown
- Image links are rewritten to local relative paths
