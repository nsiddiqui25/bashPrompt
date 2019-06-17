`PS1="[\[\033[32m\]\w]\[\033[0m\]\n\[\033[1;36m\]\u\[\033[1;33m\]=> \[\033[0m\]"

nano ~/.bash_profile
PS1="[\[\033[32m\]\w]\[\033[0m\]\n\[\033[1;36m\]n00b => \[\033[0m\]"
source ~/.bash_profile`


# Git branch in prompt.
`parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="[\[\033[32m\]\w]\[\033[0m\]\n\[\033[1;36m\]\u\$(parse_git_branch)\[\033[1;33m\]-> \[\033[0m\]"

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*`


# Git branch in prompt.
`parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="[\[\033[32m\]\w]\[\033[0m\]\n\[\033[1;36m\]n00b\$(parse_git_branch) \[\033[1;33m\]=> \[\033[0m\]"

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*`



# bash_profile for work

`# Git branch in prompt.
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

# Bash completion
if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi

# Prompt (set before autojump)
export PROMPT_COMMAND=__prompt_command

# Autojump
[[ -s `brew --prefix`/etc/autojump.sh ]] && . `brew --prefix`/etc/autojump.sh

# Default editor
export EDITOR=nano
# export EDITOR=vim

# Colours for ls and grep
alias ls="ls -G"
alias grep="grep --color=always"

# Useful Telogis Web Marketing shortcuts
alias sd="script/deploy"
alias ss="script/server"

# Prompt format
function __prompt_command() {
    # Must be first
    local EXIT="$?"

    local ResetColour='\[\e[0m\]'
    local Red='\[\e[0;31m\]'
    local Green='\[\e[0;32m\]'

    PS1='\W $(parse_git_branch "\[\e[34m\]%s\[\e[0m\] ")'

    # Red if the last command didn't exit properly
    if [ $EXIT != 0 ]; then
        PS1+="${Red}"
    else
        PS1+="${Green}"
    fi

    PS1+="\$ ${ResetColour}"
}`


# bash_profile for work - including Ruby

`# Git branch in prompt.
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

# Bash completion
if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi

# Prompt (set before autojump)
export PROMPT_COMMAND=__prompt_command

# Autojump
[[ -s `brew --prefix`/etc/autojump.sh ]] && . `brew --prefix`/etc/autojump.sh

# Default editor
export EDITOR=nano
# export EDITOR=vim

# Colours for ls and grep
alias ls="ls -G"
alias grep="grep --color=always"

# Useful Telogis Web Marketing shortcuts
alias sd="script/deploy"
alias ss="script/server"

# Prompt format
function __prompt_command() {
    # Must be first
    local EXIT="$?"

    local ResetColour='\[\e[0m\]'
    local Red='\[\e[0;31m\]'
    local Green='\[\e[0;32m\]'

    PS1='\W $(parse_git_branch "\[\e[34m\]%s\[\e[0m\] ")'

    # Red if the last command didn't exit properly
    if [ $EXIT != 0 ]; then
        PS1+="${Red}"
    else
        PS1+="${Green}"
    fi

    PS1+="\$ ${ResetColour}"
}

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*

source ~/.rvm/scripts/rvm`
