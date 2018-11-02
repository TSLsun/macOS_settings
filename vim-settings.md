# vim-setting
some note on setting vim on Mac terminal

Quick setting (using wget): 
```    
mkdir .vim
mkdir .vim/colors
wget -O .vimrc https://raw.githubusercontent.com/TSLsun/dotfiles/master/vim/plain.vimrc
wget -O .vim/colors/Tomorrow-Night-Bright.vim https://raw.githubusercontent.com/chriskempson/tomorrow-theme/master/vim/colors/Tomorrow-Night-Bright.vim
```    
#### [my vim dotfiles](https://github.com/TSLsun/dotfiles/tree/master/vim)


##   1. Terminal color theme: 
Tomorrow-Night-Bright.terminal 
##   2. vim:
* .vimrc

* .vim/colors/...

>>[Tomorrow-Night-Bright.vim](
https://github.com/chriskempson/tomorrow-theme/blob/master/vim/colors/Tomorrow-Night-Bright.vim)

* plugins:

>* (1) vundle https://github.com/VundleVim/Vundle.vim 

>* (2) YouCompleteMe http://valloric.github.io/YouCompleteMe/#mac-os-x         

>>```
:PluginInstall
Install CMake
```
