# zsh setup

## 1. Install zsh and oh-my-zsh

### 1.1. Install zsh:
`brew install zsh`

### 1.2. Install oh-my-zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

set terminal default shell to zsh `/usr/local/bin/zsh/`

## 2. Setup .zshrc

### 2.1. 切換 theme

在 `~/.oh-my-zsh/themes` 裡有一些預設的theme可以直接使用

eg. `ZSH_THEME="agnoster"`

### 2.2. Remove device name & user name

加入 `export DEFAULT_USER=$USER` 

### 2.3. add PATH

Copy the PATH from bash shell, my settings for example:

```
/Library/Frameworks/Python.framework/Versions/3.6/bin:/anaconda3/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```

### 2.4. add alias copied from .bash_profile

move aliases to a file name `.aliases` and then source the file:

```
source ~/.aliases
```
