# vscode-config

This repository stores my personal, unified VS Code setup.

## Installation

Clone this repo into your home directory:

#### Windows

```bash
rmdir /s /q "%USERPROFILE%\vscode-config"
git clone https://github.com/aben011/vscode-config.git "%USERPROFILE%\vscode-config"
```

#### Linux

```bash
rm -rf "$HOME/vscode-config"
git clone https://github.com/aben011/vscode-config.git "$HOME/vscode-config"
```

## Setup User Settings

#### Windows

> ⚠️ **Note:** Command Prompt must be run as Administrator

```bash
del "%APPDATA%\Code\User\settings.json"
mklink "%APPDATA%\Code\User\settings.json" "%USERPROFILE%\vscode-config\settings.json"
```

#### Linux (Remote Host)

```bash
rm -f "$HOME/.vscode-server/data/Machine/settings.json"
ln -s "$HOME/vscode-config/settings.json" "$HOME/.vscode-server/data/Machine/settings.json"
```

## Setup Workspace Configuration Files

#### Linux

Link to `.vscode` files from the **workspace**:

```bash
mkdir -p ./.vscode
for filename in .prettierrc extensions.json README.md; do
    rm -f ".vscode/$filename"
    ln -s "$HOME/vscode-config/$filename" ".vscode/$filename"
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
