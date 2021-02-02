# Squash all commits of a branch

## create temp branch
```
git checkout master
git checkout -b my_branch_name_temp
```
## merge my branch into temp
```
git merge --squash my_branch_name
```
## commit changes with one commit
```
git commit -m 'message to describe all the commits together'
```
## rename unsquashed branch
```
git branch -m my_branch_name my_branch_name_unsquashed
```
## rename temp branch
```
git branch -m my_branch_name
```
## delete unsquashed branch
```
git branch -D my_branch_name_unsquashed
```

## forced push if already pushed before
```
git push -f origin my_branch_name
```
