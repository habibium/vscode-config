# VSCode Config

This repository contains the configuration files for my Visual Studio Code (VSCode) that includes:

- settings
- theme
- keybindings
- extensions

# Setup

For Linux:

```sh
# For extra safety, create a backup of the existing configs
mv ~/.config/Code/User/settings.json ~/.config/Code/User/settings.json.bak
mv ~/.config/Code/User/keybindings.json ~/.config/Code/User/keybindings.json.bak
mv ~/.vscode/extensions/extensions.json ~/.vscode/extensions/extensions.json.bak

# Clone this repo
git clone git@github.com:HabibMollah/vscode-config.git ~/vscode-config

# Copy the files
cp ~/vscode-config/settings.json ~/.config/Code/User/settings.json
cp ~/vscode-config/keybindings.json ~/.config/Code/User/keybindings.json
cp ~/vscode-config/extensions.json ~/.vscode/extensions/extensions.json

# Or, if you prefer symlinks
ln -s ~/vscode-config/settings.json ~/.config/Code/User/settings.json
ln -s ~/vscode-config/keybindings.json ~/.config/Code/User/keybindings.json
ln -s ~/vscode-config/extensions.json ~/.vscode/extensions/extensions.json
```

For MacOS:

```sh
# For extra safety, create a backup of the existing configs
mv ~/Library/Application\ Support/Code/User/settings.json ~/Library/Application\ Support/Code/User/settings.json.bak
mv ~/Library/Application\ Support/Code/User/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json.bak
mv ~/.vscode/extensions/extensions.json ~/.vscode/extensions/extensions.json.bak

# Clone this repo
git clone git@github.com:HabibMollah/vscode-config.git ~/vscode-config

# Copy the files
cp ~/vscode-config/settings.json ~/Library/Application\ Support/Code/User/settings.json
cp ~/vscode-config/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
cp ~/vscode-config/extensions.json ~/.vscode/extensions/extensions.json

# Or, if you prefer symlinks
ln -s ~/vscode-config/settings.json ~/Library/Application\ Support/Code/User/settings.json
ln -s ~/vscode-config/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
ln -s ~/vscode-config/extensions.json ~/.vscode/extensions/extensions.json
```

For Windows:

Simply copy the files and replace the existing ones of VSCode.

### Extension Installation Script

You need to have [jq](https://jqlang.github.io/jq/) installed on your system

```sh
cat ~/vscode-config/extensions.json | jq '.[].identifier.id' | xargs -n 1 code --install-extension
```
