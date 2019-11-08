# dotfiles

Based on https://www.atlassian.com/git/tutorials/dotfiles

## Prerequisites

- git

## Installation

``` shell
alias dotfiles='/usr/bin/git --git-dir=$HOME/.fotfiles/ --work-tree=$HOME'
echo ".dotfiles" >> .gitignore
git clone --bare git@github.com:dalyIsaac/dotfiles.git $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles checkout
```

For any problems, see https://www.atlassian.com/git/tutorials/dotfiles

## Adding and updating dotfiles

``` shell
dotfiles status
dotfiles add .bashrc
dotfiles commit -m "Add bashrc"
dotfiles push
```
