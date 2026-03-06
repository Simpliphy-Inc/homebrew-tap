# homebrew-tap

Homebrew tap for Simpliphy tools.

## Yggdrasil Install

### Prerequisites

- macOS Apple Silicon (`arm64`)
- Homebrew installed and on `PATH` (`brew --version` succeeds)
- Internet access to GitHub
- No GitHub account, login, or token required (tap and release artifacts are public)

### Install

`brew tap Simpliphy-Inc/tap` adds Simpliphy's custom Homebrew source so Homebrew can find the `yggdrasil` cask.

```bash
brew tap Simpliphy-Inc/tap
brew install --cask Simpliphy-Inc/tap/yggdrasil

# One-time Gatekeeper unblock (until notarization is added)
xattr -dr com.apple.quarantine "$(brew --prefix)/Caskroom/yggdrasil"

yggdrasil version
```

If macOS shows "yggdrasil" Not Opened / "Apple could not verify...", rerun:
`xattr -dr com.apple.quarantine "$(brew --prefix)/Caskroom/yggdrasil"`
then run `yggdrasil version` again.

### Update

To pull the latest cask metadata from Homebrew and upgrade `yggdrasil` if a newer release is available:

```bash
brew update
brew upgrade --cask Simpliphy-Inc/tap/yggdrasil

# If macOS blocks the upgraded binary, clear quarantine again
xattr -dr com.apple.quarantine "$(brew --prefix)/Caskroom/yggdrasil"

yggdrasil version
```

`brew update` refreshes Homebrew's local metadata. `brew upgrade --cask ...` installs the latest published `yggdrasil` release from this tap.

Because the app is not notarized yet, macOS may quarantine a newly installed upgrade the same way it does on first install. If that happens, rerun the `xattr` command above and then run `yggdrasil version` again.

If you want Homebrew to upgrade everything outdated, not just `yggdrasil`, you can use:

```bash
brew upgrade
```

## Notes

- Current cask artifacts target Apple Silicon only.
- `tmux` is not required for install/version, but is required for Yggdrasil workspace and managed-run features.
