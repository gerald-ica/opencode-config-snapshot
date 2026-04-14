---
name: openscreen-tool
description: Use when the task involves the local openscreen app or repo for screen-recording workflows, product demos, walkthrough export, or debugging the OpenScreen Electron codebase.
---

# OpenScreen

Use when the task involves the local `openscreen` app or repo for screen-recording workflows, product demos, walkthrough export, or debugging the OpenScreen Electron codebase.

Repo path: `/Users/wendyly/.local/share/agent-skills/vendor/openscreen`

What to do:
- Treat this as an Electron + React + Vite app.
- Use `npm install` in the repo before build or test tasks if `node_modules` is missing.
- Use `npm run dev` for local development and `npm run build:mac` for macOS packaging.
- Use `npm run test` for unit tests and `npm run test:e2e` for Playwright coverage.
- If the user wants the installed desktop app instead of source changes, prefer the GitHub release build noted in the repo README.

Guardrails:
- macOS screen-recording and accessibility permissions are required for runtime verification.
- Do not promise system-audio capture on unsupported macOS versions.
- Prefer focused fixes in `src/` or `electron/` over broad refactors.
