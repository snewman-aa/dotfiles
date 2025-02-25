# Dotfiles

This repository contains my personal configuration files for:
- Aerospace (window manager)
- tmux (terminal multiplexer)
- Oh My Zsh (zsh framework)
   - Spaceship (zsh prompt/theme)
- iTerm2 (terminal emulator)

It's all using the [catppuccin theme](https://github.com/catppuccin) which may or may not be your cup of tea.

## Installation Guide

### Clone this Repository

```bash
git clone git@github.com:snewman-aa/dotfiles.git ~/dotfiles
```

### Aerospace

[Aerospace](https://github.com/nikitabobko/aerospace) is a tiling window manager for macOS. There's a bit of a learning curve if you're not used to using a tiling wm. I find it hard to go back after getting used to it though.

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

4. Start tmux and press `prefix + I` (usually `Ctrl+b` then `I`) to install plugins.

### Oh My Zsh

[Oh My Zsh](https://ohmyz.sh/) is a framework for managing your Zsh configuration.

1. Install Zsh if not already installed (mac os has zsh as the default shell now) :
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

### Spaceship zsh prompt

[Spaceship](https://github.com/spaceship-prompt/spaceship-prompt) is a minimalistic, powerful and extremely customizable Zsh prompt

I already have it setup in these dotfiles. It's in `.oh-my-zsh/custom/themes` and in `.zshrc` I point to the theme with `ZSH_THEME="spaceship"`

### iTerm2

[iTerm2](https://iterm2.com/) is a replacement for Terminal on macOS. I use the catppuccin them for iTerm2

1. Install iTerm2:
   ```bash
   brew install --cask iterm2
   ```

2. Follow the import guide from the [catppuccin repo](https://github.com/catppuccin/iterm)