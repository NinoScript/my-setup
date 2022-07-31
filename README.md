# Initial Setup

* Install Homebrew

    ```sh
    # Get this from `https://brew.sh/`
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

    # Make sure everything's fine
    brew doctor
    ```

* Install Fish, my favorite shell

    ```sh
    brew install fish
    echo /opt/homebrew/bin/fish | sudo tee -a /etc/shells
    chsh -s /opt/homebrew/bin/fish
    ```

    In `~/.config/fish/config.fish` add:
    ```sh
    eval "$(/opt/homebrew/bin/brew shellenv)"
    ```

* Install iTerm2, my favorite terminal emulator

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

* Install Rust

    ```sh
    brew install rustup
    ```

    In `~/.config/fish/config.fish` add:
    ```sh
    set -gx PATH "$HOME/.cargo/bin" $PATH
    ```

# Maintenance

```sh
# Keep things up to date
brew update; and brew upgrade; and brew cleanup

# Check that nothing's broken
brew doctor
```
