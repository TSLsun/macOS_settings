# emacs-setup

April, 2020. I saw some articles and videos about moving from vim to emacs. And I want to give it a try too.

* References: [Official tutorial](https://github.com/syl20bnr/spacemacs/blob/master/doc/BEGINNERS_TUTORIAL.org#3-install-spacemacs)

## 1. Install emacs

```sh
brew cask install emacs
```

## 2. Install spacemacs

```sh
git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
```

## 3. Exploring into spacemacs

* references: [practicalli.github.io](https://practicalli.github.io/spacemacs/)

* `SPC f e d` edit `~/.spacemacs`
  `SPC f e R` update dotfile

* line number     `SPC t n`
* relative number `SPC t r`

* windows:
>  * `SPC w .` Open Window transient state menu for multiple command
>  * `SPC w 2` 2 window layout - shows current buffer in new window
>  * `SPC w m` maximise the current buffer
>  * `SPC w d` delete current window
>  * `SPC t g` toggles golden ratio view of windows

* create new file:
  1. `SPC f f` open file browser
  2. Type the filename and press `Enter`
  3. Type `y` to create the new buffer, and `SPC f s` to save the file


### useful tools

* preview markdown: `markdown-live-preview-mode` or `SPC m c P`
  (PS: make sure you `brew install markdown`) 

* ranger (add as a layer): file manager 
>  * `SPC a r` Open
>  * `q` Quit
  
