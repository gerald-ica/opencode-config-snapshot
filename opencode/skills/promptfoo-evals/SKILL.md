---
name: promptfoo-evals
description: Creates or updates promptfoo evaluation suites, prompts, tests, assertions, and provider configs. Use when adding eval coverage, debugging regressions, or scaffolding a new eval matrix.
license: MIT
---

# Promptfoo Evals

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/promptfoo`

## Scope

- Create or refine maintainable `promptfoo` evaluation suites.
- Prefer deterministic assertions first and model-graded assertions only where they add real value.

## Workflow

1. Search for existing `promptfooconfig.yaml`, `promptfooconfig.yml`, or `evals/` directories before creating new ones.
2. For new suites, prefer:

```text
evals/<suite-name>/
  promptfooconfig.yaml
  prompts/
  tests/
```

3. Add the schema header to config files:

```yaml
# yaml-language-server: $schema=https://promptfoo.dev/config-schema.json
```

4. Put prompts in `prompts/*.txt` or `prompts/*.json` and reference them with `file://`.
5. Keep provider count small and aligned with the real system under test.
6. Use file-backed tests where possible and include edge cases, regressions, safety/refusal checks, and output-shape validation.
7. Use deterministic assertions first:
   - `equals`
   - `contains`
   - `regex`
   - `is-json`
   - `javascript`
   - `python`
8. Use model-graded assertions sparingly:
   - `llm-rubric`
   - `factuality`
   - `answer-relevance`
   - `context-faithfulness`

## Validation

- During development, run with `--no-cache`.
- In the promptfoo repo itself, prefer local build commands over published npm packages.

Example:

```bash
npm run local -- validate -c <config>
npm run local -- eval -c <config> --no-cache --env-file .env
```

## Output Contract

When done, state:

- what the suite evaluates
- files created or modified
- how to run it
- required env vars
- any unavoidable TODOs
