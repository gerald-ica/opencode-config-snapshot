---
name: shannon-defensive-security
description: Use when working with Shannon for white-box defensive application security testing, repo-local setup, workflow inspection, or safe evaluation of its multi-agent pentest pipeline.
license: Apache-2.0
---

# Shannon Defensive Security

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/shannon`

## Scope

- Treat Shannon as a defensive white-box security tool.
- Use only against applications you own or have explicit authorization to test.
- Do not point it at untrusted or adversarial repositories without an explicit prompt-injection review.

## Default Workflow

1. Read `README.md` and `CLAUDE.md` before making changes.
2. Inspect `apps/cli/` and `apps/worker/` separately.
3. Review Docker, Temporal, and model-provider assumptions before any execution.
4. Prefer static review and configuration work over live exploitation.
5. If execution is necessary, use isolated test targets and non-production credentials.

## Local Notes

- Stack: TypeScript, pnpm, Turbo, Docker, Temporal
- Native docs: `CLAUDE.md`
- This repo already contains agent-oriented guidance, but not a portable `SKILL.md`

## Safety

- Do not auto-install or auto-run scans against third-party systems.
- Do not bypass the repo's package age or safety checks.
- Treat generated reports, prompts, and workspace artifacts as sensitive security material.
