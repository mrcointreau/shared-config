---
layout: code-full
---

# Decision Matrix

| Area | Choice | Alternative | Why |
|------|--------|-------------|-----|
| Node version | **22 LTS** | 20, 18 | ES2024, performance |
| Python version | **3.12** | 3.11 | Faster startup, type syntax |
| Python tooling | **uv** | pip, poetry, pipenv | 10-100x faster |
| Semantic release | **Node-based** | Python-semantic-release | Better ecosystem |
| Auth default | **OIDC** | Tokens | No secret rotation |
| Audit level | **moderate** | low, high | Pragmatic security |
| Commit format | **Conventional** | Free-form | Automated changelogs |

Defaults are intentional, but every choice is overridable.

<!--
Node 22 gives ES2024 features, Python 3.12 has faster startup, uv is 10-100x faster than pip, and OIDC eliminates secret rotation. Each choice has clear reasoning but also clear escape hatches—if you're stuck on Node 18 for compatibility, override it. Let's dive deeper into why we chose uv for Python; it's probably the most controversial choice.
-->
