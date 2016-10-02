##### Learn GIT Command

### Install
[Git website](http://git-scm.com)

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



> [github markdown(.md)](https://guides.github.com/features/mastering-markdown/)
