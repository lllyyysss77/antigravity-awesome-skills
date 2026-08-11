---
name: add-or-update-skill-metadata
description: Workflow command scaffold for add-or-update-skill-metadata in antigravity-awesome-skills.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-skill-metadata

Use this workflow when working on **add-or-update-skill-metadata** in `antigravity-awesome-skills`.

## Goal

Adds a new skill or updates metadata for an existing skill, ensuring SKILL.md files are correct and complete.

## Common Files

- `skills/*/SKILL.md`
- `skills/*/references/*.md`
- `skills/*/scripts/*.py`
- `skills_index.json`
- `CATALOG.md`
- `tools/scripts/fix_missing_skill_metadata.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update skills/<skill-name>/SKILL.md
- Optionally add or update reference files in skills/<skill-name>/references/
- Optionally add or update scripts in skills/<skill-name>/scripts/
- Optionally update skills_index.json and/or CATALOG.md via registry sync
- Optionally run or update metadata fixer scripts

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.