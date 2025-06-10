# Dotfiles

This repository contains my personal configuration files for:
- Aerospace (window manager)
   - Jankyborders (borders for focused windows)
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

My `aerospace.toml` has some pretty specific space names and scripts for automatically assigning certain windows to certain spaces. For example:

```toml
[[on-window-detected]]
    if.app-name-regex-substring = 'discord'
    run = 'move-node-to-workspace Discord'
```

`.toml` files are pretty intuitive to modify, so mine might be a good jumping off point if you want spaces with custom names instead of A-Z 0-9. The keyboard shortcut matches the first letter of the custom space name.


#### Jankyborders
[Jankyborders](https://github.com/FelixKratz/JankyBorders) is a lightweight tool designed to add colored borders to user windows on macOS 14.0+. It enhances the user experience by visually highlighting the currently focused window without relying on the accessibility API, thereby being faster than comparable tools.

I use it with Aerospace for highlighting the currently focused window when I have multiple tiles.

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

4. Link the oh-my-zsh themes and plugins
   ```bash
   ln -sf ~/dotfiles/.oh-my-zsh-custom/custom ~/.oh-my-zsh/custom
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

   1. Clone the repository, or
      [download](https://github.com/catppuccin/iterm/tree/main/colors) to pick and
      choose specific flavours.
   2. Launch iTerm
   3. Press CMD+i (⌘+i)
   4. Navigate to the **Colors** tab
   5. Click on **Color Presets**
   6. Click on **Import**
   7. Navigate to the directory where you downloaded the files, and select the
      files.
      \
      If you cloned the repo, they are in the `colors/` directory.
   8. Click on **Color Presets** and choose the Catppuccin flavour
   9. Enjoy! :sparkles: