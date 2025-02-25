# Dotfiles

This repository contains my personal configuration files for:
- Aerospace (window manager)
- tmux (terminal multiplexer)
- Oh My Zsh (zsh framework)
- Starship (cross-shell prompt)
- iTerm2 (terminal emulator)

## Installation Guide

### Prerequisites

Make sure you have Git installed:

```bash
# On macOS
brew install git
```

### Clone the Repository

```bash
git clone git@github.com:snewman-aa/dotfiles.git ~/dotfiles
```

### Aerospace

[Aerospace](https://github.com/nikitabobko/aerospace) is a tiling window manager for macOS.

1. Install Aerospace:
   ```bash
   brew install --cask nikitabobko/tap/aerospace
   ```

2. Link the configuration file:
   ```bash
   ln -sf ~/dotfiles/.aerospace.toml ~/.aerospace.toml
   ```

3. Start Aerospace:
   ```bash
   open -a Aerospace
   ```

4. Enable Accessibility permissions for Aerospace when prompted.

### tmux

[tmux](https://github.com/tmux/tmux) is a terminal multiplexer that lets you switch between several programs in one terminal.

1. Install tmux:
   ```bash
   brew install tmux
   ```

2. Link the configuration:
   ```bash
   mkdir -p ~/.config/tmux
   ln -sf ~/dotfiles/.config/tmux/* ~/.config/tmux/
   ```

3. Install the tmux plugin manager (TPM):
   ```bash
   git clone https://github.com/tmux-plugins/tpm ~/.config/tmux/plugins/tpm
   ```

4. Start tmux and press `prefix + I` (usually `Ctrl+b` then `I`) to install plugins.

### Oh My Zsh

[Oh My Zsh](https://ohmyz.sh/) is a framework for managing your Zsh configuration.

1. Install Zsh if not already installed:
   ```bash
   brew install zsh
   ```

2. Install Oh My Zsh:
   ```bash
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

3. Link the Zsh configuration:
   ```bash
   ln -sf ~/dotfiles/.zshrc ~/.zshrc
   ```

4. Install custom plugins if needed:
   ```bash
   # Example: Install zsh-syntax-highlighting
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   
   # Example: Install zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```

5. Source your configuration:
   ```bash
   source ~/.zshrc
   ```

### Starship Prompt

[Starship](https://starship.rs/) is a minimal, blazing-fast, and infinitely customizable prompt for any shell.

1. Install Starship:
   ```bash
   brew install starship
   ```

2. Link the configuration:
   ```bash
   mkdir -p ~/.config
   ln -sf ~/dotfiles/.config/starship.toml ~/.config/starship.toml
   ```

3. Make sure your `.zshrc` has the Starship initialization line:
   ```bash
   # This should be at the end of your .zshrc
   eval "$(starship init zsh)"
   ```

### iTerm2

[iTerm2](https://iterm2.com/) is a replacement for Terminal on macOS.

1. Install iTerm2:
   ```bash
   brew install --cask iterm2
   ```

2. Import the profile settings:
   - Open iTerm2
   - Go to `Preferences → Profiles`
   - In the lower section, click on "Other Actions" dropdown
   - Select "Import JSON Profiles..."
   - Navigate to `~/dotfiles/.config/iterm2/` and select the profile JSON file

3. Alternatively, to use all settings:
   - Open iTerm2
   - In `Preferences → General → Preferences`, check "Load preferences from a custom folder or URL"
   - Choose `~/dotfiles/.config/iterm2/`


## Customization

Feel free to modify any of these configuration files to suit your needs. After making changes, be sure to:

1. Restart the application (or source the configuration file)
2. Run the backup script to save your changes to the repository