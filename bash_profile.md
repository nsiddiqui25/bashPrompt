# Git branch in prompt.
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="[\[\033[32m\]\w]\[\033[0m\]\n\[\033[1;36m\]\u\$(parse_git_branch)\[\033[1;33m\]-> \[\033[0m\]"

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*
