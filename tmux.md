## Tmux Cheatsheet

### Sessions

| command                       | action
| ---                           | ---
| `tmux`                        | start new session
| `tmux new -s myname`          | start new session with session name "myname"
| `tmux a #`                    | attach to session
| `tmux a -t myname`            | attach to named session with name "myname"
| `tmux ls`                     | list sessions
| `tmux kill-session -t myname` | kill session with name "myname"
| `tmux kill-server`            | kill all tmux open sessions and server
| `<C-b> d`                     | detach session

### Windows

| command | action
| ---|---
| `<C-b> c` | create window
| `<C-b> w` | list windows
| `<C-b> n` | next window
| `<C-b> p` | previous window
| `<C-b> f` | find window
| `<C-b> ,` | name window
| `<C-b> &` | kill window

### Panes

| command        | action
| ---            | ---
| `<C-b> %`      | vertical split
| `<C-b> "`      | horizontal split
| `<C-b> q`      | show pane numbers (when numbers show up, type the number to go to that pane)
| `<C-b> x`      | kill pane
|                |
|                |
| `<C-b>z`       | toggle pane zoom
| `<C-b>{`       | move current pane left
| `<C-b>}`       | move current pane right
| `<C-b><space>` | toggle between layouts

### Misc

| command   | action
| ---       | ---
| `<C-b> t` | big clock
| `<C-b> ?` | list shortcuts
| `<C-b> :` | prompt
| `<C-b> [` | enter copy mode
