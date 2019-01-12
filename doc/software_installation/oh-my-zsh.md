# install oh-my-zsh

```zsh
install git & zsh
$ sudo apt-get install git zsh

$ sudo chsh -s /bin/zsh

install oh-my-zsh via curl
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"


         __                                     __
  ____  / /_     ____ ___  __  __   ____  _____/ /_
 / __ \/ __ \   / __ `__ \/ / / /  /_  / / ___/ __ \
/ /_/ / / / /  / / / / / / /_/ /    / /_(__  ) / / /
\____/_/ /_/  /_/ /_/ /_/\__, /    /___/____/_/ /_/
                        /____/                       ....is now installed!


Please look over the ~/.zshrc file to select plugins, themes, and options.

p.s. Follow us at https://twitter.com/ohmyzsh.

p.p.s. Get stickers and t-shirts at https://shop.planetargon.com.

copy some settings from .bashrc to .zshrc
in my case copy nvm settings

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

```

# change theme
This is not necessary, but I like the theme, ys.
```zsh

$ vim .zshrc

before
ZSH_THEME="robbyrussell"
[looks like]
➜  ~ vim .zshrc

after
ZSH_THEME="robbyrussell"
[looks like]
username @ pi in ~ [4:43:19]

```
