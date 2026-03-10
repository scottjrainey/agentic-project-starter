# agentic-project-starter

> Workbench and tooling for modern agent-first projects

## Getting Started

**Replace this README** with your own project documentation after creating a new repository from this template.

**Note on licensing:** This starter includes an MIT License. Review and update the LICENSE file if a different license is appropriate for your project.

## Features

This starter provides a fully-configured development container with:

- **Ubuntu 24.04** with Docker-in-Docker support
- **mise** for reproducible tool version management
- **Claude CLI** for AI-powered development and agentic workflows
- **Modern tooling** including Node.js, Python, Bun, Neovim, fzf, ripgrep, and more
- **Zsh + Oh My Zsh** with autosuggestions
- **SSH agent forwarding** for seamless git operations
- **Custom dotfiles** support, defaulting to [scottjrainey/dotfiles](https://github.com/scottjrainey/dotfiles)

See [.devcontainer/README.md](.devcontainer/README.md) for complete details and customization options.

## Spec-Driven Development with OpenSpec

[OpenSpec](https://github.com/Fission-AI/OpenSpec) is a spec-driven workflow layer that keeps changes traceable from intent through implementation. Specs and change artifacts live in `openspec/` and are consumed by Claude Code via pre-baked skills and commands — no installation required.

**Entry points:**
- `/opsx:new` — start a new change
- `/opsx:onboard` — guided walkthrough of the workflow

**Upgrading the scaffold:** To regenerate OpenSpec skills and commands after an upstream release, run from the repo root and commit the result:

```sh
npx @fission-ai/openspec init --tools claude --force
```
