---
name: tapd-login
description: Use when the user needs to log in to the local TAPD CLI, set up personal token or app credentials, or clear local TAPD credentials with logout.
---

# TAPD Login

Use this skill when the user needs to set up or clear TAPD authentication for the local CLI.

## When to use

- First-time TAPD CLI setup
- Authentication errors from `tapd`
- The user asks to log in, configure token, bind credentials, or log out

## Steps

1. If the user needs authentication, run:

```bash
tapd login
```

2. If the user already has values, prefer non-interactive form:

```bash
tapd login --mode personal --personal-token <token> --workspace-id <workspace-id>
tapd login --mode app --client-id <id> --client-secret <secret> --company-id <company-id>
```

3. If the user wants to clear local auth, run:

```bash
tapd logout
```

## Notes

- `tapd login` writes credentials to `.tapd/credentials.json`
- Personal-token mode also validates a workspace
- `tapd logout` removes the local credentials file
