# macOS 
## Step 1: install Homebrew
macOS 套件的管理工具

``
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
``

## Step 2: install cask
用 `brew cask` 來安裝應用程式要先執行:
`brew install cask` or 
`brew tap caskroom/cask`

用 homebrew 安裝字型要先執行：
`brew tap caskroom/fonts`

## Step 3: install git

`brew install git`

[將預設 Git 改為 Homebrew 版本](https://garynil.tw/2018/05/762/%E5%A6%82%E4%BD%95%E4%BB%A5-homebrew-%E5%8F%96%E4%BB%A3-macos-%E5%85%A7%E5%BB%BA-git-%E4%B8%A6%E6%9B%B4%E6%96%B0/)

## Step 4: install vim, tmux, zsh
`brew install vim tmux zsh`

##Install iTerm2, wget:

`brew cask install iterm2`

`brew install wget`

## Step 5: install powerline
```
pip install powerline-status
```

.bash_profile 設定加入(python路徑可能不一樣)：
```
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /usr/local/lib/python3.6/site-packages/powerline/bindings/bash/powerline.sh
``` 
my settings:
```
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /anaconda3/lib/python3.6/site-packages/powerline/bindings/bash/powerline.sh
```
font settings:
```
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
