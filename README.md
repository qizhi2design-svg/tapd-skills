# TAPD Skills

This directory is structured so it can be published as a standalone skills repository.

## Layout

```text
skills/
  README.md
  index.json
  tapd-login/
    SKILL.md
  tapd-story-create/
    SKILL.md
  tapd-story-pull/
    SKILL.md
  tapd-story-sync/
    SKILL.md
```

## Included skills

- `tapd-login`: log in to the local TAPD CLI or clear local credentials
- `tapd-story-create`: create a TAPD story from local Markdown
- `tapd-story-pull`: pull a TAPD story to local Markdown
- `tapd-story-sync`: sync a local Markdown story back to TAPD

## Install intent

This directory is designed to be scanned by installers that look for:

```text
skills/*/SKILL.md
```

If you later split this into a standalone GitHub repository, keep this structure unchanged.
