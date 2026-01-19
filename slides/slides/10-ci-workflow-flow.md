---
layout: diagram-tight
---

# CI Workflow Flow

```mermaid {scale: 0.7}
flowchart LR
  subgraph inputs[Inputs]
    pt([project-type])
    skip([skip-* flags])
  end
  pt -->|node| ci_node[ci/node action]
  pt -->|python| ci_python[ci/python action]
  ci_node --> steps[lint → test → build → audit]
  ci_python --> steps
  skip -.->|controls| steps
```

::caption::
`project-type` input determines which CI action runs; `skip-*` flags control individual steps

<!--
The workflow dispatches to either ci/node or ci/python based on project-type—one interface, two implementations. This branching happens early so each ecosystem gets optimized tooling like npm versus uv without complicating the caller's config. Now let's see how the PR workflow extends this by adding commit linting.
-->
