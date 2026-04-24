---
name: tapd-story-create
description: Use when the user wants to create a new TAPD story from a local Markdown file with the tapd CLI.
---

# TAPD Story Create

Create a TAPD story from a local Markdown file.

## When to use

- The user asks to create a TAPD story
- The user wants to upload a new Markdown requirement to TAPD
- The Markdown file does not yet have `tapd_id`

## Steps

1. Read the target Markdown file.
2. Confirm it is a new story:
   - no `tapd_id` in frontmatter
3. Run:

```bash
tapd story create <markdown-file>
```

4. Verify:
   - the command succeeds
   - `tapd_id` is written back to the file

## Notes

- The CLI supports local images and Mermaid upload
- Missing `iteration_id` or `creator` may trigger interactive selection
