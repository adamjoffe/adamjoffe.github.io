---
# the default layout is 'page'
icon: fas fa-scroll
order: 3
---

A collection of helpful code snippets from DevEx to Implementation


## Git Aliases

Formatted graph commit history
```
glog = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
```

## Bash Profile

Git branch prompt
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

Always wrapped Gradle
```sh
gradle() {
    if [ -f "gradlew" ]; then
        ./gradlew $@
    else
        /usr/bin/gradle $@
    fi
}
```
