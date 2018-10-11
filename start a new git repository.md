### A new repo from scratch

Create a directory to contain the project.
```
$ git init
```
Write some code.
```
$ git add
```
to add the files (probably Readme.md)
```
$ git commit
```

### A new repo from an existing project
If It's an existing project that you want to start tracking with git.

Go into the directory containing the project.
```
$ git init
$ git add .
```
You’ll probably want to create a .gitignore file right away, to indicate all of the files you don’t want to track. 
```
$ git add .gitignore
$ git commit
```
### Connect it to github - Push an existing repository
You’ve now got a local git repository. You can use git locally, like that, if you want. 
But if you want the thing to have a home on github, do the following.

```
$ git remote add origin https://github.com/username/new_repo
$ git push -u origin master
```


