---
layout: two-cols-header
---

# Docs Workflow

::left::

### Purpose

Build docs and publish to GitHub Pages or DevPortal.

### Inputs

- `project-type`: `node` or `python`
- `publish`: `true` to push to Pages
- `publish-devportal`: `true` to push to DevPortal
- `devportal-docs-branch`: default `docs-dist`
- `docs-path`: default `docs`

::right::

```yaml
uses: mrcointreau/shared-config/.github/workflows/docs.yml@main
with:
  project-type: node    # TypeDoc
  # project-type: python  # Sphinx
  publish: true         # to GitHub Pages
  publish-devportal: true  # to DevPortal branch
  docs-path: "docs"
```

<!--
TypeDoc handles Node projects, Sphinx handles Python—documentation tooling matches the ecosystem. There are two publish targets: GitHub Pages and DevPortal. DevPortal integration is optional for teams using centralized documentation portals, and both can be enabled simultaneously. Here's the flow showing how both publishing targets work independently.
-->
