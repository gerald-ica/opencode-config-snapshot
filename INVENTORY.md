# OpenCode Snapshot Inventory

Snapshot source:

- `~/.config/opencode`
- `~/.agents/AGENTS.md`

Snapshot notes:

- Symlinks were materialized into real files for `skills/`, `commands/`, and `tools/`.
- `node_modules/` and `.DS_Store` were excluded from the repo snapshot.
- This snapshot is intended to preserve OpenCode configuration, agents, commands, skills, MCP config, and linked tool assets.

Verified contents:

- OpenCode config file: `opencode/opencode.json`
- Plugin config file: `opencode/oh-my-openagent.json`
- Local policy docs: `opencode/OPENCODE.md`, `opencode/README-installed-assets.md`
- Shared instruction file: `shared-agents/AGENTS.md`
- Current OpenCode agents: `4`
- Legacy imported agents: `15`
- Commands: `11`
- Skills directories: `173`
- Skills with `SKILL.md`: `173`
- Tool files under `tools/`: `140`

Configured OpenCode plugin(s):

- `oh-my-openagent`

Configured MCP servers in `opencode/opencode.json`:

- `gitnexus`
- `paper`
- `pencil`

Current first-party agents in `opencode/agents/`:

- `framework-adapter.md`
- `local-orchestrator.md`
- `repo-scout.md`
- `review-gate.md`

Current commands in `opencode/commands/`:

- `analyze-project.md`
- `brainstorm.md`
- `create-agent-skill.md`
- `create-hook.md`
- `create-plan.md`
- `create-slash-command.md`
- `create-subagent.md`
- `debug.md`
- `execute-plan.md`
- `run-plan.md`
- `write-plan.md`

Verification summary:

- The repo snapshot contains the actual skill content, not just local symlink pointers.
- The counts above were verified against the copied snapshot, not only the source tree.
