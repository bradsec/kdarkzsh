# MacOS and Debian ZSH configuration and dotfiles

## MacOS Usage
> kdark.terminal colour scheme combined with the kdark.zshrc for a zsh prompt and appearance in MacOS terminal similar to Kali linux.  

![kdark.terminal](/previewmacos.png)

#### Requirements for theme and .zshrc 
`zsh-syntax-highlighting`, `zsh-autosuggestions` and `Fira Code font`.

These can be installed manually or using Homebrew:

```sh
brew install zsh-syntax-highlighting
brew install zsh-autosuggestions
brew tap homebrew/cask-fonts
brew install --cask font-fira-code
```
`kdark.terminal` is a colour theme for the default MacOS terminal application. 

- Download [kdark.terminal](https://github.com/bradsec/zsh/blob/main/kdark.terminal).
```sh
wget -O ~/Desktop/kdark.terminal https://raw.githubusercontent.com/bradsec/zsh/main/kdark.terminal
```
- Double click on kdark.terminal file. It will open a new Terminal window with the kdark color theme. This theme will also now be in the Preferences themes.
  - Alternatively open the terminal.app and go into the preferences and import the kdark.terminal color scheme. 
- Make the imported colour scheme the Default.  
- Download [kdark.zshrc](https://github.com/bradsec/zsh/blob/main/kdark.zshrc) and rename as `.zshrc` in the user home path `~/.zshrc`.  
```sh
wget -O ~/.zshrc https://raw.githubusercontent.com/bradsec/zsh/main/kdark.zshrc
```
- Logout or reload the .zshrc by running `source ~/.zshrc`


## Debian Console Usage (No xDesktop)
1. Install zsh shell, zsh-syntax-highlighting and zsh-autosuggestions
```sh
sudo apt -y install zsh zsh-syntax-highlighting zsh-autosuggestions
```
2. Change default user shell to zsh (don't use sudo)  
```sh
chsh -s $(which zsh)
```
3. Check current user shell
```sh
ps -p $$
```
4. Download [debian.zshrc](https://github.com/bradsec/zsh/blob/main/debian.zshrc) and rename as `.zshrc` in the user home path `~/.zshrc`.  
```sh
wget -O ~/.zshrc https://raw.githubusercontent.com/bradsec/zsh/main/debian.zshrc
```
5. Logout or reload the .zshrc by running `source ~/.zshrc`  
  - Sometimes `source .zshrc` does not cause shell changes to take affect. In this case logout and log back in.  

#### Change console font
Manually change by running the following command:  
```sh
`sudo dpkg-reconfigure console-setup`
```
- Try TerminusBold 10x18 or VGA 8x16

Quick change:
```sh
sudo tee /etc/default/console-setup <<'EOF'
# CONFIGURATION FILE FOR SETUPCON

# Consult the console-setup(5) manual page.

ACTIVE_CONSOLES="/dev/tty[1-6]"

CHARMAP="UTF-8"

CODESET="guess"
FONTFACE="TerminusBold"
FONTSIZE="10x18"

VIDEOMODE=
EOF
```
Alternative VGA font
```sh
sudo tee /etc/default/console-setup <<'EOF'
# CONFIGURATION FILE FOR SETUPCON

# Consult the console-setup(5) manual page.

ACTIVE_CONSOLES="/dev/tty[1-6]"

CHARMAP="UTF-8"

CODESET="guess"
FONTFACE="VGA"
FONTSIZE="8x16"

VIDEOMODE=
EOF
```

![debian.console](/previewdebian.png)
