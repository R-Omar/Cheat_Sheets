# Git commands

**Display Git configuration:**
```
git config --list
```
**Add settings to Git configuration:**
```
git config --global user.name "Omar RIAHI"
git config --global user.email omar.riahi@mail.com
```
**Remove/edit a setting from Git configuration:**
```
git config --global  --unset user.email
git config --global  --edit user.email omar.riahi@mail.com
```

**Initialise a Git repo**
```
git init
```

**Show the status of the local repo (files to stage, to commit…):**
```
git status
```

**Add all/tracked files to the staging:**
```
git add .
git add -u
```

**Commit changes:**
```
git commit –a –m "commit message"
```

**What the remote repo the local is mapped to:**
```
git remote -v
```

**Map (link) a local repo to a remote repo:**
```
git remote add origin https://github.com/Omar-R-O/web-page-repo.git
```

**Push local repo to remote repo on master branch:**
```
git push origin master
```

**Pull remote repo to local repo:**
```
git pull origin master
```

**Difference between the files in the stage and the previous commit:**
```
git diff –staged
```

**Viewing the commit log:**
```
git log
git log --oneline
git log -1 (latest commit)
git log -2 (the two latest) 
git log stat
```

**Create a branch:**
```
git checkout –b new _branch
```

**Switch to another branch:**
```
git checkout master
```

**List all branches on remote and local repo:**
```
git branch -a
```

**Stash untracked files in order to switch branches:**
```
git stach
```

**Merge pointed branch with another branch:**
```
git merge branch
```
