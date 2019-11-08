# dotfiles

Based on https://www.atlassian.com/git/tutorials/dotfiles

## Prerequisites

- git

## Installation

``` shell
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
echo ".dotfiles" >> .gitignore
git clone --bare git@github.com:dalyIsaac/dotfiles-wsl.git $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
```

To move existing dotfiles, which may block the application of the dotfiles:

``` shell
mkdir -p .old-dotfiles && \
dotfiles  checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .old-dotfiles/{}
```

### Apply the changes

``` shell
dotfiles checkout
```

Set `showUntrackedFiles` to no:

``` shell
dotfiles config --local status.showUntrackedFiles no
```

For any problems, see https://www.atlassian.com/git/tutorials/dotfiles

## Adding and updating dotfiles

``` shell
dotfiles status
dotfiles add .bashrc
dotfiles commit -m "Add bashrc"
dotfiles push
```
