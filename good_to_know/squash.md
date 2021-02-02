# Squash all commits of a branch

```
git checkout master
git checkout -b my_branch_name_temp                             # create temp branch
git merge --squash my_branch_name                               # merge my branch into temp
git commit -m 'message to describe all the commits together'    # commit changes with one commit
git branch -m my_branch_name my_branch_name_unsquashed          # rename unsquashed branch
git branch -m my_branch_name                                    # rename temp branch
git branch -D my_branch_name_unsquashed                         # delete unsquashed branch
git push -f origin my_branch_name                               # forced push if already pushed before
```
