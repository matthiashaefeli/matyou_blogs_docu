# How to undo a mistaken rebase

```
$ git reflog
```

```
$ git reflog my_branch
7dj998u7 my_branch@{0}: rebase finished: refs.heads/my_branch onto e087087987gr987987987we987988d98987
l9d8dwhe my_branch@{1}: commit: some commit messages
```

then do:

```
$ git checkout my_branch  # if you are not in the branch
```

```
$ git reset --hard l9d8dwhe
```

or:

```
$ git reset --hard my_branch@{1}
```

and you are back to the original as before the rebase
