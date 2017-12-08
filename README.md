# git
Some useful practical notes on git

-- create branch with existing changes
git add .
git commit -m "{comment}"
git branch {feature-branch}
git checkout {feature-branch}
git push --set-upstream origin {feature-branch}
git checkout master

--resets master branch with origin branch in the server
git fetch origin
git reset --hard origin/master

--merge master branch with feature branch
git checkout master
git merge {feature-branch}

--squash last 2 commits before push
git rebase -i HEAD~2

After running command It'll ask you to what to do with commits. In order to make changes you need to use vi like editor and change pick or squash (there are other options as well) then write and quit with :wq  

sample : 
pick 01d1124 Adding license
squash 6340aaa Moving license into its own file
squash ebfd367 Jekyll has become self-aware.
