# git
Some useful practical notes on git :+1:

The public keys should be generated and stored at git settings. 
It authenticates the computer against the repo.

# create branch with existing changes
```
git add .
git commit -m "{comment}"
git branch {feature-branch}
git checkout {feature-branch}
git push --set-upstream origin {feature-branch}
```

# resets master branch with origin branch in the server
```
git fetch origin
git reset --hard origin/master
```
# undoes the commit and leaves the changes you committed unstaged (so they'll appear as "Changes not staged for commit" in git status, and you'll need to add them again before committing)
```
git reset HEAD~
```

# Git rebase solves the same problem than git merge. Merging is nice because is a non destructive operation. Never do rebase on a public branch. Rebasing moves the commits of your feature branch to begin on the tip of the master branch. You can rebase the feature branch onto master branch using the following commands
```
git checkout feature
git rebase master
```

# merge master branch with feature branch
```
git checkout master
git merge {feature-branch}
```

# squash last 2 commits before push
```
git rebase -i HEAD~2
```

After running command It'll ask you to what to do with commits. In order to make changes you need to use vi like editor and change pick or squash (there are other options as well) then write and quit with :wq  

## sample : 
pick 01d1124 Adding license
squash 6340aaa Moving license into its own file
squash ebfd367 Jekyll has become self-aware.
