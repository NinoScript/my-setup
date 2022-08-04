# Initial Setup

* Install Homebrew (Package Manager)

    ```sh
    # Get this from `https://brew.sh/`
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

    # Make sure everything's fine
    brew doctor
    ```

* Install Fish (Shell)

    ```sh
    brew install fish
    echo (brew --prefix fish) | sudo tee -a /etc/shells
    chsh -s (brew --prefix fish)
    ```

    In `~/.config/fish/config.fish` add:
    ```sh
    # Homebrew (Package Manager)
    # output of: echo eval "\$($(brew --prefix)/bin/brew shellenv)"
    eval "$(/opt/homebrew/bin/brew shellenv)"
    ```

* Install iTerm2 (Terminal Emulator)

    ```sh
    brew install --cask iterm2
    ```

* Install Xcode

    * If not doing iOS development, install from App Store
    * If doing iOS development, download from https://developer.apple.com/download/all/

* Install the rest of my apps
    ```sh
    brew install --cask alfred
    brew install --cask discord
    brew install --cask firefox
    brew install --cask google-chrome
    brew install --cask karabiner-elements
    brew install --cask messenger
    brew install --cask openemu
    brew install --cask slack
    brew install --cask sourcetree
    brew install --cask spotify
    brew install --cask telegram
    brew install --cask textmate
    brew install --cask visual-studio-code
    brew install --cask vlc
    brew install --cask vox
    ```

* Install my mouse software
    ```sh
    brew install --cask homebrew/cask-drivers/logi-options-plus
	# Currently, this needs the installer to be run manually:
	open (brew --prefix)/Caskroom/logi-options-plus/latest/logioptionsplus_installer.app
	```

* Setup GitHub ssh keys

* Install Sourcetree's `stree` command

    * Sourcetree > Install Command Line Tools
    * If it fails:
        ```sh
        alias stree=/Applications/SourceTree.app/Contents/Resources/
        funcsave stree
        ```

* Install Visual Studio Code's `code` command

    * Shell Command: Install 'code' command in PATH

* Install Asdf (Version Manager)

    ```sh
    brew install asdf
    ```

    In `~/.config/fish/config.fish` add:
    ```sh
    # Asdf (Version Manager)
    # output of: echo -e "source "(brew --prefix asdf)"/libexec/asdf.fish"
    source /opt/homebrew/opt/asdf/libexec/asdf.fish
    ```

# Setup Development Environment

## Rust

```sh
brew install rustup
fish_add_path "$HOME/.cargo/bin"

# Enable tab completion
mkdir -p ~/.config/fish/completions
rustup completions fish > ~/.config/fish/completions/rustup.fish
```

Note: I don't install Rust with Asdf because Rustup can already do everything I need.
And thanks to Editions, I see no point in having anything but the latest version of Rust.

## Elixir

```sh
# erlang
asdf plugin-add erlang
asdf install erlang latest
asdf global erlang latest

# elixir
asdf plugin-add elixir
asdf install elixir latest
asdf global elixir latest
```

## TypeScript

```sh
# npm
asdf plugin-add nodejs
asdf install nodejs latest
asdf global nodejs latest

# yarn
asdf plugin-add yarn
brew install gpg
asdf install yarn latest
asdf global yarn latest
```

# Maintenance

```sh
# Keep things up to date
brew update; and brew upgrade; and brew cleanup

# Check that nothing's broken
brew doctor
```
