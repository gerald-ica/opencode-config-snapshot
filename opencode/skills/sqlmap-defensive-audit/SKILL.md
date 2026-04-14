---
name: sqlmap-defensive-audit
description: Use when working with sqlmap for defensive SQL injection research, local lab validation, code reading, or safe remediation guidance around SQLi testing workflows.
license: GPL-2.0
---

# sqlmap Defensive Audit

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/sqlmap`

## Scope

- sqlmap is a high-risk offensive security tool.
- Restrict use to local labs, owned infrastructure, or explicitly authorized security testing.

## Default Workflow

1. Prefer explaining capabilities, flags, and defensive testing strategy over executing attacks.
2. For code tasks, inspect `sqlmap.py`, `lib/`, and the top-level `README.md` first.
3. If a live run is required, confirm the target is authorized and use a contained environment.
4. Focus on validation, remediation, and safe reproduction steps.

## Safety

- Never aim sqlmap at third-party targets without explicit written authorization.
- Do not automate exploitation by default.
- Treat stored requests, traffic captures, and outputs as sensitive.
