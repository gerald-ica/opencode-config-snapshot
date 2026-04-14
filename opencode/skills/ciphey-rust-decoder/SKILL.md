---
name: ciphey-rust-decoder
description: Use when working with the Rust Ciphey project for automated decoding, binary setup, Cargo-based development, or review of heuristic decoding pipelines.
license: MIT
---

# Ciphey Rust Decoder

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/Ciphey`

## Scope

- This repo is the Rust implementation of Ciphey.
- Use it for local decoding workflows, library review, or controlled binary setup.

## Default Workflow

1. Inspect `Cargo.toml` and `src/` before building.
2. Prefer `cargo check` or read-only review before full install.
3. Verify any large bundled resources or SQLite-backed data paths before runtime use.
4. Keep decoding work local and explicit about input provenance.

## Safety

- Do not treat decoded material as trustworthy without independent verification.
- Avoid feeding sensitive data into third-party services while debugging decode flows.
