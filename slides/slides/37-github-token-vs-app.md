---
layout: two-cols-header
---

# GITHUB_TOKEN vs App

::left::

### Purpose

Enable secure automation that can bypass branch protection.

### Benefits

- Trigger downstream workflows
- Fine-grained, repo-specific permissions
- Short-lived, on-demand tokens

### Security

- No long-lived PATs
- Automatic expiration (1 hour max)
- Audit trail per installation

::right::

| `GITHUB_TOKEN` Limitation | GitHub App Solution |
|--------------------------|---------------------|
| Can't trigger other workflows | App tokens can trigger workflows |
| Blocked by branch protection | Bypasses branch protection rules |
| Fixed permissions per job | Fine-grained, repo-specific perms |
| Tied to workflow run | Short-lived, on-demand tokens |

<!--
GITHUB_TOKEN has two critical limitations: it can't trigger downstream workflows and can't bypass branch protection rules. GitHub App tokens solve both while being short-lived at 1 hour max, fine-grained per repo, and fully auditable. If someone asks "why not just use a PAT?"—the answer is security. PATs are long-lived and org-wide.
-->
