# A Collection of everything Apple 
http://macintosh.ddns.net

This is intended for your https://brew.sh/ .zshrc configuration file, once 
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" 
```
HOMEBREW has been installed.

### Homebrew installs the stuff you need that Apple (or your Linux system) didn’t.

```
$ brew install wget curl git zsh
```

### Homebrew installs packages to their own directory and then symlinks their files into /usr/local (on macOS Intel).

```
/usr/local
$ find Cellar
Cellar/wget/1.16.1
Cellar/wget/1.16.1/bin/wget
Cellar/wget/1.16.1/share/man/man1/wget.1
```

```
$ ls -l bin
bin/wget -> ../Cellar/wget/1.16.1/bin/wget
```

### Homebrew won’t install files outside its prefix and you can place a Homebrew installation wherever you like.
### Trivially create your own Homebrew packages.

```
$ brew create https://foo.com/bar-1.0.tgz
Created /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core/Formula/bar.rb
```

### It’s all Git and Ruby underneath, so hack away with the knowledge that you can easily revert your modifications and merge upstream updates.

```
$ brew edit wget # opens in $EDITOR!
```

### Homebrew formulae are simple Ruby scripts:

```
class Wget < Formula
  homepage "https://www.gnu.org/software/wget/"
  url "https://ftp.gnu.org/gnu/wget/wget-1.15.tar.gz"
  sha256 "52126be8cf1bddd7536886e74c053ad7d0ed2aa89b4b630f76785bac21695fcd"

  def install
    system "./configure", "--prefix=#{prefix}"
    system "make", "install"
  end
