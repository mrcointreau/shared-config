---
layout: two-cols-header
---

# CI Workflow

::left::

### Purpose

Lint, test, build, and audit in a single job.

### Inputs

- `project-type`: `node` or `python`
- `node-version`: default `22`
- `audit-level`: `low|moderate|high|critical`
- `skip-*`: lint, test, build, audit

### Overrides

- `lint-command`, `test-command`, `build-command`
- `pre-test-script` for setup tasks
- `working-directory` for monorepos

::right::

```yaml
jobs:
  ci:
    uses: mrcointreau/shared-config/.github/workflows/ci.yml@main
    with:
      project-type: node  # or python
      node-version: "22"
      audit-level: "moderate"
      skip-lint: false
      skip-test: false
      skip-build: false
      skip-audit: false
    secrets:
      NPM_TOKEN: ${{ secrets.NPM_TOKEN }}  # for private packages
```

<div>

**Outputs:** `audit-outcome`, `lint-outcome`, `test-outcome`, `build-outcome`

</div>

<!--
The real selling point here is flexibility. Skip flags, custom commands, and working-directory support mean you're never locked in. I know the biggest concern with shared workflows is "what if my project is different?"—these overrides address that directly. Let me show you how it flows internally when you call this workflow.
-->
