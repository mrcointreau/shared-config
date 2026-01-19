---
layout: two-cols-header
---

# Standalone Publish Workflow

::left::

### Purpose

Republish a specific version without a full release.

### Inputs

- `project-type`: `node` or `python`
- `version`: tag without the `v` prefix
- `use-oidc`: recommended

### Notes

Use for recovery or one-off publishing.

::right::

```yaml
uses: mrcointreau/shared-config/.github/workflows/publish.yml@main
with:
  project-type: node
  version: "1.2.3"      # republish specific version
  use-oidc: true
```

<!--
This is a recovery workflow for republishing a specific version without running semantic-release again. If npm publish times out but the Git tag was created, you don't want to bump version again—this publishes the existing tag's code instead. Here's the flow showing how it checks out by tag and publishes with your preferred auth method.
-->
