# How to use this knowledge store

This repository is a Giterloper knowledge store for end-to-end tests.

Knowledge lives under `knowledge/`.

Required store contract:

- `CONSTITUTION.md` — the normative operation contract
- `CONSTITUTION.md5` — checksum file for the contract
- `INSTRUCTIONS.md` — these usage instructions
- `README.md` — a short project description
- `knowledge/` — markdown content consumed by QMD indexing

## Local usage

In the project using this store, state lives under `.giterloper/`:

- `.giterloper/pinned.yaml` (committed): `name: source@sha`
- `.giterloper/versions/` (ignored): pinned store clones
- `.giterloper/staged/` (ignored): temporary working clones

Pins must use full 40-character commit SHAs.

## Branch and versioning

The default branch is `main`.
The current version for production use is tracked by a pinned SHA in the consuming project.

## Operations supported by the gl CLI

- `gl pin add <name> <source> [--ref <ref>]`
- `gl setup <name> <source> [--ref <ref>]`
- `gl stage <branch> [--pin <name>]`
- `gl promote <branch> [--pin <name>]`
- `gl stage-cleanup <branch> [--pin <name>]`
- `gl search <query> [--pin <name>]`
- `gl query <question> [--pin <name>]`
- `gl get <path> [--pin <name>]`
- `gl verify [--pin <name>]`
- `gl teardown <name>`

## Notes

- Only markdown files in `knowledge/` are indexed.
- Tests and agents should use this repository only for controlled local validation.
