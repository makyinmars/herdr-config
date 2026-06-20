# Herdr Config

Personal [Herdr](https://herdr.dev) configuration with tmux-style controls,
Vim-style navigation, and a Gruvbox Dark Hard theme matching Ghostty and
Neovim.

## Configuration

Herdr reads the configuration from:

```text
~/.config/herdr/config.toml
```

The prefix/leader is `Ctrl+L`. Prefix bindings are sequential: press and
release `Ctrl+L`, then press the action key. Press `Ctrl+L` twice to send a
literal `Ctrl+L` to the active terminal.

Reload changes without restarting Herdr:

```bash
herdr server reload-config
```

## Theme

The theme is based on Herdr's Gruvbox preset with explicit Gruvbox Dark Hard
overrides:

- Background: `#1d2021`
- Foreground: `#ebdbb2`
- Selection/surface: `#665c54` / `#3c3836`
- Yellow accent: `#d79921`
- Red: `#fb4934`
- Green: `#b8bb26`
- Blue: `#83a598`
- Purple: `#d3869b`
- Aqua: `#8ec07c`
- Orange: `#fe8019`

These values match Ghostty's bundled `Gruvbox Dark Hard` palette and the
Neovim Gruvbox hard-contrast setup.

## Keybindings

`Prefix` means `Ctrl+L`, released before the following key.

### Spaces and worktrees

| Binding | Action |
| --- | --- |
| `Prefix s` | Open the spaces/workspace picker |
| `Prefix Shift+N` | Create a new space/workspace |
| `Prefix Shift+W` | Rename the current workspace |
| `Prefix Shift+D` | Close the current workspace |
| `Prefix Shift+G` | Create a Git worktree |
| `Prefix g` | Open the searchable session navigator |
| `j` / `k` | Move down/up in the spaces picker |

### Tabs

| Binding | Action |
| --- | --- |
| `Prefix c` | Create a tab |
| `Prefix Shift+T` | Rename the current tab |
| `Prefix n` / `Prefix p` | Next/previous tab |
| `Prefix 1` … `Prefix 9` | Switch directly to a tab |
| `Prefix Shift+X` | Close the current tab |

### Panes

| Binding | Action |
| --- | --- |
| `Prefix h/j/k/l` | Focus pane left/down/up/right |
| `Prefix Shift+h/j/k/l` | Swap pane left/down/up/right |
| `Prefix %` | Split vertically |
| `Prefix "` | Split horizontally |
| `Prefix x` | Close the focused pane |
| `Prefix z` | Toggle pane zoom |
| `Prefix Tab` | Cycle to the next pane |
| `Prefix Shift+Tab` | Cycle to the previous pane |
| `Prefix Shift+P` | Rename the focused pane |
| `Prefix r` | Enter resize mode |

In resize mode, use `h/l` for width, `j/k` for height, and `Enter` or `Esc`
to finish.

### Agents

| Binding | Action |
| --- | --- |
| `Prefix .` | Focus the next agent |
| `Prefix ,` | Focus the previous agent |
| `Prefix o` | Open the latest notification target |

### Herdr controls

| Binding | Action |
| --- | --- |
| `Prefix b` | Toggle the sidebar |
| `Prefix d` | Detach while leaving the session running |
| `Prefix ?` | Show keybinding help |
| `Prefix Shift+S` | Open settings |
| `Prefix Shift+R` | Reload the configuration |
| `Prefix e` | Edit pane scrollback |
| `Prefix [` | Enter keyboard copy mode |

### Copy mode

| Binding | Action |
| --- | --- |
| `h/j/k/l` | Move the cursor |
| `w/b/e` | Move by words |
| `{` / `}` | Move by paragraphs |
| `v` or `Space` | Start a selection |
| `y` or `Enter` | Copy the selection |
| `q` or `Esc` | Exit copy mode |

## Installation

For a new machine:

```bash
git clone git@github.com:makyinmars/herdr-config.git ~/.config/herdr
herdr server reload-config
```

If Herdr has already created the directory, clone elsewhere and copy
`config.toml` into `~/.config/herdr/`.

Herdr's runtime session files, logs, and Unix sockets are intentionally ignored
by Git.

## Requirements

- Herdr 0.7.0 or newer
- A terminal that can distinguish the configured modified key chords

