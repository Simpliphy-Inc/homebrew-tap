# homebrew-tap

Homebrew tap for Simpliphy tools.

## Yggdrasil Install

### Prerequisites

- macOS Apple Silicon (`arm64`)
- Homebrew installed and on `PATH` (`brew --version` succeeds)
- Internet access to GitHub
- No GitHub account, login, or token required (tap and release artifacts are public)

### Install

```bash
brew tap Simpliphy-Inc/tap
brew install --cask Simpliphy-Inc/tap/yggdrasil
yggdrasil version
```

## Notes

- Current cask artifacts target Apple Silicon only.
- `tmux` is not required for install/version, but is required for Yggdrasil workspace and managed-run features.
