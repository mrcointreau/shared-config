---
layout: diagram-tight
---

# Release Workflow Flow

```mermaid {scale: 0.5}
flowchart LR
  subgraph inputs[Inputs]
    pt([project-type])
    pub([publish])
    oidc_in([use-oidc])
    bm([back-merge])
    dr([dry-run])
  end
  pt -->|node| rel_node[release/node]
  pt -->|python| rel_python[release/python]
  pub -.->|enables npm publish| rel_node
  pub -.->|enables pypi publish| rel_python
  oidc_in -.->|controls auth| rel_node
  oidc_in -.->|controls auth| rel_python
  rel_node --> merge_check
  rel_python --> merge_check
  bm --> merge_check{back-merge && !dry-run?}
  dr --> merge_check
  merge_check -->|yes| back_merge[back-merge job]
  merge_check -->|no| done[done]
```

::caption::
`publish` enables atomic npm/pypi publishing based on project-type; `use-oidc` controls auth

<!--
The publish flag enables atomic registry publishing and OIDC controls authentication. Back-merge only runs on real releases, not dry-runs. The dry-run option lets you preview what would happen without side effects—useful for testing release configuration changes. Here's what the actual consumer workflow looks like; notice how simple it is.
-->