end
```

### Homebrew complements macOS (or your Linux system). Install your RubyGems with gem and their dependencies with brew. “To install, drag this icon…” no more. Homebrew Cask installs macOS apps, fonts and plugins and other non-open source software.

```
$ brew install --cask iterm2
```

### Making a cask is as simple as creating a formula.

```
$ brew create --cask foo
Editing /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask/Casks/foo.rb
```

## Homebrew Documentation https://docs.brew.sh/Manpage

# Oh My Zsh is an open source, community-driven framework for managing your zsh configuration.

https://github.com/ohmyzsh/ohmyzsh

# Getting Started

### Prerequisites

A Unix-like operating system: macOS, Linux, BSD. On Windows: WSL2 is preferred, but cygwin or msys also mostly work.
Zsh should be installed (v4.3.9 or more recent is fine but we prefer 5.0.8 and newer). If not pre-installed (run zsh --version to confirm), check the following wiki instructions here: Installing ZSH
curl or wget should be installed
git should be installed (recommended v2.4.11 or higher)

## Basic Installation
Oh My Zsh is installed by running one of the following commands in your terminal. You can install this via the command-line with either curl, wget or another similar tool.

## Method	Command

### curl	
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

### wget	
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

### fetch	
sh -c "$(fetch -o - https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

### Note that previous configuration in .zshrc will be placed in .pre-oh-my-zsh. After installation you can move configuration you want to preserve into .zshrc.

## Manual inspection
### It's a good idea to inspect the install script from projects you don't yet know. You can do that by downloading the install script first, looking through it so everything looks normal, then running it:

```
$ wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```

## Using Oh My Zsh

## Plugins

### Oh My Zsh comes with a shitload of plugins for you to take advantage of. You can take a look in the plugins directory and/or the wiki to see what's currently available.

## Enabling Plugins
### Once you spot a plugin (or several) that you'd like to use with Oh My Zsh, you'll need to enable them in the .zshrc file. You'll find the zshrc file in your $HOME directory. Open it with your favorite text editor and you'll see a spot to list all the plugins you want to load.

```
$ vi ~/.zshrc
```

### For example, this might begin to look like this:

plugins=(
  git
  bundler
  dotenv
  macos
  rake
  rbenv
  ruby
)

Note that the plugins are separated by whitespace (spaces, tabs, new lines...). Do not use commas between them or it will break.

### Using Plugins
Each plugin includes a README, documenting it. This README should show the aliases (if the plugin adds any) and extra goodies that are included in that particular plugin.

### Themes
We'll admit it. Early in the Oh My Zsh world, we may have gotten a bit too theme happy. We have over one hundred and fifty themes now bundled. Most of them have screenshots on the wiki (We are working on updating this!). Check them out!

### Selecting a Theme
Robby's theme is the default one. It's not the fanciest one. It's not the simplest one. It's just the right one (for him).

Once you find a theme that you'd like to use, you will need to edit the ~/.zshrc file. You'll see an environment variable (all caps) in there that looks like:

ZSH_THEME="robbyrussell"
To use a different theme, simply change the value to match the name of your desired theme. For example:

ZSH_THEME="agnoster" # (this is one of the fancy ones)
see https://github.com/ohmyzsh/ohmyzsh/wiki/Themes#agnoster
Note: many themes require installing the Powerline Fonts in order to render properly.

Open up a new terminal window and your prompt should look something like this:

Agnoster theme

In case you did not find a suitable theme for your needs, please have a look at the wiki for more of them.

If you're feeling feisty, you can let the computer select one randomly for you each time you open a new terminal window.

ZSH_THEME="random" # (...please let it be pie... please be some pie..)
And if you want to pick random theme from a list of your favorite themes:

ZSH_THEME_RANDOM_CANDIDATES=(
  "robbyrussell"
  "agnoster"
)
If you only know which themes you don't like, you can add them similarly to an ignored list:

ZSH_THEME_RANDOM_IGNORED=(pygmalion tjkirch_mod)

export -f $(cat /Users/"USERNAME"/_/.profile.func)
/Users/"USERNAME"/.profile

### Motto for a research laboratory: What we work on today, others will first think of tomorrow. Science is knowledge which we understand so well that we can teach it to a computer; and if we don't fully understand something, it is an art to deal with it.

### .zshrc Configuration File from next line down.
zmodload zsh/zprof # top of your .zshrc file
#
#!/usr/bin/env python
#!/bin/sh
#
#oh-my-zsh .zshrc configuration.
##
DISABLE_UPDATE_PROMPT=true
##
PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/sbin:/Library/Apple/usr/bin:/Users/darrin/bin:$PATH"
PATH="/usr/local/opt/libtool/libexec/gnubin:$PATH"

### Path to your oh-my-zsh installation.
export ZSH="/Users/darrin/.oh-my-zsh"
export PATH="$HOME/.cask/bin:$PATH"
# Enable completions
autoload -Uz compinit && compinit
# autolo##
# ad -Uz compinit

for dump in ~/.zcompdump(N.mh+24); do
  compinit
done

compinit -C
##
# Minimal - Theme Settings
export MNML_INSERT_CHAR="$"
export MNML_PROMPT=(mnml_git mnml_keymap)
export MNML_RPROMPT=('mnml_cwd 20')
##
# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH
. /usr/local/etc/profile.d/z.sh
##
# If $ZSH_CACHE_DIR is already defined
ZSH_COMPDUMP="$ZSH_CACHE_DIR/.zcompdump"
##
typeset -g POWERLEVEL9K_INSTANT_PROMPT=quiet
# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi
##
# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/robbyrussell/oh-my-zsh/wiki/Themes
ZSH_THEME="powerlevel10k/powerlevel10k"
# ZSH_THEME="powerlevel9k/powerlevel9k"
# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in ~/.oh-my-zsh/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )
##
# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"
##
Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
HYPHEN_INSENSITIVE="true"
##
# eval "$(_PYMOBILEDEVICE3_COMPLETE=source_zsh pymobiledevice3)"
# Uncomment the following line to disable bi-weekly auto-update checks.
# DISABLE_AUTO_UPDATE="true"
##
# Uncomment the following line to automatically update without prompting.
DISABLE_UPDATE_PROMPT="true"
##
# Uncomment the following line to change how often to auto-update (in days).
export UPDATE_ZSH_DAYS=1
# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS=true
##
# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"
##
# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"
##
# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"
##
# Uncomment the following line to display red dots whilst waiting for completion.
COMPLETION_WAITING_DOTS="true"
##
# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
DISABLE_UNTRACKED_FILES_DIRTY="true"
##
# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
HIST_STAMPS="dd/mm/yyyy"
##
# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=$DOTFILES
if type brew &>/dev/null; then
  FPATH=$(brew --prefix)/share/zsh/site-functions:$FPATH

autoload -Uz compinit
compinit
fi
##
# Which plugins would you like to load?
# Standard plugins can be found in ~/.oh-my-zsh/plugins/*
# Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(
  git
  bundler
  # autojump
  wd
  zsh-autosuggestions
  zsh-syntax-highlighting
  zsh-history-substring-search
  jhipster
  brew
  cake
  copypath
  copyfile
  direnv
  dnf
  iterm2
  python
  man
  colorize
  web-search
  jsontools
  macports
  sudo
  thor
  macos
  sublime
  taskwarrior
  vagrant
  autoupdate
  clipboard
  hacker-quotes
  dotbare
  nvm
  cp
  colorize
  colored-man-pages
  extract
  web-search
  betterbrew
  bundler
  zsh-navigation-tools
  zsh-syntax-highlighting
  zsh-completions
  aliases
  autoenv
  cask
  colorize
  command-not-found
  common-aliases
  composer
  dircycle
  dotenv
  node
  npm
  pip
  pipenv
  ssh-agent
  sublime
  urltools
  xcode
  wp-cli
  z
  yarn
  )
##
##Zplugs
# export ZPLUG_HOME=/usr/local/opt/zplug
# source $ZPLUG_HOME/init.zsh
##
#Fix errors
ZSH_DISABLE_COMPFIX="true"
##
source $ZSH/oh-my-zsh.sh
##
# User configuration
# Miniplug
# Minimalistic plugin manager for ZSH.
# It was developed as a drop-in replacement for zplug and Antigen. 
# They both have serious problems and are not maintained anymore.
# Add to zshrc:
source "$HOME/.local/share/miniplug.zsh"
# simple ssh manager. 
# It looks for your previous ssh sessions in $HISTFILE and 
# keeps relevant the ones that you reconnect to. Supports bash and zsh.
source ./ssh-connect/ssh-connect.sh

# Nodejs
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
# [ -s "$NVM_DIR/bash_completion" ] && \. "\$NVM_DIR/bash_completion"

# This loads nvm bash_completion
# Define a plugin
#miniplug plugin 'zsh-users/zsh-syntax-highlighting'
if type brew &>/dev/null; then
    FPATH=$(brew --prefix)/share/zsh-completions:$FPATH

    autoload -Uz compinit
    compinit
  fi

# Define a theme
#miniplug theme 'dracula/zsh'

# Source Git
source /usr/local/opt/git-extras/share/git-extras/git-extras-completion.zsh
source "/usr/local/opt/zsh-git-prompt/zshrc.sh"
# Source plugins
#miniplug load
# Aliases
alias ls='ls -G'
alias g=git
alias gc='git commit'
# notice the space inside the quotes
# alias ss='sudo '
# Without the space you would receive an error that the `g` command is not found
# ^^ runs `sudo git`
alias ss g='sudo git'
alias grep='grep --color=auto'
# echo foo | grep fo
         # ^^^^ uses grep --color=auto alias

# echo foo | 'grep' fo
         #  ^^^^ will not colorize match
alias :q=exit
alias ..='cd ..'
alias ....='cd ../..'
# alias --='cd -'
# pipe output to grep
alias -g G='| grep'
# pipe output to less
alias -g L='| less'
# pipe output to `wc` with option `-l`
alias -g W='| wc -l'
# convert multiline output to single line and copy it to the system clipboard
alias -g C='| tr -d ''\n'' | xclip -selection clipboard'
echo -e 'zsh\nis\n\great\nhello\ngoodbye' G -A1 hello C
  # grep for hello and include 1 line after ^^^^^^^^^ ^
  #                                                   |
  # trim new lines and copy 'hello goodbye' to the ---|
  # system clipboard
alias -g G='| grep'
alias -g W='| wc -l'
alias -g GfooW='G foo W'
# don't worry about zle. We'll go over it later in the zle section.
globalias() {
   zle _expand_alias
   zle expand-word
   zle self-insert
}
zle -N globalias

# space expands all aliases, including global
bindkey -M emacs " " globalias
bindkey -M viins " " globalias

# control-space to make a normal space
bindkey -M emacs "^ " magic-space
bindkey -M viins "^ " magic-space

# normal space during searches
bindkey -M isearch " " magic-space
# Search through your command history and print the top 10 commands
alias history-stat='history 0 | awk ''{print $2}'' | sort | uniq -c | sort -n -r | head'

# Use `which` to find aliases and functions including binaries
which='(alias; declare -f) | /usr/bin/which --tty-only --read-alias --read-functions --show-tilde --show-dot'
# Functions
function to-lower() {
    echo ${1:l}
}

# whence -v do-ls
# do-ls is a shell function from ./do-ls

# if you declare the function directly you won't
# see the path with -v
# do-ls() { emulate -L zsh; \ls; }

# whence -v do-ls
# do-ls is a shell function

function curl-cert() {
  openssl s_client -showcerts -connect "${1}":443 -servername ${1}
}

function awsp() {
    export AWS_PROFILE=$(grep profile ${HOME}/.aws/config \
        | awk '{print $2}' | sed 's,],,g' \
        | fzf --layout reverse --height=10% --border)
}

function  mans(){
    man -k . \
    | fzf -n1,2 --preview "echo {} \
    | cut -d' ' -f1 \
    | sed 's# (#.#' \
    | sed 's#)##' \
    | xargs -I% man %" --bind "enter:execute: \
      (echo {} \
      | cut -d' ' -f1 \
      | sed 's# (#.#' \
      | sed 's#)##' \
      | xargs -I% man % \
      | less -R)"
}

function fshow() {
  git log --graph --color=always \
      --format="%C(auto)%h%d %s %C(black)%C(bold)%cr" "$@" \
  | fzf --ansi --preview "echo {} \
    | grep -o '[a-f0-9]\{7\}' \
    | head -1 \
    | xargs -I % sh -c 'git show --color=always %'" \
        --bind "enter:execute:
            (grep -o '[a-f0-9]\{7\}' \
                | head -1 \
                | xargs -I % sh -c 'git show --color=always % \
                | less -R') << 'FZF-EOF'
            {}
FZF-EOF"
}

disappointed() { echo -n " ಠ_ಠ " |tee /dev/tty| xclip -selection clipboard; }

flip() { echo -n "（╯°□°）╯ ┻━┻" |tee /dev/tty| xclip -selection clipboard; }

shrug() { echo -n "¯\_(ツ)_/¯" |tee /dev/tty| xclip -selection clipboard; }

matrix() { echo -e "\e[1;40m" ; clear ; while :; do echo $LINES $COLUMNS $(( $RANDOM % $COLUMNS)) $(( $RANDOM % 72 )) ;sleep 0.05; done|awk '{ letters="abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789@#$%^&*()"; c=$4;        letter=substr(letters,c,1);a[$3]=0;for (x in a) {o=a[x];a[x]=a[x]+1; printf "\033[%s;%sH\033[2;32m%s",o,x,letter; printf "\033[%s;%sH\033[1;37m%s\033[0;0H",a[x],x,letter;if (a[x] >= $1) { a[x]=0; } }}' }

# load zgen
source "${HOME}/.zgen/zgen.zsh"
# if the init script doesn't exist
if ! zgen saved; then

  # specify plugins here
  zgen oh-my-zsh

  # generate the init script from plugins above
  zgen save
fi
export MANPATH="/usr/local/man:$MANPATH"
#  GITSTATUS_LOG_LEVEL=DEBUG
##
# You may need to manually set your language environment
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
##
#A CA file has been bootstrapped using certificates from the system
#keychain. To add additional certificates, place .pem files in
#/usr/local/etc/openssl@1.1/certs
##
#and run
#/usr/local/opt/openssl@1.1/bin/c_rehash
#openssl@1.1 is keg-only, which means it was not symlinked into /usr/local,
#because macOS provides LibreSSL.
export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"
##
export LDFLAGS="-L/usr/local/opt/php@7.4/lib"
export CPPFLAGS="-I/usr/local/opt/php@7.4/include"
##
export JAVA_HOME=$(/usr/libexec/java_home)
#For pkg-config to find openssl@1.1 you may need to set:
export PKG_CONFIG_PATH="/usr/local/opt/openssl@1.1/lib/pkgconfig"
##
### ZNT's installer added snippet ###
#fpath=( "$fpath[@]" "$HOME/.config/znt/zsh-navigation-tools" )
#autoload n-aliases n-cd n-env n-functions n-history n-kill n-list n-list-draw n-list-input n-options n-panelize n-help
#autoload znt-usetty-wrapper znt-history-widget znt-cd-widget znt-kill-widget
#alias naliases=n-aliases ncd=n-cd nenv=n-env nfunctions=n-functions nhistory=n-history
#alias nkill=n-kill noptions=n-options npanelize=n-panelize nhelp=n-help
#zle -N znt-history-widget
#bindkey '^R' znt-history-widget
#setopt AUTO_PUSHD HIST_IGNORE_DUPS PUSHD_IGNORE_DUPS
#zstyle ':completion::complete:n-kill::bits' matcher 'r:|=** l:|=*'
### END ###
[ -f /usr/local/etc/profile.d/autojump.sh ] && . /usr/local/etc/profile.d/autojump.sh
# You may not want common commands in the command history. 
# Adding the following to zshrc prevent ll ls la cd man scp vim nvim less ping open 
# file which whois drill uname md5sum traceroute commands in the command history.
##
source /Users/darrin/.oh-my-zsh/custom/themes/powerlevel10k/powerlevel10k.zsh-theme
##
# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
##
source ~/.custom-alias

# $GOPATH/bin
export PATH=$PATH:$GOPATH/bin
##
bindkey '^[OA' history-substring-search-up
bindkey '^[OB' history-substring-search-down
export PATH="/usr/local/bin:$PATH"
##
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh
antibody bundle < ~/.zsh_plugins.txt
antibody bundle < ~/.zsh_plugins.txt > ~/.zsh_plugins.sh
# ~/.zshrc
source ~/.zsh_plugins.sh
##
# PATH=$PATH:$HOME/.rvm/bin
# export PYENV_ROOT="$HOME/.pyenv"
# export PATH="$PYENV_ROOT/bin:$PATH"
# if command -v pyenv 1>/dev/null 2>&1; then
#   eval "$(pyenv init -)"
# fi
#
# eval “$(pyenv init -)”
# eval “$(pyenv virtualenv-init -)”

#PATH=$PATH:$HOME/
PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
PATH=${PATH}:/Users/darrin/Github/mobiledevice/libimobiledevice-macosx/
export DYLD_LIBRARY_PATH=/Users/darrin/Github/mobiledevice/libimobiledevice-macosx/:$DYLD_LIBRARY_PATH

# export PATH="
export PATH="/usr/local/sbin:$PATH"
export PATH="/usr/local/opt/binutils/bin:$PATH"
export PATH="/usr/local/opt/php@7.4/bin:$PATH"
export PATH="/usr/local/opt/php@7.4/sbin:$PATH"
export PATH="/usr/local/opt/php@7.4/bin:$PATH"
export PATH="/usr/local/opt/php@7.4/sbin:$PATH"
export PATH="/usr/local/opt/php@7.4/bin:$PATH"
export PATH="/usr/local/opt/php@7.4/sbin:$PATH"
export PATH=$HOME/.nodebrew/current/bin:$PATH
export NODEBREW_ROOT=/usr/local/var/nodebrew
export PATH="/usr/local/opt/ssh-copy-id/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/openssl@3/bin:$PATH"
export PATH="/usr/local/opt/llvm/bin:$PATH"
export PATH="/usr/local/opt/util-linux/bin:$PATH"
export PATH="/usr/local/opt/util-linux/sbin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
export SSH_ASKPASS="/usr/local/bin/ssh-askpass"

# For compilers to find dependencies you may need to set:
export LDFLAGS="-L/usr/local/opt/openssl@3/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@3/include"
export LDFLAGS="-L/usr/local/opt/zlib/lib -L/usr/local/opt/sqlite/lib"
export CPPFLAGS="-I/usr/local/opt/zlib/include -I/usr/local/opt/sqlite/include"
export LDFLAGS="-L/usr/local/opt/python@3.10/lib"
export LDFLAGS="-L/usr/local/opt/libxml2/lib"
export CPPFLAGS="-I/usr/local/opt/libxml2/include"
export LDFLAGS="-L/usr/local/opt/php@7.4/lib"
export CPPFLAGS="-I/usr/local/opt/php@7.4/include"
export LDFLAGS="-L/usr/local/opt/readline/lib"
export CPPFLAGS="-I/usr/local/opt/readline/include"
export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"
export LDFLAGS="-L/usr/local/opt/libxslt/lib"
export CPPFLAGS="-I/usr/local/opt/libxslt/include"
export LDFLAGS="-L/usr/local/opt/portable-zlib/lib"
export CPPFLAGS="-I/usr/local/opt/portable-zlib/include"
export LDFLAGS="-L/usr/local/opt/libressl/lib"
export CPPFLAGS="-I/usr/local/opt/libressl/include"
export LDFLAGS="-L/usr/local/opt/luajit-openresty/lib"
export CPPFLAGS="-I/usr/local/opt/luajit-openresty/include"
export LDFLAGS="-L/usr/local/opt/libpcap/lib"
export CPPFLAGS="-I/usr/local/opt/libpcap/include"
export LDFLAGS="-L/usr/local/opt/util-linux/lib"
export CPPFLAGS="-I/usr/local/opt/util-linux/include"
export LDFLAGS="-L/usr/local/opt/python@3.10/lib"
LDFLAGS="-L/usr/local/opt/llvm/lib -Wl,-rpath,/usr/local/opt/llvm/lib"
export LDFLAGS="-L/usr/local/opt/llvm/lib"
export CPPFLAGS="-I/usr/local/opt/llvm/include"
export CPPFLAGS="-I/usr/local/opt/openjdk/include"
export LDFLAGS="-L/usr/local/opt/util-linux/lib"
export CPPFLAGS="-I/usr/local/opt/util-linux/include"
export PATH="/usr/local/opt/openssl@1.1/bin:$PATH"
#export PATH="/usr/local/opt/php@7.4/bin:$PATH"
export PATH="/usr/local/opt/luajit-openresty/bin:$PATH"
export PATH="/usr/local/opt/libpcap/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/openssl@3/bin:$PATH"
# eval "$(pyenv init -)"
export PATH="/usr/local/opt/python@3.7/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/python@3.7/lib"
export PKG_CONFIG_PATH="/usr/local/opt/python@3.7/lib/pkgconfig"
export PATH="/usr/local/opt/mysql-client/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/mysql-client/lib"
export CPPFLAGS="-I/usr/local/opt/mysql-client/include"
export PKG_CONFIG_PATH="/usr/local/opt/mysql-client/lib/pkgconfig"
export PATH="/usr/local/opt/llvm/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/llvm/lib"
export CPPFLAGS="-I/usr/local/opt/llvm/include"
LDFLAGS="-L/usr/local/opt/llvm/lib -Wl,-rpath,/usr/local/opt/llvm/lib"
export PATH="/usr/local/opt/libxslt/bin:$PATH"
export PATH="/usr/local/opt/unzip/bin:$PATH"export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"

export PATH="/usr/local/opt/llvm/bin:$PATH"
export PATH="/usr/local/opt/python@3.10/bin:$PATH"
export PATH="/usr/local/opt/llvm/bin:$PATH"
export PATH="/usr/local/opt/openjdk/bin:$PATH"
eval "$(pyenv virtualenv-init -)"

CPPFLAGS="-I$(brew --prefix zlib)/include" pyenv install -v 3.9.9

CPPFLAGS="-I$(brew --prefix openssl)/include -I$(xcrun --show-sdk-path)/usr/include" LDFLAGS="-L$(brew --prefix openssl)/lib"

CPPFLAGS="-I$(brew --prefix openssl)/include -I$(brew --prefix readline)/include -I$(xcrun --show-sdk-path)/usr/include" LDFLAGS="-L$(brew --prefix openssl)/lib -L$(brew --prefix readline)/lib"

CPPFLAGS="-I<openssl install prefix>/include" \
LDFLAGS="-L<openssl install prefix>/lib" \
# pyenv install -v <python version>

CONFIGURE_OPTS="--with-openssl=<openssl install prefix>"

export PKG_CONFIG_PATH="/usr/local/opt/libpcap/lib/pkgconfig"

# CFLAGS="-D_FILE_OFFSET_BITS=64 -D_DARWIN_USE_64_BIT_INODE" ./configure --prefix=/usr/local

# ifndef ENOATTR
# define ENOATTR ENODATA
# endif

# For pkg-config to find readline you may need to set:
export PKG_CONFIG_PATH="/usr/local/opt/libressl/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/libxml2/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/openssl@3/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/python@3.10/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/readline/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/libxslt/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/portable-zlib/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/luajit-openresty/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/util-linux/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/python@3.10/lib/pkgconfig"
export PKG_CONFIG_PATH="/usr/local/opt/util-linux/lib/pkgconfig"

if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi
export PATH="/usr/local/opt/python@3.10/bin:$PATH"
# load all brew pkgconfig
export PKG_CONFIG_PATH=$(find /usr/local/Cellar -name 'pkgconfig' -type d | grep lib/pkgconfig | tr '\n' ':' | sed s/.$//)
export PATH="/usr/local/opt/python/libexec/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/util-linux/lib"
export CPPFLAGS="-I/usr/local/opt/util-linux/include"
export LDFLAGS="-L/usr/local/opt/readline/lib"
export CPPFLAGS="-I/usr/local/opt/readline/include"
export PKG_CONFIG_PATH="/usr/local/opt/readline/lib/pkgconfig"
export NVM_DIR="$HOME/.nvm"
  [ -s "/usr/local/opt/nvm/nvm.sh" ] && \. "/usr/local/opt/nvm/nvm.sh"  # This loads nvm
  [ -s "/usr/local/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/usr/local/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion

export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"

LDFLAGS="-L/usr/local/opt/llvm/lib -Wl,-rpath,/usr/local/opt/llvm/lib"
export LDFLAGS="-L/usr/local/opt/llvm/lib"
export CPPFLAGS="-I/usr/local/opt/llvm/include"

# load glue pkgconfig
# export PKG_CONFIG_PATH={where glue pkginfo}:$PKG_CONFIG_PATH
#
[ -s "/Users/darrin/.scm_breeze/scm_breeze.sh" ] && source "/Users/darrin/.scm_breeze/scm_breeze.sh"

autoload -U +X bashcompinit && bashcompinit
complete -o nospace -C /usr/local/bin/mc mc
alias dotdrop='<absolute-path-to-dotdrop.sh> --cfg=<path-to-your-config.yaml>'


export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi

export PATH="/usr/local/opt/libxml2/bin:$PATH"

# POWERLEVEL10K_DISABLE_GITSTATUS=true
# GITSTATUS_LOG_LEVEL=DEBUG
# POWERLEVEL9K_DISABLE_GITSTATUS=true
# GITSTATUS_DAEMON=~/.oh-my-zsh/custom/themes/export PATH="$HOME/.asdf/bin:$HOME/.asdf/shims:$PATH"
# . $(brew --prefix asdf)/asdf.sh

export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/sbin:/Library/Apple/usr/bin:/Users/"USERNAME"/bin"
# source /usr/local/opt/gitstatus/gitstatus.prompt.zsh
export PATH="/usr/local/opt/libxml2/bin:$PATH"
export PATH="/usr/local/opt/libimobiledevice/bin:/usr/local/opt/libxml2/bin:$PATH"
