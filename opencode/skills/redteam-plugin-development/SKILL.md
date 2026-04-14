---
name: redteam-plugin-development
description: Standards for creating promptfoo redteam plugins and graders. Use when creating new plugins, writing graders, or modifying attack templates.
license: MIT
---

# Redteam Plugin Development

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/promptfoo`

## Scope

- Create or modify promptfoo redteam plugins and graders.
- Keep grader prompts and plugin metadata aligned with promptfoo's internal conventions.

## Required Tag Conventions

Use these tags in graders:

- `<UserQuery>{{prompt}}</UserQuery>`
- `<purpose>{{purpose}}</purpose>`
- `<AllowedEntities>` when relevant

Do not use deprecated alternatives like:

- `<UserPrompt>`
- `<UserInput>`
- lowercase `<prompt>`

## Development Pattern

1. Add or modify the plugin implementation in `src/redteam/plugins/`.
2. Export it from the relevant index files.
3. Register metadata and grader entries in the redteam constants and grader registry.
4. Add or update docs under `site/docs/red-team/plugins/`.
5. Reuse existing base classes for image-dataset plugins when applicable.

## Grader Rules

- Keep pass/fail criteria explicit.
- Return a `{reason, pass, score}` structure.
- For multimodal grading, avoid feeding base64-heavy `{{prompt}}` into the grader when `{{testVars.prompt}}` is sufficient.

## Reference Files

- `src/redteam/plugins/`
- `src/redteam/constants/`
- `src/redteam/graders.ts`
- `src/prompts/grading.ts`

## Safety

- Redteam plugins are for controlled evaluation of owned or authorized systems.
- Treat jailbreak prompts, traces, and model outputs as sensitive evaluation artifacts.
