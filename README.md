# Matin Agent Skills

Private, portable skill bundle for Codex, Claude Code, and OpenCode.

## Install all skills

Install this bundle into a repository for all three agents:

```bash
npx skills add matinz03/agent-skills --skill '*' -a claude-code -a codex -a opencode --yes
```

Install into every supported agent detected on the machine:

```bash
npx skills add matinz03/agent-skills --all
```

Project scope is default. Add `-g` when skills should be available across all repositories for that agent.

## RTK

RTK is distributed as a separate native CLI, not committed as a platform-specific binary. After installing this bundle, invoke `/rtk-setup` to install the correct RTK release and configure it for Claude Code, Codex, OpenCode, or all three.

Direct setup request:

```text
Use rtk-setup. Configure RTK for Claude Code, Codex, and OpenCode in this repository.
```

## Included

- Caveman skills from `JuliusBrussee/caveman`.
- JSMastery skills from `jsmastery-pro/jsm-agent-skill`.
- `rtk-setup`, maintained here, for portable RTK installation and agent setup.

## Updating

Refresh this bundle from its upstream sources, then reinstall into a repository:

```bash
npx skills add matinz03/agent-skills --skill '*' -a claude-code -a codex -a opencode --yes
```

Review upstream changes before publishing updates to this private repository.
