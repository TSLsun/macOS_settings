# tmux setup

## 1. Install tmux

`brew install tmux`

## 2. Setup `.tmux.conf` (some highlights)

set prefix from `C-b` to `C-a`

```tmux.conf
set -g prefix C-a
unbind C-b
bind C-a send-prefix
```

set default shell to zsh: `/usr/local/bin/zsh`

`set -g default-shell /usr/local/bin/zsh`

bind `|` to split vertically and `-` to split horizontally

```tmux.conf
bind | split-window -h
bind - split-window -v
```

## 3. tmux theme setup

---

## Issue

### tmux disregarding the configuration file

sol: make sure all the tmux windows are closed
[ref](https://superuser.com/questions/188491/tmux-disregarding-the-configuration-file)
