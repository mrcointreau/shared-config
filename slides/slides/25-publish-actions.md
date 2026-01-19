---
layout: two-cols-header
---

# Publish Actions

::left::

### Purpose

Republish a specific version without a full release.

### Inputs

- `version`: tag without the `v` prefix
- `use-oidc` or `npm-token`
- Optional: `dist-directory`, `working-directory`

### Notes

Used for recovery and manual publishes.

::right::

```yaml
- uses: mrcointreau/shared-config/actions/publish/node@main
  with:
    version: "1.2.3"
    use-oidc: true
    # OR
    npm-token: ${{ secrets.NPM_TOKEN }}
```

<!--
These are standalone publish actions for recovery scenarios. The version input expects the tag without the "v" prefix. Prefer OIDC over tokens for new projects—it means no secrets to rotate, plus you get signed provenance attestations that prove where the package came from. Finally, let's look at the utility actions that support all the workflows.
-->
