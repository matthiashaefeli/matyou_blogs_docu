# zshc case insensitive completion

open file .zshrc with your text editor:

```
code ~/.zshrc
```

add command below to the file:

```
zstyle ':completion:*' mathcer-list 'm:{a-z}={A-Za-z}'
autoload -Uz compinit && compinit
```

Restart terminal.

If you have a message on the new started terminal like

```
zsh compinit: insecure directories, run compaudit for list.
Ignore insecure directories and continue [y] or abort compinit [n]?
```

then type:

```
compaudit
```

if the following file show up after hit enter:

```
/usr/local/share/zsh/site-functions
```

type following commands:

```
sudo chmod -R 755 /usr/local/share/zsh/site-functions
sudo chmod _R 755 /usr/local/share/zsh
```

Restart terminal and try again!
