# OpenCode Asset Map

This machine uses a deduplicated OpenCode setup.

## Already present, reused

- `impeccable`
- `last30days`
- marketing skill set from `marketingskills`
- platform design skills
- `superdesign`

## Newly linked from external repos

- `taste-skill` collection
- `emil-design-eng`
- computational design skills
- curated unique skills from `claude-code-config`
- selected PR/release skills from `oh-my-openagent`

## Wrapper skills created locally

- `shannon-defensive-security`
- `sherlock-osint`
- `sqlmap-defensive-audit`
- `social-analyzer-osint`
- `ciphey-rust-decoder`
- `maigret-osint`
- `defaultcreds-audit`
- `promptfoo-evals`
- `redteam-plugin-development`
- `search-params`

## Agent strategy

- Imported a curated subset of specialist markdown agents from `claude-code-config`
- Added `local-orchestrator` as the default high-signal coordinator for local-first work

## LM Studio

- Provider ID: `lmstudio`
- Base URL: `http://127.0.0.1:1234/v1`
- Default model: `Jackrong/Qwen3.5-27B-Claude-4.6-Opus-Reasoning-Distilled-GGUF/Qwen3.5-27B.Q4_K_S.gguf`

## Note on duplicates

If a requested repo overlapped an already-installed skill family, the existing installed source was kept and the duplicate repo was staged only for inspection and reference.

## Security-sensitive repos

The following repos were integrated conservatively:

- `shannon`
- `sherlock`
- `sqlmap`
- `social-analyzer`
- `Ciphey`
- `maigret`
- `promptfoo`
- `DefaultCreds-cheat-sheet`

These were added as wrapper skills and staged for local inspection. High-risk repos are not auto-executed by default.

## Canonicalized overlaps

The following overlapping custom wrappers were retired in favor of canonical community or repo-native skills:

- `openscreen-workflow` -> `openscreen-tool`
- `awesome-autoresearch` -> `awesome-autoresearch` from community-pack
- `tribev2-neuroscience` -> `tribev2-research`
- `embedding-atlas-workflow` -> `embedding-atlas`
- `metadata-extractor-java` -> `metadata-extractor`
- `promptfoo-evals-redteam` -> `promptfoo-evals` plus `redteam-plugin-development`

## Promptfoo native skills promoted

The local `promptfoo` source snapshot ships reusable agent guidance. The following were normalized into portable multi-tool skills and linked into the shared toolchain:

- `promptfoo-evals`
- `redteam-plugin-development`
- `search-params`
