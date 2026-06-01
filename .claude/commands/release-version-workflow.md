---
name: release-version-workflow
description: Workflow command scaffold for release-version-workflow in antigravity-awesome-skills.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /release-version-workflow

Use this workflow when working on **release-version-workflow** in `antigravity-awesome-skills`.

## Goal

Prepares, documents, and finalizes a new release, updating changelogs, metadata, and syncing lockfiles.

## Common Files

- `CHANGELOG.md`
- `README.md`
- `docs/users/getting-started.md`
- `docs/users/walkthrough.md`
- `docs/maintainers/security-findings-triage-*.md`
- `package.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update CHANGELOG.md with new version notes
- Update README.md with release messaging and acknowledgements
- Update docs/users/getting-started.md and related user docs
- Update package.json version
- Update package-lock.json to sync lockfile version

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.