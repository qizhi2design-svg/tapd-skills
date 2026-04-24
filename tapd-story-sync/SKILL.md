---
name: tapd-story-sync
description: Use when the user wants to sync a local Markdown story back to TAPD with the tapd CLI, including updates to an existing story.
---

# TAPD Story Sync

Sync a local Markdown story to TAPD.

## When to use

- The user says sync, update, push changes, or resubmit a story
- The Markdown file already has `tapd_id`
- The goal is to keep TAPD and local Markdown aligned

## Steps

1. Read the Markdown file.
2. Confirm `tapd_id` exists in frontmatter.
3. Run:

```bash
tapd story update <markdown-file>
```

4. Verify:
   - the update succeeds
   - `updated_at` is written back locally

## Notes

- The CLI will auto-create a new story if the old `tapd_id` no longer exists in TAPD
- Local images and Mermaid blocks are handled during sync
