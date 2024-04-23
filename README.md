# Add node version auto-switching
Read the following for zsh integration

https://github.com/nvm-sh/nvm#zsh 

Change the command prompt
Docs - https://scriptingosx.com/2019/07/moving-to-zsh-06-customizing-the-zsh-prompt/ 

To show the following with foreground colour changes

[USER_NAME] [PWD] [GIT_BRANCH] $

Add this code towards the bottom of the .zshrc file in your user folder and change colour references as required.

# Show git branch
function parse_git_branch() {
    git branch 2> /dev/null | sed -n -e 's/^\* \(.*\)/[\1]/p'
}

setopt PROMPT_SUBST
export PROMPT='%F{13}%n %F{blue}%~ %F{10}$(parse_git_branch)%f $ '
The F stands for ‘Foreground colour.’ zsh understands the colours black, red, green, yellow, blue, magenta, cyan and white.

Blue

%F{blue}

Alternatively colours referenced by numbers could be used

https://www.ditig.com/publications/256-colors-cheat-sheet 

Fuchsia

%F{13}

Change back to the default colour

%F
