# vscode-config
This repository stores my personal, unified VS Code setup.

## Installation (Linux/MacOS)
Clone repo into Home directory:
```bash
git clone https://github.com/aben011/vscode-config.git $HOME
```

Link to files from workspace (`.vscode` directory must exist)
```bash
rm -f ./.vscode/extensions.json && \
rm -f ./.vscode/settings.json && \
ln -s $HOME/vscode-config/extensions.json ./.vscode/extensions.json && \
ln -s $HOME/vscode-config/settings.json ./.vscode/settings.json
```
