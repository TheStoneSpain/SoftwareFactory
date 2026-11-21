# Maestro

Maintained by [Oscar Rangel](https://github.com/TheStoneSpain).

A file-based workflow for keeping AI-assisted development organized across sessions.

Requirements, design decisions, plans, and handoff notes live alongside the code, so the next session can pick up from a written project record.

This is Oscar Rangel’s maintained distribution of [Maestro](https://github.com/pjasielski/maestro), originally developed by Piotr Jasielski. See [CHANGES.md](CHANGES.md) for the changes in this version and [LICENSE](LICENSE) for the original MIT license.

## What it includes

- Commands for exploration, specifications, planning, implementation, and review.
- Reusable Markdown templates for project documentation.
- Adapters for Claude Code, Cursor, Codex, and GitHub Copilot.
- A Bash installer that preserves project notes and configuration on reinstall.
- Offline installer acceptance checks and GitHub Actions validation.

## Quick start

Download or clone this repository, then run the installer against a **different project folder**:

```bash
bash install.sh /absolute/path/to/your-project --quick
```

Requires Bash, curl, and an AI coding tool. Git is recommended. For Windows, use Git Bash or WSL. The framework itself needs no API key or running service.

Open your target project in your coding tool and follow the workflow:

```text
mae-explore     Understand the project
mae-specs       Write the requirements and architecture
mae-plan        Break the work into tasks
mae-do         Implement a task
sync           Save the session handoff
```

Use slash commands in Claude Code and Cursor; use command names or the installed skills in Codex. Adapter installation is checked automatically; interactive behavior depends on the tool and has not been verified here.

## Repository layout

```text
.maestro/          Canonical commands, skills, and document templates
.claude/           Claude Code adapters
.cursor/           Cursor adapters
.agents/           Shared skill adapters
.github/workflows/ Automated checks
assets/            Original Maestro artwork
setup/             Optional upstream browser setup helper
install.sh         Framework installer
MAESTRO.md         Framework reference
maestro.toml       Repository configuration
```

## Install from your GitHub repository

After publishing this repository as `TheStoneSpain/SoftwareFactory`, run:

```bash
export MAESTRO_REPO="TheStoneSpain/SoftwareFactory"
export MAESTRO_BRANCH="main"
curl -fsSL "https://raw.githubusercontent.com/$MAESTRO_REPO/$MAESTRO_BRANCH/install.sh" -o /tmp/maestro-install.sh
bash /tmp/maestro-install.sh /absolute/path/to/your-project --quick
```

`MAESTRO_REPO` selects the repository used for downloads. It defaults to `TheStoneSpain/SoftwareFactory`. `MAESTRO_URL` can override the entire source URL. Local installation uses this checkout's files.

## Development

```bash
bash -n install.sh
bash docs/06-test/install-check.sh
```

The acceptance suite checks local/download parity, adapter references, incomplete downloads, upgrades, preserved user configuration, license inclusion, and session visibility. Downloads in the suite use local files, so no network access is needed.

## Documentation

- [User guide](docs/user-guide.md)
- [Command and configuration reference](docs/reference.md)
- [Installation guide](docs/installation.md)
- [Changes in this distribution](CHANGES.md)
- [Upstream release history](CHANGELOG.md)
- [Publishing to GitHub](PUBLISHING.md)

Installation links in the guides and optional browser helper point to `TheStoneSpain/SoftwareFactory`. They become available after the repository is published with a `main` branch.

## License

MIT. Original copyright © 2026 Piotr Jasielski. The license is included in this repository and copied into `.maestro/LICENSE` in installed projects.
