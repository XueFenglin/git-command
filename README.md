# Learn GIT Command

### Install
Git
[Git website](http://git-scm.com)

Book :
[Git Pro](https://git-scm.com/book/zh/v2)

check git install
```
which git
git --version
```

### Configuration

system configuration (/etc/gitconfig)
```
git config --system
```

user configuration(~/.gitconfig)
```
git config --global
```

project configuration(my_project/.git/config)
```
git config
```

example
```
git config --global user.name "snow xue"
git config --global user.email "someone@nowhere.com"

git config --list
git config user.name
git config user.email
```

more two useful configuration
```
git config --global core.editor "vim"
git config --global color.ui true
```

auto completion
```
curl -OL https://github.com/git/git/raw/master/contrib/completion/git-completion.bash
mv git-completion.bash .git-completion.hash
source .git-completion.hash
```

### Help
```
git help
git help <command>
git help log
man git-log

```
next page: whitespace
f: forward
b: backward
q: quit


### Initializing a repository
```
git init

```

add file
```
git add .
```
commit
```
git commit -m "Initial commit"
```


### Commit log
```
git log
git log -n 1
git log --since=2012-06-15
git log --until=2016-10-15
git log --author="snow"
git log --grep="Init"
git log --oneline -n3
git log --since="2 weeks ago" --until="3 days ago"
git log --since=2.weeks --until=3.days
git log -p c4b8132.. index.html
git log --stat --summary
git log --format=oneline (short,full,fuller,email,raw)
git log --graph
git log --oneline --graph --all --decorate

git help log
```
check the commit detail
```
git show c4b8132
git show --format=oneline HEAD^('^' means the parent one)
git show HEAD~3 (means HEAD^^^)
```
check workspace diff with HEAD
```
git diff
```
check staged diff with HEAD
```
git diff --staged
```
more example
```
git diff --color-words --staged

git diff c4b8132 tours.html
git diff c4b8132.. c4b8133 change.file
git diff --stat --summary c4b8132..HEAD
git diff -w (--ignore-all-space)
git diff -b (--ignore-space-change)
```


### Delete file

```
git rm filename
```

reset
```
git reset --soft
git reset --mixed(default)
git reset --hard
```
removing untracked
```
git clean
```

ignore file
[.gitignore] (https://help.github.com/articles/ignoring-files/)
[.gitignore sample] (https://github.com/github/gitignore)
example: How to ignore file has committed already.
```
git rm --cached tempfile
```

### Branch

check current branch
```
git branch
```

create new branch
```
git branch <new branch name>
```
switch
```
git checkout <branch name>
git checkout master
```

create branch and switch it
```
git checkout -b <new branch name>
```
compare the branch
```
git diff oldbranch..newbranch
```

check merged status
```
git branch --merged
```

rename branch
```
git branch -m branchOldName branchNewName
git branch --move branchOldName branchNewName
```

delete branch
```
git branch -d branchNewName
git branch --delete branchName
```
merge branch
```
git merge other_branch
```
fastforword merge and real merge

conflicts
1. abort merge
```
git merge --abort
```
2. merge it manually
3. merge by merge tool
```
git mergetool
```
reduce the conflicts
1. keep lines short
2. keep commits small and focused
3. beware stray edits to whitespace
 > space, tabs, line returns
4. merge often
5. track changes to master

### Stash

save to stash
```
git stash save "message"
```
view change stash
```
git stash list
git stash show stash@{0}
git stash show -p stash@{0}
```

pop stash
```
git stash apply
git stash pop (remove it form stash)
git stash pop stash@{2}
```
delete item in stash
```
git stash drop stash@{0}
git stash clear (delete all)
```
### Remotes


add remote git server
```
git remote add <alias> https://XXXX.git
```
check remote
```
git remote -v
```

remove remote
```
git remote rm <alias>
```

push to remote
```
git push -u <alias> <branch>
```

git remote branch
```
git branch -r
git branch -a (both remote and local)
```
clone repository
```
git clone https://XXXX.git <newname>
```

fetch change from remote repository
```
git fetch
```

merging in fetched changes
```
git merge <origin/master> (alias/branch)
```

git pull = git fetch + git merge

delete remote branch
```
git push <alias> :<to_delete_remote_branch_name>
git push <alias> --delete <to_delete_remote_branch_name>
```
push local branch to remote branch
```
git push <alias> <localBranch>:<remote_branch>
```

### some shortcut

```
git config --global alias.logg "log --graph --decorate --oneline --abbrev-commit --all"
```
