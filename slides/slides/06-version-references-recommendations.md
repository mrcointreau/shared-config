---
layout: two-cols-header
---

# Version References

::left::

| Reference | Example | Behavior |
|-----------|---------|----------|
| **Branch** | `@main` | Always latest commit |
| **Major** | `@v12` | Latest v12.x.x |
| **Exact** | `@v12.0.0` | Pinned forever |

### Recommendations

- **Internal projects**: `@main` — get fixes immediately
- **External/OSS**: `@v12` — stability + new features
- **Compliance**: `@v12.0.0` — audit trail

::right::

```yaml
jobs:
  ci:
    uses: mrcointreau/shared-config/.github/workflows/ci.yml@v12
    #                                                      ^^^^
    # @main    → always latest (may break)
    # @v12     → latest v12.x.x (recommended)
    # @v12.0.0 → pinned (manual updates)
```

<!--
Three ways to reference: branch, major tag, or exact tag. For most teams, I recommend the major tag like @v12—you get new features and fixes automatically while staying on a stable API. Use @main only for internal projects where you want fixes immediately. Use exact tags for compliance where you need audit trails.
-->
