# vim-setting
some note on setting vim on Mac terminal

Quick setup without plugins (using wget): 
```    
mkdir .vim
mkdir .vim/colors
wget -O .vimrc https://raw.githubusercontent.com/TSLsun/dotfiles/master/vim/plain.vimrc
wget -O .vim/colors/Tomorrow-Night-Bright.vim https://raw.githubusercontent.com/chriskempson/tomorrow-theme/master/vim/colors/Tomorrow-Night-Bright.vim
```    

## .vimrc

[my vim dotfiles](https://github.com/TSLsun/dotfiles/tree/master/vim)

## .vim/colors/...

[Tomorrow-Night-Bright.vim](https://github.com/chriskempson/tomorrow-theme/blob/master/vim/colors/Tomorrow-Night-Bright.vim)

## Plugins:

#### 1. [vundle](https://github.com/VundleVim/Vundle.vim) as plugin manger

Set up vundle:
```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

`so %` to source `.vimrc` after adding new plugins 

run `:PluginInstall` to install plugins

#### 2. [YouCompleteMe](http://valloric.github.io/YouCompleteMe/#mac-os-x) for code autocompletion 

Install CMake

Compiling YCM with semantic support for C-family languages:

```
cd ~/.vim/bundle/YouCompleteMe
/usr/local/Cellar/python/3.7.1/bin/python3 ./install.py --clang-completer
```

Setup in .vimrc:
```
" YouCompleteMe settings"
let g:ycm_server_keep_logfiles = 1
let g:ycm_server_log_level = 'debug'
let g:ycm_path_to_python_interpreter='/usr/local/Cellar/python/3.7.1/bin/python3'

" add anaconda3 envs, remember to `source activate envs`"
let g:ycm_python_binary_path = '/anaconda3/bin/python3'
let g:ycm_python_binary_path = '/anaconda3/envs/DataScience/bin/python3'
let g:ycm_global_ycm_extra_conf = "~/.ycm_extra_conf.py"
let g:ycm_autoclose_preview_window_after_completion = 1
map <leader>g  :YcmCompleter GoToDefinitionElseDeclaration<CR>
```

#### 3. [fzf](https://github.com/junegunn/fzf) look for files to open

`:FZF` look for files under current folder

`:FZF ~` look for files under home directory 

`:FZF!` starts fzf in fullscreen mode

`Ctrl-T`, `Ctrl-X`, `Ctrl-V` to open files in new tabs, horizontal splits or in vertical splits.

#### 4. [nerdtree](https://github.com/scrooloose/nerdtree) a tree explorer plugin for vim

Setup in .vimrc:
```
"Open NERDTree with Ctrl-n"
map <C-n> :NERDTreeToggle<CR>

"close vim if NERDTree left open"
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

"fix to show first letter"
let NERDTreeNodeDelimiter = "\t"
```

#### 5. [nerdcommenter](https://github.com/scrooloose/nerdcommenter) make comments easier

`[count]<leader>c<space>` NERDComToggleComment

`[count]<leader>ci` NERDComInvertComment

`<leader>cA` Add comment at the end of the line

#### 6. [surround.vim](https://github.com/tpope/vim-surround) to deal with surroundings

`cs"'` change surroundings from `"` to `'`

`ysiw]` add surroundings `[]` (`iw` is a text object)

`ds{` delete surroundings `{}` 

#### 7. [repeat.vim](https://github.com/tpope/vim-repeat) `.` works for surround.vim

#### 8. Plugins for Markdown support and preview:

[tabular](https://github.com/godlygeek/tabular)

[vim-markdown](https://github.com/plasticboy/vim-markdown)

[markdown-preview](https://github.com/iamcco/markdown-preview.vim)



---
#### To try list:

[vim-multiple-cursors](https://github.com/terryma/vim-multiple-cursors)

[tagbar](https://github.com/majutsushi/tagbar)

[fugitive](https://github.com/tpope/vim-fugitive)

