# gitPractice
Git Practice

## Commits are shared by branches
In git, commits are not "owned" by a branch. Instead they are shared among branches

## Squash commits into one
**Method 1: git reset, deletes history and starts over, simple, blunt, and quick**

Move HEAD back by N commits you want to squash, this will delete those commits and stage their changes for next step
```
git reset --soft HEAD~N
```
After, do a new commit for all
```
git commit -m "New combined commit"
```
Push to remote with --force-with-lease (safer than --force)

--force = overwrite the remote branch no matter what

--force-with-lease = overwrite only if nobody else changed it, only if you are not cloberring anyone
```
git push --force-with-lease origin <branch-name>
```
**Method 2: git rebase, rewrites the last N commits one by one, let you edit history carefully**

Rebase interactively to the last 'N+1'th commit of your branch
```
git rebase -i HEAD~N
```
force-push is needed after rebase -i, because commit hashes change: remote branch history no longer matches
```
git push --force-with-lease
```
