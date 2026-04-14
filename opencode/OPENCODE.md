# OpenCode Local Policy

Use OpenCode as the local-first orchestrator for this machine.

## Priorities

- Prefer the shared skill layer and wrapper skills before inventing new repo glue.
- Use `repo-scout` for read-only discovery, `framework-adapter` for wrappers and integration, and `review-gate` for final verification when the task is large enough to justify parallel work.
- Keep edits narrow and verifiable. Do not leave half-configured plugins or duplicate skill trees behind.

## Local Model Policy

- Default model is served through LM Studio.
- Verify `http://127.0.0.1:1234/v1/models` or a real OpenCode run before declaring the local provider healthy.
- If plugin behavior is in doubt, isolate with `--pure` during diagnosis.

## Repo Policy

- Read the nearest repo-local `AGENTS.md`, `CLAUDE.md`, or `SKILL.md` before generalizing.
- For security-sensitive repos, prefer source review and wrapper guidance over executing the tool.
- If a repo is available only as a source snapshot rather than a valid Git checkout, treat it as read-only source unless the user explicitly asks for local modifications.
