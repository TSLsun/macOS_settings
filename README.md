# macOS environment setup

[some issues & solution](https://github.com/TSLsun/macOS_settings/blob/master/issue-sol.md)

[My dotfiles](https://github.com/TSLsun/dotfiles)

## Step 1: Install Homebrew

macOS 套件的管理工具

`xcode-select --install`

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Step 2: Install cask

用 `brew cask` 來安裝應用程式要先執行:
`brew install cask` or
`brew tap caskroom/cask`

用 homebrew 安裝字型要先執行：
`brew tap caskroom/fonts`

## Step 3: Install git

`brew install git`

[將預設 Git 改為 Homebrew 版本](https://garynil.tw/2018/05/762/%E5%A6%82%E4%BD%95%E4%BB%A5-homebrew-%E5%8F%96%E4%BB%A3-macos-%E5%85%A7%E5%BB%BA-git-%E4%B8%A6%E6%9B%B4%E6%96%B0/)

## Step 4: Install vim, tmux, zsh

`brew install vim tmux zsh`

[My vim setup](https://github.com/TSLsun/macOS_settings/blob/master/vim-setup.md)

[My zsh setup](https://github.com/TSLsun/macOS_settings/blob/master/zsh-setup-antigen.md)

## Install iTerm2, wget

`brew cask install iterm2`

`brew install wget`

iTerm2 setup color: [iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes/tree/master/schemes)

eg. download Tomorrow-Night-Bright (save at projects/iTerm2-Color-Schemes/schemes/):

```shell
wget -O  "Tomorrow Night Bright.itermcolors" https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/Tomorrow%20Night%20Bright.itermcolors
```

then import it.

Set zsh to be iTerm2 default shell:

a. Go to iTerm2 preferences.

b. Head to Profiles -> General.

c. Paste /bin/zsh in the Command textbox and restart iTerm2.

## Step 5: Install powerline

powerline是一個python套件

5.1. Install powerline-status

```shell
pip install powerline-status
```

.bash_profile 設定加入(python路徑可能不一樣)：

```shrc
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /usr/local/lib/python3.6/site-packages/powerline/bindings/bash/powerline.sh
```

my settings:

```shrc
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /anaconda3/lib/python3.6/site-packages/powerline/bindings/bash/powerline.sh
```

5.2. font setup:

```shell
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

再去terminal設定那邊更改字型

5.3. To show gitstatus: [ref](https://medium.freecodecamp.org/jazz-up-your-bash-terminal-a-step-by-step-guide-with-pictures-80267554cb22)

```shell
pip install powerline-gitstatus
```

my powerline-install-directory: `/anaconda3/lib/python3.6/site-packages/`

add some lines into:
`${powerline-install-directory}/powerline/config_files/colorschemes/shell/default.json`

add the following lines into
`${powerline-install-directory}/powerline/config_files/themes/shell/default.json`:

```json
{
    "function": "powerline_gitstatus.gitstatus",
    "priority": 40
}
```

after edit above, save the file and run the following:

`powerline-daemon —-replace` in the Terminal.

5.4. vim setup:

add follow lines to `.vimrc`:

```vimrc
set rtp+={powerline-install-directory}/powerline/bindings/vim/
set laststatus=2
set t_Co=256
```

5.5. tmux setup:

add follow line to `.tmux.conf`:

```tmux.conf
source '{powerline-install-directory}/powerline/bindings/tmux/powerline.conf'
```

5.6. zsh setup:

add follow line to `.zshrc`:

```zshrc
{powerline-install-directory}/powerline/bindings/zsh/powerline.zsh
```
