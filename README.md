# dotfiles

My macOS dotfiles managed with GNU Stow.

## Prerequisites

```bash
# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install stow and dependencies
brew install stow

# Restore Homebrew packages
brew bundle install --file=Brewfile
```

## Installation

```bash
# Clone the repo
git clone https://github.com/Sombrechip88244/dotfiles.git ~/.config
cd ~/.config

# Dry run to preview
stow -n -t ~ */

# Apply all dotfiles
stow -t ~ zsh nvim starship gh ghostty skhd yabai yazi btop borders gh-dash

# Or stow individually
stow -t ~ zsh
stow -t ~ nvim
```

## Packages

| Package | Target |
|---------|--------|
| zsh | `~/.zshrc`, `~/.zprofile` |
| nvim | `~/.config/nvim/` |
| starship | `~/.config/starship.toml` |
| gh | `~/.config/gh/` |
| gh-dash | `~/.config/gh-dash/` |
| ghostty | `~/.config/ghostty/` |
| skhd | `~/.config/skhd/` |
| yabai | `~/.config/yabai/` |
| yazi | `~/.config/yazi/` |
| btop | `~/.config/btop/` |
| borders | `~/.config/borders/` |

## Updating

```bash
# Restow after changes
stow -R -t ~ <package>

# Update Brewfile
brew bundle dump --file=Brewfile --describe
```

## Cheat Sheet

```bash
stow -n -v */        # Preview
stow -v */           # Apply
stow -R -v */        # Restow
stow -D <package>    # Unstow
```
