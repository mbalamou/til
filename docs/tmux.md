# tmux

* [Manual](https://man.openbsd.org/tmux)
* [Official Wiki](https://github.com/tmux/tmux/wiki/)
* [Arch wiki](https://wiki.archlinux.org/index.php/tmux)
* [Display formats](https://github.com/tmux/tmux/wiki/Formats)
* [Copy/paste](http://www.rushiagr.com/blog/2016/06/16/everything-you-need-to-know-about-tmux-copy-pasting-ubuntu/#comment-4242059466)

## Common commands

Command|Description
---|---
`C-b ?`|Help; list all keybindings
`C-b d`|Detach
`C-b C-b d`|[Detach inner tmux session](https://superuser.com/a/249671)
`C-b D`|List clients
`C-b [`|Enter Copy/Paste mode
`C-b ]`|Paste
`C-b 0-9`|Switch to window number
`C-b n`|Switch to the next window
`C-b p`|Switch to the previous window
`C-b q`|Print pane numbers
`C-b Up|Down|Left|Right`|Change pane focus
`C-b C-[Up|Down|Left|Right]`|Resize current pane
`C-b Alt-1`|`select-layout even-vertical
`C-b Alt-2`|`select-layout even-vertical
`C-b %`|Split pane vertically
`C-b "`|Split pane horizontally
`C-b x`|Close the current pane
`C-b &`|Close the current window
`C-b ,`|Rename the current window
`C-b $`|Rename the current session
`C-b w`|Enter [tree mode](https://github.com/tmux/tmux/wiki/Getting-Started#choosing-sessions-windows-and-panes). `x` to kill a pane/window/session
`C-b :`|Command line
`C-b :kill-[pane|server|session|window]`|Close
`C-b :new-window`|[Create](https://github.com/tmux/tmux/wiki/Getting-Started#creating-new-windows) and switch to a new window
`C-b :rename-window -n $name`|Rename current window
`C-b :split-window`|[Split](https://github.com/tmux/tmux/wiki/Getting-Started#splitting-the-window) the current window
`C-c`|Cancel

## Usage

```
$ tmux

# Detach
C-b d

$ tmux attach

# Attach to an existing session named "dev" if it exists, or create a new one if it does not
$ tmux new -As dev

$ tmux ls

# Show current setting value, eg.
$ tmux show -s status-right
```

## Troubleshooting

Problem: Meta key shortcuts do not work on macOS. Eg. `bind -n M-h select-pane -L`

Solution: Navigate to: iTerm2 > Profiles > Keys, then set "Left Option Key" to "Esc+"
