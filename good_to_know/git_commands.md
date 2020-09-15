# Git commands

## Show only the changed words with color
```
$ git diff --color-words
```

## Shows change on specific commit
```
$ git show commit_number
```
You can add the flags --color-words

## Shows difference between 2 commits
```
$ git diff older_commit_number..HEAD
```

## Skips git add .
```
$ git commit -am 'commit text'
```

## Opens editor to add multiline commit messages
```
$ git commit
```
save and close file in editor after adding commit text

## Shows commits on one line each
```
$ git log --online
```

## discard changes of files not staged
```
$ git checkout -- .
```
discard all changes
```
$ git checkout file
```
discard changes for this file

## Unstage a staged file
```
$ git reset HEAD file
```
or unstage all
```
$ git reset HEAD
```

## Add changes to the last commit, or change commit message of the last commit
```
$ git commit --amend -m 'commit text'
```

## Revert commit
```
$ git revert commit_number
```

## Remove untracked files
```
$ git clean -n
```
tells what it would do
```
$ git clean -f
```
remove untracked files
