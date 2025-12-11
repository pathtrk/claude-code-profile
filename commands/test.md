---
description: Generate unit tests for the selected code
argument-hint: [test-framework]
allowed-tools: [Bash, Filesystem, mcp__puppeteer, mcp__playwright]
---

Generate tests for current context using $1 (or infer from project).

Follow existing test patterns. Cover edge cases, errors, and typical use cases.

**UI Verification (if applicable)**
For web UI changes (HTML/CSS/JS, React components, forms, routing):
- Use Playwright/Puppeteer after implementation
- Navigate, screenshot, test interactions
- Report findings before completing
