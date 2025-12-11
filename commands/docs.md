---
description: Generate documentation from implementation
argument-hint: [scope: function|class|module|file]
allowed-tools: [Filesystem]
---

Generate/update documentation for $1 (defaults to current context).

Use appropriate style: JSDoc/docstrings (TS/Python), Doxygen (C++), XML (C#), roxygen2 (R).
Focus on why/what, assumptions, constraints. Include examples for public APIs.