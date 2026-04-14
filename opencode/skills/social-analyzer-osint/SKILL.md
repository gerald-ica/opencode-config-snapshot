---
name: social-analyzer-osint
description: Use when working with Social Analyzer for profile discovery, OSINT workflow review, Python or Node setup, browser automation constraints, or defensive social footprint analysis.
license: AGPL-3.0
---

# Social Analyzer OSINT

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/social-analyzer`

## Scope

- Social Analyzer mixes Python and Node tooling with browser automation.
- Use it for lawful OSINT, account monitoring, or internal security research.

## Default Workflow

1. Inspect both `package.json` and `requirements.txt` before installing.
2. Treat browser, OCR, and screenshot features as higher-risk and dependency-heavy.
3. Prefer documentation, configuration, and wrapper guidance unless execution is explicitly requested.
4. If setup is needed, isolate Python and Node dependencies and avoid system-wide install.

## Safety

- Do not use for harassment, doxxing, or mass scraping of protected targets.
- Be clear about Chrome, geckodriver, and automation dependencies before enabling them.
- Avoid executing bundled installs implicitly.
