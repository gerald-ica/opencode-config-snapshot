---
name: sherlock-osint
description: Use when working with Sherlock for username-based OSINT, social account discovery, Python packaging, or repo-local defensive investigation workflows.
license: MIT
---

# Sherlock OSINT

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/sherlock`

## Scope

- Sherlock is for username reconnaissance across public social platforms.
- Use only for lawful investigations, consented research, or defensive identity monitoring.

## Default Workflow

1. Inspect `pyproject.toml` and the main Python entrypoints before installing anything.
2. Prefer source inspection and dry-run planning over live mass queries.
3. If execution is required, isolate it in a virtualenv and keep request volume conservative.
4. Be explicit about rate limits, ToS constraints, and false-positive risk.

## Local Notes

- Stack: Python, Poetry
- Console entrypoint: `sherlock`

## Safety

- Do not use for harassment, stalking, credential abuse, or bulk profiling.
- Avoid automated installs unless the user explicitly wants local execution.
