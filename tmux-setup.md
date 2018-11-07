# tmux setup

## 1. Install tmux

`brew install tmux`

## 2. Setup `.tmux.conf` (some highlights)

set prefix from `C-b` to `C-a`

```
set -g prefix C-a
unbind C-b
bind C-a send-prefix
```

set default shell to zsh: `/usr/local/bin/zsh`

`set -g default-shell /usr/local/bin/zsh` 

bind `|` to split vertically and `-` to split horizontally

```
bind | split-window -h
bind - split-window -v
```

## 3. tmux theme setup
