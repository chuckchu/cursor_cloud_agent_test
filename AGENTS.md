# AGENTS.md

Guidance for AI agents working in this repository.

## Repository purpose

`cursor_cloud_agent_test` is a minimal GitHub repository used to exercise Cursor Cloud Agent workflows. It contains no application source code, package manifests, containers, or CI configuration.

## Cursor Cloud specific instructions

### Services

| Service | Required? | Notes |
|---------|-----------|--------|
| *(none)* | No | There is no app server, database, or background worker in this repo. |

### Dependency install

No install step is required. The VM update script is a no-op (`true`).

### Lint / test / build

Not applicable until application code is added (no `package.json`, `pyproject.toml`, `Makefile`, etc.).

### Running the “application”

There is no runnable product. Verification for agents is limited to:

- `git status` — working tree and branch
- `cat README.md` — repo identity

### VM toolchain (for future code)

The Cloud Agent VM typically provides Node.js (via nvm), pnpm, npm, Python 3.12, and Git. Use the stack that matches files you add to the repo.

### Secrets

No application secrets are defined in-repo. Git push uses the environment-injected `origin` remote token.
