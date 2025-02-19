Here's a cheatsheet for Tmux that includes some of the most commonly used commands:

**Sessions:**

- `tmux new -s <session-name>`: Creates a new Tmux session with the specified name.
- `tmux attach -t <session-name>`: Attaches to an existing Tmux session with the specified name.
- `tmux switch -t <session-name>`: Switches to an existing Tmux session with the specified name.
- `tmux list-sessions`: Lists all active Tmux sessions.

**Windows:**

- `tmux new-window`: Creates a new Tmux window.
- `tmux select-window -t <window-number>`: Switches to the specified Tmux window.
- `tmux rename-window <new-name>`: Renames the current Tmux window.
- `tmux list-windows`: Lists all Tmux windows in the current session.

**Panes:**

- `tmux split-window`: Splits the current Tmux window into two panes.
- `tmux split-window -h`: Splits the current Tmux window horizontally.
- `tmux select-pane -t <pane-number>`: Switches to the specified Tmux pane.
- `tmux swap-pane -[UDLR]`: Swaps the current Tmux pane with the specified direction.
- `tmux kill-pane`: Closes the current Tmux pane.

**Miscellaneous:**

- `tmux detach`: Detaches from the current Tmux session.
- `tmux list-commands`: Lists all Tmux commands.
- `tmux source-file <file>`: Sources the specified Tmux configuration file.
- `tmux show-options`: Shows all Tmux options and their values.
- `tmux kill-session`: Kills the current Tmux session.
