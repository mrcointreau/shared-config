---
layout: diagram-tight
---

# Standalone Publish Workflow Flow

```mermaid {scale: 0.6}
flowchart LR
  subgraph inputs[Inputs]
    pt([project-type])
    ver([version])
    oidc_in([use-oidc])
  end
  ver --> checkout[checkout tag]
  checkout --> pt
  pt -->|node| pub_node[publish/node]
  pt -->|python| pub_python[publish/python]
  pub_node --> oidc_check
  pub_python --> oidc_check
  oidc_in --> oidc_check{true?}
  oidc_check -->|yes| oidc_auth[OIDC trusted publishing]
  oidc_check -->|no| token_auth[token auth]
```

::caption::
`use-oidc` input controls authentication method; OIDC eliminates long-lived secrets

<!--
Checkout happens by Git tag, not branch—this ensures you publish exactly what was released. OIDC is preferred over long-lived tokens since it eliminates secret rotation headaches. Both npm and PyPI support it now, so there's no reason to use tokens for new projects. That covers the workflows layer. Now let's dive into the composite actions that implement all this.
-->
