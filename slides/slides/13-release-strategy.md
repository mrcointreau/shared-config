---
layout: code-full
---

# Release Strategy

### Trunk-Based Development

| Branch | Role | Version |
|--------|------|---------|
| `main` | Development trunk (beta) | `1.2.0-beta.1` |
| `release` | Stable releases only | `1.2.0` |

### Flow

- All PRs merge to `main` → triggers beta release automatically
- Merge `main` → `release` for stable release
- Or **manually dispatch** stable release from GitHub UI

<div>

### Back-merge (automatic)

After stable release, `release` → `main` back-merge happens automatically to sync version history.

</div>

<!--
We use trunk-based development where main produces beta releases and the release branch produces stable versions. The orchestration layer handles back-merge automatically—no configuration needed. Stable releases can be triggered by merging to release or manually via workflow dispatch for recovery scenarios.
-->
