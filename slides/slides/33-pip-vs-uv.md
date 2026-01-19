---
layout: two-cols-header
---

# pip vs uv

::left::

### Purpose

Use a faster, simpler Python toolchain in CI.

### Key advantages

- 10–100x faster installs
- Single binary, no bootstrap
- `uv run` replaces venv activation

### Notes

Drop‑in replacement for pip, pip-tools, and virtualenv.

::right::

| Tool | Install Speed | Lock Support | Dependency Resolution |
|------|--------------|--------------|----------------------|
| **uv** | ~10-100x faster | Native | Fast SAT solver |
| pip | Baseline | pip-tools | Sequential |
| poetry | Slow | poetry.lock | Custom resolver |
| pipenv | Slow | Pipfile.lock | pip-based |

<!--
uv replaces pip, pip-tools, and virtualenv in a single binary. The "uv run" command eliminates the venv activation dance entirely. In CI, speed matters—uv's 10-100x improvement shaves minutes off every build, and its fast SAT solver handles complex dependency trees better than pip. Let's wrap up with the key takeaways before moving to Q&A.
-->
