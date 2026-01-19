---
layout: two-cols-header
---

# PR Workflow

::left::

### Purpose

Run CI and enforce Conventional Commits.

### Inputs

- `project-type`: `node` or `python`
- `run-commit-lint`: default `true`

### Notes

- Requires `fetch-depth: 0`
- Validates commits from `base..head`

::right::

```yaml
jobs:
  pr:
    uses: mrcointreau/shared-config/.github/workflows/pr.yml@main
    with:
      project-type: node
      run-commit-lint: true  # default
```

<div>

**Allowed types:** `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`

</div>

<!--
The PR workflow combines CI with commit linting. Conventional Commits gate merges and enable automated changelogs and semantic versioning. If commits don't follow the convention, semantic-release can't determine version bumps—catching this early prevents release failures. Here's the parallel execution flow; CI and commitlint run simultaneously for faster feedback.
-->
