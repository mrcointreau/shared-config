---
layout: code-full
---

# Workflows Overview

| Workflow | Purpose | Trigger |
|----------|---------|---------|
| **ci.yml** | Lint, test, build, audit | `workflow_call` |
| **pr.yml** | CI + commit linting | `workflow_call` |
| **release.yml** | Versioning & publish | `workflow_call`, `dispatch` |
| **docs.yml** | Generate & publish docs (Pages/DevPortal) | `workflow_call` |
| **publish.yml** | Republish to npm/PyPI | `workflow_call`, `dispatch` |

All workflows require `project-type: node | python` input.

<!--
Five workflows cover the full development lifecycle: CI, PR, release, docs, and publish. All require project-type as the primary input—this keeps the interface simple while supporting both ecosystems. Let's look at the CI workflow first since it's the foundation that others build on.
-->
