# VSCode Config (when VSCode's sync isn't enough)

This repository contains the configuration files for my Visual Studio Code (VSCode) that includes:

- settings
- theme
- keybindings
- extensions

# Setup

First, make sure VSCode is installed and opened at least once. Now close VSCode and follow the instructions below.

For Linux:

```sh
# If needed, create a backup of the existing configs
mv ~/.config/Code/User/settings.json ~/.config/Code/User/settings.json.bak
mv ~/.config/Code/User/keybindings.json ~/.config/Code/User/keybindings.json.bak

# Clone this repo
mkdir -p ~/Code
git clone git@github.com:habibium/vscode-config.git ~/Code/vscode-config

# Copy the files
cp ~/Code/vscode-config/settings.json ~/.config/Code/User/settings.json
cp ~/Code/vscode-config/keybindings.json ~/.config/Code/User/keybindings.json
cp ~/Code/vscode-config/extensions.json ~/.vscode/extensions/extensions.json

# Or, if you prefer symlinks
ln -sf ~/Code/vscode-config/settings.json ~/.config/Code/User/settings.json
ln -sf ~/Code/vscode-config/keybindings.json ~/.config/Code/User/keybindings.json
ln -sf ~/Code/vscode-config/extensions.json ~/.vscode/extensions/extensions.json
```

For MacOS:

```sh
# If needed, create a backup of the existing configs
mv ~/Library/Application\ Support/Code/User/settings.json ~/Library/Application\ Support/Code/User/settings.json.bak
mv ~/Library/Application\ Support/Code/User/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json.bak

# Clone this repo
mkdir -p ~/Code
git clone git@github.com:habibium/vscode-config.git ~/Code/vscode-config

# Copy the files
cp ~/Code/vscode-config/settings.json ~/Library/Application\ Support/Code/User/settings.json
cp ~/Code/vscode-config/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
cp ~/Code/vscode-config/extensions.json ~/.vscode/extensions/extensions.json

# Or, if you prefer symlinks
ln -sf ~/Code/vscode-config/settings.json ~/Library/Application\ Support/Code/User/settings.json
ln -sf ~/Code/vscode-config/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
ln -sf ~/Code/vscode-config/extensions.json ~/.vscode/extensions/extensions.json
```

For Windows:

Simply copy the files and replace the existing ones of VSCode.

### Extension Installation Script

You need to have [jq](https://jqlang.github.io/jq/) installed on your system

```sh
cat ~/vscode-config/extensions.json | jq '.[].identifier.id' | xargs -n 1 code --install-extension
```
