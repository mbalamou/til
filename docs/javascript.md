# JavaScript

* [npm](./npm.md)
* [Use `console.log()` like a pro](https://markodenic.com/use-console-log-like-a-pro/)

## Install NVM on macOS

* [NVM on GitHub](https://github.com/nvm-sh/nvm)
* [NVM on Homebrew](https://formulae.brew.sh/formula/nvm)
```
brew install nvm

cat <<'EOF' >> ~/.bashrc
export NVM_DIR="$HOME/.nvm"
    [ -s "$(brew --prefix)/opt/nvm/nvm.sh" ] && \. "$(brew --prefix)/opt/nvm/nvm.sh" # This loads nvm
    [ -s "$(brew --prefix)/opt/nvm/etc/bash_completion.d/nvm" ] && \. "$(brew --prefix)/opt/nvm/etc/bash_completion.d/nvm" # This loads nvm bash_completion
EOF
```

## Install Node and NPM using NVM
```
nvm install v16
nvm alias stable v16
nvm alias default stable
nvm use default
```
