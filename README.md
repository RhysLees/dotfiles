# My personal dotfiles

My personal dotfiles. Also used by nearly all other geeks at [spatie.be](http://spatie.be) and [the amazing Frederick Vanbrabant](https://twitter.com/maybeFrederick/status/912620087538016257).

It contains the installation of some basic tools, some handy aliases and functions. Backups of settings are done via [Mackup](https://github.com/lra/mackup).

## Requirements

- macOS (tested on macOS Sonoma and later)
- Administrator access (for Homebrew installation and system configuration)
- Dropbox (optional, for Mackup backups)

## Installation

You can install them by cloning the repository as `.dotfiles` in your home directory and running the bootstrap script.

```bash
git clone git@github.com:rhyslees/dotfiles.git .dotfiles
cd .dotfiles
./bootstrap
```

The bootstrap script will:
1. Install oh-my-zsh
2. Set up shell configuration (zsh, vim)
3. Install Homebrew and all required packages
4. Configure npm, PHP, Composer, and other development tools
5. Set up symlinks for configuration files

## Installed Tools

### Development Tools
- **Node.js** - Managed via `fnm` (Fast Node Manager)
- **PHP 8.3** - Via Homebrew tap
- **Composer** - PHP dependency manager
- **MySQL** - Database server
- **Yarn** - JavaScript package manager
- **Git** - Version control (with GitHub CLI)

### Modern CLI Tools
- **gh** - GitHub CLI (replaces deprecated `hub`)
- **rg** (ripgrep) - Fast text search
- **fd** - Modern `find` alternative
- **bat** - Modern `cat` with syntax highlighting
- **eza** - Modern `ls` alternative
- **fzf** - Fuzzy finder
- **zoxide** - Smart directory jumping (alternative to `z.sh`)

### Utilities
- **httpie** - HTTP client
- **ncdu** - Disk usage analyzer
- **wget** - File downloader
- **doctl** - DigitalOcean CLI
- **git-secret** - Git encryption
- **mackup** - Application settings backup
- **zsh-autosuggestions** - Zsh plugin

### Laravel/PHP Tools
- **Laravel Valet** - Local development environment
- **Laravel Envoy** - Task runner
- **PHPUnit Watcher** - Test watcher
- **aicommits** - AI-powered commit messages

### Quick Look Plugins
- qlcolorcode, qlstephen, qlmarkdown, quicklook-json, qlprettypatch, quicklook-csv, betterzip, suspicious-package

## Configuration Files

- `shell/.zshrc` - Zsh configuration
- `shell/.vimrc` - Vim configuration
- `shell/.aliases` - Shell aliases
- `shell/.functions` - Shell functions
- `shell/.exports` - Environment variables
- `macos/set-defaults.sh` - macOS system defaults
- `macos/.mackup.cfg` - Mackup configuration

## Using Brewfile

For easier dependency management, you can use the included `Brewfile`:

```bash
brew bundle
```

This will install all Homebrew packages and casks listed in the Brewfile.

## Post-Installation

After running the bootstrap script:

1. **Install terminal font**: Install the Menlo Powerline font from `~/.dotfiles/misc/Menlo-Powerline.otf`
2. **Install terminal theme**: Install the Solarized Dark theme from `~/.dotfiles/misc`
3. **Run Mackup** (if using Dropbox):
   - First time: `mackup backup`
   - Restore existing: `mackup restore`
4. **Set macOS defaults**: Run `~/.dotfiles/macos/set-defaults.sh`
5. **Create custom aliases** (optional): Create `~/.dotfiles-custom/shell/.aliases` for personal commands

## Troubleshooting

### Node.js not found
After installation, you may need to install a Node version:
```bash
fnm install --lts
fnm use --install-if-missing
```

### PHP not found
Ensure PHP is linked:
```bash
brew link --overwrite --force php@8.3
```

### GitHub CLI authentication
After installation, authenticate with GitHub:
```bash
gh auth login
```

### Terminal theme not working
Make sure you've installed the Menlo Powerline font and set it as your terminal font.

## Customization

You can add custom configuration files that won't be committed:
- `~/.dotfiles-custom/shell/.aliases`
- `~/.dotfiles-custom/shell/.functions`
- `~/.dotfiles-custom/shell/.exports`
- `~/.dotfiles-custom/shell/.zshrc`

These files are automatically sourced by the main `.zshrc`.

## License

Feel free to use and modify these dotfiles for your own use.

![screenshot](https://freekmurze.github.io/dotfiles/screenshot.png)
