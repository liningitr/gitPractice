# gitPractice
Git Practice

## Commits are shared by branches
In git, commits are not "owned" by a branch. Instead they are shared among branches

## Squash commits into one

Move HEAD back by N commits you want to squash, this will delete those commits and stage their changes for next step

```
git reset --soft HEAD~N
```
After, do a new commit for all
```
git commit -m "New combined commit"
```
