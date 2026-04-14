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

## Install on another computer

This repo can be used as a baseline, but it needs local adaptation after cloning.

### 1. Clone the repository

```bash
git clone https://github.com/gerald-ica/opencode-config-snapshot.git
cd opencode-config-snapshot
```

### 2. Copy the config into your local OpenCode locations

The source machine used:

- `~/.config/opencode`
- `~/.agents/AGENTS.md`

On a new machine, copy the published files into those paths:

```bash
mkdir -p ~/.config/opencode
mkdir -p ~/.agents
rsync -a opencode/ ~/.config/opencode/
cp shared-agents/AGENTS.md ~/.agents/AGENTS.md
```

### 3. Install OpenCode prerequisites

What you need depends on which parts of the snapshot you want to use. At minimum, expect to need:

- OpenCode itself
- Node.js and `npx`
- Git
- any local MCP binaries referenced in `opencode/opencode.json`
- any local services referenced by the config

### 4. Review and edit machine-specific settings

Before using the config, inspect `opencode/opencode.json` and update:

- absolute paths such as `/Users/wendyly/...`
- local binaries such as the Pencil desktop MCP binary path
- local HTTP endpoints such as `http://127.0.0.1:1234/v1`
- local MCP endpoints such as `http://127.0.0.1:29979/mcp`

Typical items to change:

- `instructions` paths
- local provider base URL
- MCP `command` arrays
- MCP remote `url` values

### 5. Install or recreate dependent local services

This snapshot expects these local integrations to exist if you want the same behavior:

- LM Studio or another OpenAI-compatible local model server
- Pencil desktop app, if you want the `pencil` MCP entry
- GitNexus CLI checkout at the configured path, if you want the `gitnexus` MCP entry
- the service behind the `paper` MCP endpoint

### 6. Verify the config on the new machine

Recommended checks:

```bash
cat ~/.config/opencode/opencode.json
test -f ~/.agents/AGENTS.md && echo "AGENTS.md installed"
curl http://127.0.0.1:1234/v1/models
curl http://127.0.0.1:29979/mcp
```

If you changed ports, hosts, or providers, use your updated values instead.

### 7. Start minimal, then expand

If the full snapshot is too machine-specific, start by enabling only:

- `shared-agents/AGENTS.md`
- `opencode/OPENCODE.md`
- `opencode/opencode.json`

Then add custom agents, commands, skills, and MCPs after the base config is working.

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
- Clone And Configure
