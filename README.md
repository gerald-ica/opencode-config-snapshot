# OpenCode Config Snapshot

This repository is a published snapshot of a local OpenCode setup.

It preserves the OpenCode configuration, agents, commands, skills, MCP declarations, and linked tool references from the source machine in a repo-safe form. Local symlinks were resolved into real files so the published tree contains the actual assets instead of machine-specific pointers.

## What is included

- `opencode/opencode.json`: primary OpenCode config
- `opencode/oh-my-openagent.json`: plugin configuration for `oh-my-openagent`
- `opencode/agents/`: current local OpenCode agents
- `opencode/agents-legacy-20260409-004339/`: imported legacy agent set
- `opencode/commands/`: OpenCode command markdown files
- `opencode/skills/`: installed skill library
- `opencode/tools/`: linked tool registry and integration wrappers
- `shared-agents/AGENTS.md`: shared machine-level instruction file
- `INVENTORY.md`: verified counts and snapshot summary

## Verified snapshot contents

- `173` skill directories
- `173` skill folders with `SKILL.md`
- `4` current local agents
- `15` legacy imported agents
- `11` commands
- `140` tool files
- OpenCode plugin: `oh-my-openagent`
- OpenCode MCP servers: `gitnexus`, `paper`, `pencil`

## Notes

- This is a machine-specific snapshot, not a portable turnkey install.
- Some config files contain absolute local paths and local service URLs.
- `node_modules/` and desktop metadata files were excluded from publication.
- The source snapshot was taken from `~/.config/opencode` and `~/.agents/AGENTS.md`.

## Layout

```text
.
├── INVENTORY.md
├── README.md
├── opencode/
│   ├── OPENCODE.md
│   ├── README-installed-assets.md
│   ├── agents/
│   ├── agents-legacy-20260409-004339/
│   ├── commands/
│   ├── oh-my-openagent.json
│   ├── opencode.json
│   ├── skills/
│   └── tools/
└── shared-agents/
    └── AGENTS.md
```

## Wiki

The repository wiki documents the snapshot structure and the main config surfaces:

- Home
- Snapshot Overview
- Agents Commands Skills
- MCP And Plugins
