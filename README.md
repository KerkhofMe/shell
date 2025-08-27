# Oh-My-Zsh — Recommended Plugins

Overview
- This file lists recommended Oh My Zsh plugins and the exact git clone commands to install them.
- After installing the plugins, enable them by updating the `plugins=(...)` line in your `~/.zshrc` and reloading your shell.

Plugins (purpose + install commands)

1. zsh-autosuggestions — provides typing suggestions as you type
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

2. zsh-syntax-highlighting — adds syntax highlighting in the shell
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

3. fast-syntax-highlighting — alternative/complimentary syntax highlighting (faster)
```bash
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```

4. zsh-autocomplete — intelligent autocompletion
```bash
git clone --depth 1 https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
```

Note: `$ZSH_CUSTOM` is usually set by Oh My Zsh; the fast-syntax command uses a fallback `${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}` if it's not defined.

Activate (update your `~/.zshrc`)
- Open your `~/.zshrc` in an editor:
```bash
nvim ~/.zshrc
# or
nano ~/.zshrc
```
- Find the line that starts with:
```text
plugins=(git)
```
- Replace or update it to:
```text
plugins=(git zsh-autosuggestions zsh-syntax-highlighting fast-syntax-highlighting zsh-autocomplete)
```
- Reload your shell:
```bash
source ~/.zshrc
```

Quick checks to verify installations
```bash
ls -1 $ZSH_CUSTOM/plugins | sed -n '1,200p'
# or check each plugin folder, e.g.:
test -d "$ZSH_CUSTOM/plugins/zsh-autosuggestions" && echo "zsh-autosuggestions OK"
```

Common issues
- `$ZSH_CUSTOM` is empty: use the fallback path shown above in the fast-syntax command.
- Plugins don't appear to work: ensure you ran `source ~/.zshrc` and check for errors in your `~/.zshrc`.
- Some plugins require additional setup—see each plugin's README for extra configuration steps.

Optional automation (for advanced users)
- I can add a safe script that runs the clone commands and updates the `plugins=` line in `~/.zshrc`. Tell me if you want that.

Sources / license
- Plugin sources: external GitHub repositories (see the clone URLs above).