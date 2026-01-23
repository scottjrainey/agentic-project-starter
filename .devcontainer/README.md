# Development Container Configuration

This devcontainer provides a fully-configured Ubuntu 24.04 development environment with mise-based tooling.

## Features

### Base Environment

- **Ubuntu 24.04** with Docker-in-Docker support
- **Zsh** as default shell with Oh My Zsh and autosuggestions
- **mise** for tool version management (bun, python, uv, wrangler, etc.)
- **tmux** for terminal multiplexing

### Mounted Resources

- **SSH keys** from host (`~/.ssh` → `/home/vscode/.ssh`, read-only)
- **Docker socket** from host for Docker-in-Docker functionality

### SSH Agent Forwarding

- Host SSH agent forwarded via `SSH_AUTH_SOCK` for git operations with GitHub

## Setup Process

The devcontainer automatically runs on creation:

1. **apply-dotfiles** - Clones and applies custom dotfiles defaulting to `scottjrainey/dotfiles`
2. **setup** - Installs tmux and runs `mise trust && mise install` to install all project tools

## Customization

### Custom Dotfiles Repository

Override the dotfiles repository by setting environment variables before container creation:

```bash
export DEVCONTAINER_DOTFILES_REPO="git@github.com:yourusername/your-dotfiles.git"
export DEVCONTAINER_DOTFILES_TARGET="$HOME/.dotfiles"
export DEVCONTAINER_DOTFILES_INSTALL="$HOME/.dotfiles/install.sh"
```

### VSCode Extensions

The devcontainer automatically installs:

- `ms-azuretools.vscode-docker` - Docker management

## Scripts

- **scripts/apply-dotfiles** - Clones dotfiles repository and runs install script
- **scripts/setup** - Installs system packages and mise tools

## Usage

The container is ready to use after creation. All project commands work as documented in the main README.md.
