# ZSH Setup

zsh + antigen + oh-my-zsh

[my .zshrc file](https://github.com/TSLsun/dotfiles/blob/master/zsh/zshrc)

## 1. Install **zsh** and **antigen**

### 1.1. Install zsh

```shell
brew install zsh
```

then set terminal default shell to zsh
`/usr/local/bin/zsh/`

or macOS也有內建，切換shell：

```sh
chsh -s /bin/zsh
```

### 1.2. Install antigen for plugins management

```shell
curl -L git.io/antigen > antigen.zsh
```

## 2. Setup `~/.zshrc`

### 2.1. antigen [github](https://github.com/zsh-users/antigen)

官方初始建議

```zsh
# Load Antigen
source /path-to-antigen/antigen.zsh

# Load the oh-my-zsh's library.
antigen use oh-my-zsh

# Bundles from the default repo (robbyrussell's oh-my-zsh).
antigen bundle git
antigen bundle heroku
antigen bundle pip
antigen bundle lein
antigen bundle command-not-found

# Syntax highlighting bundle.
antigen bundle zsh-users/zsh-syntax-highlighting

# Load the theme.
antigen theme robbyrussell

# Tell Antigen that you're done.
antigen apply
```

### 2.2. Theme

在 `/path-to-oh-my-zsh/themes` 裡有一些預設的theme可以直接使用

eg. `agnoster`, `robbyrussell`, `ys` 這幾個是我比較可以接受的

在zshrc中加入：

```zsh
antigen theme robbyrussell
```

當然也可以載入其他的，像是 `powerlevel10k` ([github link](https://github.com/romkatv/powerlevel10k))

```zsh
antigen theme romkatv/powerlevel10k
```

#### Some Extra settings for theme

* Remove device name & user name

    ```zsh
    export DEFAULT_USER=$USER
    ```

* Customize powerlevel10k prompt

    ```zsh
    # To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
    [[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
    ```

* Install `nerd-font` to show all kinds of **icons** ([official instructions](https://github.com/ryanoasis/nerd-fonts#font-installation))

    For macOS (install hack):

    ```zsh
    brew tap homebrew/cask-fonts
    # install `Hack` for example
    brew cask install font-hack-nerd-font
    ```

### 2.3. add PATH

Copy the PATH from bash shell, my settings for example:

```zsh
# If you come from bash you might have to change your $PATH.

export PATH=$HOME/bin:/Library/Frameworks/Python.framework/Versions/3.6/bin:$HOME/miniconda3/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:$HOME/.local/bin:$PATH
```

### 2.4. alias

move aliases into a file name `.aliases` and then source the file:

```zsh
source ~/.aliases
```

### 2.5. some setup for other packages like `conda`, `nvm`

### 2.6. more plugins

* some useful plugins from `zsh-users` repo

    ```zsh
    antigen bundle zsh-users/zsh-completions
    antigen bundle zsh-users/zsh-autosuggestions
    antigen bundle zsh-users/zsh-syntax-highlighting
    ```

* `autojump` installed by brew

    ```zsh
    brew install autojump
    ```

    then add to zshrc:  

    ```zsh
    antigen bundle autojump
    ```
