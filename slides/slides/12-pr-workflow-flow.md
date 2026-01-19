---
layout: diagram-tight
---

# PR Workflow Flow

```mermaid {scale: 0.7}
flowchart LR
  subgraph inputs[Inputs]
    pt([project-type])
    rcl([run-commit-lint])
  end
  pt --> ci[ci job]
  ci -->|calls| ci_wf[ci.yml workflow]
  rcl --> check{true?}
  check -->|yes| commitlint[commitlint action]
  check -->|no| skip[skip]
```

::caption::
`ci` and `commit-lint` jobs run in parallel

<!--
CI and commit-lint run in parallel so developers get both results quickly—neither blocks the other. Note that fetch-depth: 0 is required for commitlint to see the full commit range. Now let's look at the release strategy and how we handle beta versus stable releases.
-->
