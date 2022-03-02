# terminal
MacOS and Linux Terminal related files and dotfiles

## MacOS Usage
kdark.terminal color scheme combined with the kdark.zshrc for a terminal zsh prompt and appearance in MacOS similar to Kali linux.  
![kdark.terminal](/previewmacos.png)

`kdark.terminal` is a color scheme for the default MacOS terminal application. Download `kdark.terminal` and open to import. Alternative open terminal.app and go into the preferences and import the kdark.terminal color scheme.

`kdark.zshrc` copy and rename as `.zshrc` in the user home path `~/.zshrc`.

#### `.zshrc` uses `zsh-syntax-highlighting`, `zsh-autosuggestions.zsh` and `Fira Code font`.

These can be installed manually or using Homebrew:

```
brew install zsh-syntax-highlighting
brew install zsh-autosuggestions
brew tap homebrew/cask-fonts
brew install --cask font-fira-code
```
