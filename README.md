# macOS setup

this is my setup when migrating to a new MacOS machine or re-installing.

### Homebrew 🍺

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

---

### Tools / Apps 🔧

Homebrew allows to install not only CLI-based but full-desktop apps. This allows to automate installation of most required apps.

Dev:

    brew cask install \
    chrome-devtools \
    docker 
    firefox \
    google-chrome \
    iterm2 \
    vagrant \
    vagrant-manager \
    virtualbox \
    visual-studio-code



    brew install \
    bash bash-completion \
    composer
    docker-compose \
    node \
    zsh zsh-completions

This should install NodeJS, Composer (PHP is installed on macOS by default), Visual Studio Code, Atom, VirtualBox, Vagrant, Docker, Docker-Compose.

---

### ZSH

    brew install zsh zsh-completions
    chsh -s $(which zsh)
    echo $SHELL #/bin/zsh

### Bash Completions,

add the following script into **~/.bash_profile**.

    if type brew &>/dev/null; then
      HOMEBREW_PREFIX="$(brew --prefix)"
      if [[ -r "${HOMEBREW_PREFIX}/etc/profile.d/bash_completion.sh" ]]; then
        source "${HOMEBREW_PREFIX}/etc/profile.d/bash_completion.sh"
      else
        for COMPLETION in "${HOMEBREW_PREFIX}/etc/bash_completion.d/"*; do
          [[ -r "$COMPLETION" ]] && source "$COMPLETION"
        done
      fi
    fi
