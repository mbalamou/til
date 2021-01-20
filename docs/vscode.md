# Visual Studio Code

# Add CLI executable on macOS

1. Launch VS Code.
1. Open the Command Palette (⇧⌘P)
1. Type 'shell command' and then select: Shell Command: Install 'code' command in PATH

This will install an script in `/usr/local/bin/code` that can be used to open Code.

You can then create handy aliases, such as:

```
$ grep code ~/.bash_aliases
alias scratch="code --new-window ${HOME}/scratch.md"
alias til="code --new-window ${HOME}/src/github.com/andornaut/til"
```
