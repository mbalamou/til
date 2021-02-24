# tmux

* [Manual](https://man.openbsd.org/tmux)
* [Wiki](https://github.com/tmux/tmux/wiki/)


## Common commands

Command|Description
---|---
`C-b ?`|help
`C-b d`|detach
`C-b :`|command line
`C-b :kill-server`|stop server
`C-c`|cancel

## Usage

```
$ tmux

C-b d # detach

$ tmux attach


# Attach to an existing session named "dev" if it exists, or create a new one if it does not
$ tmux new -As dev

$ tmux ls
```
