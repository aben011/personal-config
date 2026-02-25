# personal-config

This repository stores my personal, unified Linux and VS Code setup.

## Installation

Clone this repo into your home directory:

#### Windows

```bash
rmdir /s /q "%USERPROFILE%\personal-config"
git clone https://github.com/aben011/personal-config.git "%USERPROFILE%\personal-config"
```

#### Linux

```bash
rm -rf "$HOME/personal-config"
git clone https://github.com/aben011/personal-config.git "$HOME/personal-config"
```

## Setup User Settings

#### Windows

> ⚠️ **Note:** Command Prompt must be run as Administrator

```bash
del "%APPDATA%\Code\User\settings.json"
mklink "%APPDATA%\Code\User\settings.json" "%USERPROFILE%\personal-config\.vscode/settings.json"
```

#### Linux

```bash
rm -f "$HOME/.config/Code/User/settings.json"
ln -s "$HOME/personal-config/.vscode/settings.json" "$HOME/.config/Code/User/settings.json"
```

#### Linux (Remote Host)

```bash
rm -f "$HOME/.vscode-server/data/Machine/settings.json"
ln -s "$HOME/personal-config/.vscode/settings.json" "$HOME/.vscode-server/data/Machine/settings.json"
```

## Setup Workspace Configuration Files

#### Linux

Link to `.vscode` files from the **workspace**:

```bash
mkdir -p ./.vscode
ln -s "$HOME/personal-config/README.md" ".vscode/README.md"
for filename in .prettierrc extensions.json; do
    rm -f ".vscode/$filename"
    ln -s "$HOME/personal-config/.vscode/$filename" ".vscode/$filename"
done
```

Link to other files from the **workspace**:

```bash
for filename in .bash_profile .bashrc; do
    rm -f "./$filename"
    ln -s "$HOME/$filename" "./$filename"
done

rm -f ./.kube_config
ln -s "$HOME/.kube/config" ./.kube_config
```

## Setup Linux config files

```bash
ln -s "$HOME/personal-config/.gitconfig" "$HOME/.gitconfig"
ln -s "$HOME/personal-config/.tmux.conf" "$HOME/.tmux.conf"
```
