```markdown
# antigravity-awesome-skills Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill introduces the core development patterns and workflows used in the `antigravity-awesome-skills` repository. The project is primarily written in Python (no major framework detected), but also includes JavaScript/TypeScript for web app and testing components. It emphasizes clear coding conventions, structured commit messages, and a set of collaborative workflows for skill management, release, registry sync, security, and community contributions.

## Coding Conventions

- **File Naming:**  
  Use PascalCase for Python files and skill directories.
  ```
  Example: MyAwesomeSkill.py, DataProcessor.py
  ```

- **Import Style:**  
  Use relative imports within modules.
  ```python
  from .utils import helper_function
  ```

- **Export Style:**  
  Use named exports (i.e., explicitly state what is exported).
  ```python
  __all__ = ['MyClass', 'my_function']
  ```

- **Commit Messages:**  
  Follow [Conventional Commits](https://www.conventionalcommits.org/) with prefixes:
  - `chore`, `fix`, `docs`, `meta`, `feat`
  - Example:  
    ```
    feat: add metadata validation for new skills
    fix: correct import path in DataProcessor
    ```

## Workflows

### Add or Update Skill Metadata
**Trigger:** When you want to add a new skill or update metadata for an existing skill.  
**Command:** `/add-skill`

1. Create or update `skills/<skill-name>/SKILL.md`.
2. Optionally add or update reference files in `skills/<skill-name>/references/`.
3. Optionally add or update scripts in `skills/<skill-name>/scripts/`.
4. Optionally update `skills_index.json` and/or `CATALOG.md` via registry sync.
5. Optionally run or update metadata fixer scripts.

**Example:**
```bash
/add-skill
# Then edit skills/my-new-skill/SKILL.md and add references/scripts as needed
```

---

### Release Version Workflow
**Trigger:** When you want to cut a new release version.  
**Command:** `/release`

1. Update `CHANGELOG.md` with new version notes.
2. Update `README.md` with release messaging and acknowledgements.
3. Update `docs/users/getting-started.md` and related user docs.
4. Update `package.json` version.
5. Update `package-lock.json` to sync lockfile version.
6. Sync generated registry files (`CATALOG.md`, `skills_index.json`, `data/catalog.json`, etc.).
7. Document release in walkthroughs and maintenance docs.

**Example:**
```bash
/release
# Then follow prompts to update changelog and docs
```

---

### Sync Generated Registry Files
**Trigger:** When you add/update skills or metadata and need the registry to reflect the current state.  
**Command:** `/sync-registry`

1. Run scripts to regenerate `CATALOG.md`, `skills_index.json`, `data/catalog.json`, `data/bundles.json`.
2. Update `README.md` with registry sync comment if needed.
3. Commit only generated files with `[ci skip]` if no code changes.

**Example:**
```bash
/sync-registry
# Regenerates and commits registry/catalog files
```

---

### Add or Update GitHub Templates and Community Files
**Trigger:** When you want to improve or add community and contribution documentation.  
**Command:** `/add-template`

1. Add or update files in `.github/ISSUE_TEMPLATE/` and `.github/DISCUSSION_TEMPLATE/`.
2. Update `CONTRIBUTING.md` and/or `CODE_OF_CONDUCT.md`.
3. Update `README.md` to reflect new community links or standards.
4. Optionally update `docs/COMMUNITY_GUIDELINES.md`.

**Example:**
```bash
/add-template
# Then edit or add template/community files as needed
```

---

### Security Hardening and Fix Workflow
**Trigger:** When you want to fix security vulnerabilities or improve security posture.  
**Command:** `/security-fix`

1. Update `package.json` and `package-lock.json` to pin safe dependencies.
2. Update scripts or code paths to remediate vulnerabilities.
3. Add or update regression/security tests in `tools/scripts/tests/` or `apps/web-app/src/__tests__/`.
4. Document changes in security triage or maintenance docs.

**Example:**
```bash
/security-fix
# Then update dependencies, code, and add tests
```

---

### Web App Feature or Bugfix with Tests
**Trigger:** When you add a new feature or fix a bug in the web app.  
**Command:** `/webapp-feature`

1. Update or add implementation files in `apps/web-app/src/`.
2. Update or add tests in `apps/web-app/src/__tests__/` or `apps/web-app/src/pages/__tests__/`.
3. Update public assets or scripts if needed.
4. Optionally update `README.md` or user docs.

**Example:**
```bash
/webapp-feature
# Then implement feature and add corresponding tests
```

---

## Testing Patterns

- **Framework:** [vitest](https://vitest.dev/)
- **Test File Pattern:**  
  JavaScript/TypeScript test files use the `*.test.js` or `*.test.ts` pattern.
  ```
  Example: skills/MyAwesomeSkill/scripts/validate.test.js
  ```

- **Test Example:**
  ```js
  // skills/MyAwesomeSkill/scripts/validate.test.js
  import { validateSkill } from './validate';

  test('validates correct skill metadata', () => {
    expect(validateSkill({ name: 'TestSkill' })).toBe(true);
  });
  ```

## Commands

| Command           | Purpose                                                      |
|-------------------|--------------------------------------------------------------|
| /add-skill        | Add or update a skill and its metadata                       |
| /release          | Prepare and document a new release version                   |
| /sync-registry    | Regenerate and sync registry/catalog files                   |
| /add-template     | Add or update GitHub/community templates and guidelines      |
| /security-fix     | Address security issues and add regression/security tests    |
| /webapp-feature   | Add a new web app feature or fix a bug with appropriate tests|
```
