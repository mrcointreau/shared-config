---
layout: diagram-tight
---

# Docs Workflow Flow

```mermaid {scale: 0.55}
flowchart LR
  subgraph inputs[Inputs]
    pt([project-type])
    pub([publish])
    devp([publish-devportal])
  end
  pt -->|node| typedoc[docs/typedoc]
  pt -->|python| sphinx[docs/sphinx]
  typedoc --> artifact[upload artifact]
  sphinx --> artifact
  pub --> pub_check{true?}
  devp --> dev_check{true?}
  artifact --> pub_check
  artifact --> dev_check
  pub_check -->|yes| pages[docs/publish]
  dev_check -->|yes| devportal[docs/devportal-publish]
```

::caption::
GitHub Pages and DevPortal publishing are independent and controlled by inputs

<!--
GitHub Pages and DevPortal publishing run independently—you can enable either or both. The artifact step ensures docs are built once and deployed many times. This decoupling makes it easy to add new targets later. Finally, let's cover the standalone publish workflow for recovery scenarios.
-->
