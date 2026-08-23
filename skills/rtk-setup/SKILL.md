---
name: rtk-setup
description: Install and configure RTK, the Rust Token Killer CLI, for the current repository and selected coding agents. Use when a user asks to install RTK, make RTK mandatory, or configure RTK for Claude Code, Codex, OpenCode, or multiple agents.
---

# RTK setup

Install RTK as a native CLI, then configure agent integration. Never commit the RTK binary or credentials to a repository.

## Workflow

1. Detect current OS, architecture, agent(s), and repository root.
2. Check existing installation:

   ```text
   rtk --version
   rtk gain
   ```

   `rtk gain` must identify the Rust Token Killer. Do not accept a different package named `rtk`.

3. If missing or wrong, install from the official RTK repository/release only: `https://github.com/rtk-ai/rtk`. Use the platform's documented package or prebuilt artifact, verify the release checksum when downloading an artifact, and place the executable on `PATH`.
4. Disable telemetry unless user explicitly opts in:

   ```text
   rtk telemetry disable
   ```

5. Configure requested agents:

   - Claude Code: `rtk init -g`
   - Codex: `rtk init -g --codex`
   - OpenCode: `rtk init -g --opencode`

   If global configuration is unavailable or the user requested repository-only setup, use the corresponding project-scoped command and keep generated instructions in the repository.

6. If RTK creates a repository-local analytics directory, add `.rtk/` to that repository's `.gitignore`. Never commit tracking databases.
7. Check the resulting setup with:

   ```text
   rtk --version
   rtk gain
   rtk init --show
   ```

## Safety

- Do not use `cargo install rtk` without verifying `rtk gain`, because another unrelated package uses the same name.
- Do not enable optimization, proxy provider traffic, or change model behavior; RTK only compacts command output.
- Preserve existing agent settings. If setup would overwrite custom configuration, stop and show the proposed change.
- Report exact version, agent targets, files changed, and any permission or PATH limitation.
