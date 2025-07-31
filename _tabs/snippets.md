---
layout: page
icon: fas fa-scroll
order: 4
---

A collection of helpful code snippets from DevEx to Implementation

## Git Aliases

#### Formatted graph commit history

```
glog = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
```

#### Set remote for current branch with same branch name

```
up = "!git branch --set-upstream-to=origin/$(git branch --show-current) $(git branch --show-current)"
```

#### Create and checkout new branch from main with given name

```
br = "!git checkout main && git pull && git checkout -b \"$1\" #"
```

Usage:

```sh
git br "my-branch-name"
```

#### Checkout and pull latest main

```
mu = "!git checkout main && git pull"
```

## Bash Profile

#### Git branch prompt - Bash

```sh
parse_git_branch() {
        git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

if [ "$color_prompt" = yes ]; then
        PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\[\033[01;31m\] $(parse_git_branch)\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
```

#### Git branch prompt - zsh

```sh
autoload -Uz vcs_info
precmd() { vcs_info }

zstyle ':vcs_info:git:*' formats '(%b)'

setopt PROMPT_SUBST
PROMPT='%F{green}%n:%f%F{blue}%~%f %F{red}${vcs_info_msg_0_}%f$ '
```

#### Always wrapped Gradle

```sh
gradle() {
    if [ -f "gradlew" ]; then
        ./gradlew $@
    else
        /usr/bin/gradle $@
    fi
}
```

#### NVM auto load

```sh
autoload -U add-zsh-hook
load-nvmrc() {
    local node_version="$(nvm version)"
    local nvmrc_path="$(nvm_find_nvmrc)"
 
   if [ -n "$nvmrc_path" ]; then
        local nvmrc_node_version=$(nvm version "$(cat "${nvmrc_path}")")
 
        if [ "$nvmrc_node_version" = "N/A" ]; then
            nvm install
        elif [ "$nvmrc_node_version" != "$node_version" ]; then
            nvm use
        fi
    elif [ "$node_version" != "$(nvm version default)" ]; then
        echo "Reverting to nvm default version"
        nvm use default
    fi
}
add-zsh-hook chpwd load-nvmrc
load-nvmrc
```

#### Lefthook auto load

```sh
autoload -U add-zsh-hook
install-lefthook() {
    if [ -f "lefthook.yml" ]; then
        if [ ! -f ".git/hooks/pre-commit" ]; then
            lefthook install
        fi
    fi
}
add-zsh-hook chpwd install-lefthook
install-lefthook
```
