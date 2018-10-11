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

# undoes the commit and leaves the changes you committed unstaged 
(so they'll appear as "Changes not staged for commit" in git status, and you'll need to add them again before committing)
```
git reset HEAD~
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

### sample : 
``` bash
pick 01d1124 Adding license
squash 6340aaa Moving license into its own file
squash ebfd367 Jekyll has become self-aware.
```

# to change the last commits description
```
git commit --amend
```

# to allow empty commits
```
git commit --allow-empty -m "some comment"
```


# Undo published commits with new commits

If you've published the work, you probably don't want to reset the branch, since that's effectively rewriting history. In that case, you could indeed revert the commits. With Git, revert has a very specific meaning: create a commit with the reverse patch to cancel it out. This way you don't rewrite any history.

This will create three separate revert commits:
```
git revert a867b4af 25eee4ca 0766c053
```

It also takes ranges. This will revert the last two commits:
```
git revert HEAD~2..HEAD
```

Similarly, you can revert a range of commits using commit hashes:
```
git revert a867b4af..0766c053 
```

Reverting a merge commit
```
git revert -m 1 <merge_commit_sha>
```

To get just one, you could use `rebase -i` to squash them afterwards
Or, you could do it manually (be sure to do this at top level of the repo)
get your index and work tree into the desired state, without changing HEAD:
```
git checkout 0d1d7fc32 .
```

Then commit. Be sure and write a good message describing what you just did
```
git commit
```
# Changing Committer Name & Email Globally 

```
git config --global user.name "John Doe"
git config --global user.email "john@doe.org"
```
# Changing Your Committer Name & Email per Repository

```
git config user.name "John Doe"
git config user.email "john@doe.org"
```

# Remote related commands
```
git remote -v
```

```
git remote add [name] [url]
```

```
git remote remove [name]
```

```
git remote rename [old name] [new name]
```
