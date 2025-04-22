# Configuracion zsh 

> **Descripción breve:**  
Este documento contiene mi configuracion personal de zsh, actualizada a dia de hoy.

- **Fecha de modificación:** 22-04-2025
- **Autor:** Neira9919

---

## Configuracion

```
# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# Path al Zsh
export SHELL=/bin/zsh
export EDITOR=nano

# HISTORIA
HISTFILE=~/.zsh_history
HISTSIZE=10000
SAVEHIST=10000

# PROMPT (tema)
ZSH_THEME="powerlevel10k/powerlevel10k"
 # o "robbyrussell", "powerlevel10k" si lo tenés

# OH MY ZSH
export ZSH="$HOME/.oh-my-zsh"

plugins=(
  git
)
# plugins instlados con pacman
source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
source /usr/share/zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

source $ZSH/oh-my-zsh.sh

# ALIAS ÚTILES
alias ll="ls -alF"
alias la="ls -A"
alias l="ls -CF"
alias gs="git status"
alias gp="git pull"
alias gc="git commit"
alias gl="git log --oneline --graph --all"
alias c="clear"

# AUTOSUGERENCIAS (si lo instalaste con pacman)
source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh

# HIGHLIGHTING
source /usr/share/zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

# COLORES Y ESTÉTICA
autoload -U colors && colors
setopt prompt_subst
PROMPT='%F{blue}%n%f@%F{green}%m%f %F{yellow}%~%f %# '

# Kitty: usar 24-bit true color
export COLORTERM=truecolor
export TERM=kitty

# NAVEGACIÓN MEJORADA
bindkey '^[[H' beginning-of-line
bindkey '^[[F' end-of-line

# FUZZY FINDER (si usás fzf)
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh

# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

```

