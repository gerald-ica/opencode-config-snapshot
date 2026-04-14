# Local Agent Flow

Use a repo-first, verification-first workflow on this machine.

## Execution Order

1. Read the nearest repo-local AI docs first when they exist: `AGENTS.md`, `GEMINI.md`, `CLAUDE.md`, `SKILL.md`.
2. Scout manifests, entrypoints, install docs, and existing wrappers before editing.
3. Split substantial work into discovery, implementation, and review tracks only when the work is actually independent.
4. Keep one canonical config location per tool and link everything else back to it.
5. Verify local services with real commands, endpoints, or process checks before declaring setup complete.

## Tool Ownership

- OpenCode canonical config: `~/.config/opencode`
- OpenCode compatibility dir: `~/.opencode`
- Gemini local instructions: `~/.gemini/GEMINI.md`
- Codex canonical config: `~/.codex/config.toml`
- Codex local memory layer: `~/.codex/memories`
- Community skill sources: `/Users/wendyly/.local/share/agent-skills/repos/community-pack`

## Skill Policy

- Never activate two skills with the same purpose and name.
- Reuse existing installed repos when they already provide the same skill pack.
- Keep imported community skills as symlinks to their source repos.
- Prefer wrapper skills for framework repos instead of copying raw source trees into agent paths.

## Security-Sensitive Repo Policy

- Default to static inspection, wrapper skills, and documentation for offensive or OSINT-heavy repos.
- Only run scans or exploit-oriented tooling against systems the user owns or has explicit permission to test.
- Prefer isolated virtualenvs, containers, or local snapshots over system-wide installs.
- Treat generated reports, prompts, traces, and scan outputs as sensitive artifacts.

## Verification Policy

- Do not claim a model, plugin, MCP server, or local service works unless the actual endpoint or command succeeds.
- When a repo is staged from a source snapshot instead of a valid Git checkout, say that explicitly.
