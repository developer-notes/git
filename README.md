# git
Some useful practical notes on git :+1:

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

# merge master branch with feature branch
```
git checkout master
git merge {feature-branch}
```

# squash last 2 commits before push
```
git rebase -i HEAD~2
```
After running this command, it'll ask you what to do with commits. In order to make changes you need to use a vi like editor and change pick or squash (there are other options as well) then you can write and quit with :wq.  

## sample : 
``` bash
pick 01d1124 Adding license
squash 6340aaa Moving license into its own file
squash ebfd367 Jekyll has become self-aware.
```

# to change the last commits description
```
git commit --amend
```
