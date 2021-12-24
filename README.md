On my zsh environment
>prompt -p clint
>zsh/2 13636 %F{magenta}(%fgit%F{magenta})%F{yellow}-%F{magenta}[%F{green}main%F{magenta}]%f %
So let's fix it with this one:
sudo cp prompt_clint2_setup /usr/share/zsh/functions/Prompts/prompt_clint2_setup

And in my zshrc, I have this:

# https://scriptingosx.com/2019/07/moving-to-zsh-06-customizing-the-zsh-prompt/
autoload -Uz vcs_info
precmd_vcs_info() { vcs_info }
precmd_functions+=( precmd_vcs_info )
# RPROMPT=\$vcs_info_msg_0_
zstyle ':vcs_info:git:*' formats '%F{240}(%b)%r%f'
zstyle ':vcs_info:*' enable git
