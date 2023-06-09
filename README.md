# Git CheatSheet

In this set of documents, we intend to teach the **Git source control** completely and comprehensively, the training starts from the basic level and covers all the commands that are widely used in the git.

This cheat sheet has been prepared and collected by [**Mohammad Dori**](https://github.com/dori-dev)

## Getting Started

- [Git installation](#Git-Installation)
- [Git Config](#Git-Config)
- [Git Phases](#Git-Phases)
- [Git Commands](#Git-Commands)

#

# Git Installation

### Linux

- **ubuntu**, **debian**

  ```bash
  sudo apt-get update
  sudo apt-get install git
  ```

- **fedora**

  ```bash
  sudo dnf install git
  sudo yum install git
  ```

- **arch**, **manjaro**

  ```bash
  sudo pacman -S git
  ```

### Mac

```
brew package manager
```

### Windows

Download and install Git from here: https://git-scm.com/downloads

### Check Version

```bash
git --version
```

#

# Git Config

- Local level config
- Global level config
- System level config

```
git config --global user.username "dori-dev"
git config --global user.email "mr.dori.dev@gmail.com"
```

List of global configs

```
git config --global --list | -L
```

Edit git configs

```bash
git config --global --edit
```

add alias for git commands

```
git config --local alias.xyz "git status"
```

add alias, with xyz name

```
git config --local alias.xyz "git log --oneline --all"
```

#

# Git Phases

Three phases of git :

1. **Working directory** | **Working tree** | **Working Space**
2. **Index** | **Stage**
3. **Repository**

Files in a repository go through three stages before being under version control with git:

- **Untracked**: the file exists, but is not part of git's version control
- **Staged**: the file has been added to git's version control but changes have not been committed
- **Committed**: the change has been committed

To understand what stage the files in a repository are at.

```
git status
```

#

# Git Commands

### Create repository

<br>
initial repository

```bash
git init
```

<br>
clone repository from remote

```bash
git clone https://github.com/dori-dev/learning-git.git
```

#

#

### Deep dive into the phases of Git

<br>
show untracked, modified, staged files

```bash
git status
```

<br>
add untracked or modified file to stage

```bash
git add filename
```

<br>
add all of untracked or modified file to stage

```bash
git add .
```

<br>
add all of untracked or modified file to stage

```bash
git add -A
```

<br>
add part of file to staging area

```bash
git add --patch
```

<br>

```bash
git commit
```

<br>
commit changes of tracked files to head

```bash
git commit -m "comm_msg"
```

<br>
add all changes of tracked files to staging and commit them.

```bash
git commit -a -m "comm_msg"
```

<br>
amend commit

```bash
git commit --amend
```

<br>

```bash
git commit --amend --no-edit
```

#

#

### Git history

<br>
log of commits with date, descriptions and author name

```bash
git log
```

<br>
summary of git log

```bash
git log --oneline
```

<br>
log of commits with date, descriptions and author name related to a specific file

```bash
git log filename
```

<br>
git log with all diff between commits

```bash
git log -p filename
```

<br>
show all info and diff HEAD and commit(HEAD-1)

```bash
git show <commID>
```

<br>
show all info and diff commID and commit(commID-1)

```bash
git show <commID> filename
```

<br>
git reference log

```bash
git reflog
```

<br>
show only commits that occurred one day ago until now

```bash
git log --since "2 days ago"
```

<br>
only shows commits that have occurred until 18:21

```bash
git log --until "18:21"
```

<br>
only shows the commits that user `dori-dev` has made

```bash
git log --author "dori-dev"
```

<br>
only shows commits that have occurred in specific date and time

```bash
git log --since "Mon Nov 23 11:54:10 2023" --oneline
```

<br>
show all commits that have remove in their message

```bash
git log --grep "remove"
```

<br>
show the number of changes per file

```bash
git log --stat --summary
```

<br>
show all commits of all branches in tree mode

```bash
git log --all --graph
```

#

#

### Git alias

<br>
set shortcuts for git commands for example: s instead of status

```bash
git config --global alias.s "status"
```

<br>

```bash
git config --global alias.lo "log --oneline"
```

#

#

### Git help

<br>
show document related to command

```bash
git help <any_commands>
```

#

#

### Git diff

<br>
show different between first commit and second commit in a specific file

```bash
git diff <commID_1> <commID_2> filename
```

<br>
show all changes that were staged in a specific file

```bash
git diff --staged filename
```

<br>
show all changes that were not commit, whether staged or not

```bash
git diff HEAD
```

<br>
show all changes that were not staged

```bash
git diff
```

#

#

### Checkout & Restore

<br>
git checkout

```bash
git checkout
```

<br>
checkout in commID and create new branch

```bash
git checkout -b branch_name <commID>
```

<br>
checkout in tag_version and create new branch

```bash
git checkout -b branch_name tag_name
```

<br>
git restore

```bash
git restore
```

<br>
restore unstaged parts of file to head(like "git diff")

```bash
git restore index.txt
```

<br>
restore staging parts of file to unstaged(like "git diff --staged")

```bash
git restore --staged index.txt
```

<br>
restore staging part of file and unstaging part of file(like "git diff head")

```bash
git restore --source HEAD index.txt
```

#

#

### Git Reset

<br>
git reset(default tag is --mixed)

```bash
git reset
```

<br>
reset commits history

```bash
git reset --soft  <commID>
```

<br>
reset commits history and staging area

```bash
git reset --mixed <commID>
```

<br>
reset commits history and staging area and working directory

```bash
git reset --hard  <commID>
```

<br>
reset to the two commits before head

```bash
git reset --hard  HEAD~2
```

#

#

### Git revert

<br>
undoing commit like git reset but it's safe

```bash
git revert <commitID>
```

#

#

### Git branch

<br>
list of all local branches

```bash
git branch
```

<br>
list of all remote branches

```bash
git branch -r
```

<br>
list of all branches (local branches and remote branches)

```bash
git branch -a
```

<br>
delete a branch

```bash
git branch -d branch_name
```

<br>
create branch

```bash
git branch branch_name
```

<br>
switch in branches

```bash
git switch branch_name
```

<br>
create and switch branch

```bash
git switch -c branch_name
```

<br>
switch branch

```bash
git checkout branch_name
```

<br>
create and switch branch

```bash
git checkout -b branch_name
```

<br>
create and switch branch on the special commit

```bash
git checkout -b branch_name <commID>
```

<br>
log of all commits history on all of branch and show that in graph

```bash
git log --oneline --all --graph
```

#

#

### Git merge

<br>
merge a branch

```bash
git merge
```

<br>
merge branch with specific message

```bash
git merge branch_name -m "merge message"
```

<br>
merge without fast forward merging

```bash
git merge --no-ff branch_name
```

#

#

### Git rebase

<br>
for example, `feature` branch

```bash
git rebase master
```

<br>

```bash
git checkout master
```

<br>

```bash
git merge feature
```

#

#

### Conflicts

<br>
if see this message: "both modified" you have conflict

```bash
git merge branch_name
```

<br>
you should solve conflict and commit changes

```bash
git commit -m "merge branch_name"
```

<br>
aborting merge

```bash
git merge --abort
```

#

#

### Git stash

<br>
Temporary storage for saving all of changes in your repository

```bash
git stash
```

<br>
save files to stash

```bash
git stash save
```

<br>
save files to stash with specific message

```bash
git stash save "message"
```

<br>
for stash untracked files

```bash
git stash save --include-untracked | -u
```

<br>
show stash 0

```bash
git stash show stash@{0}
```

<br>
show `stash-0` with more information

```bash
git stash show -p stash@{0}
```

<br>
get `stash-0` files back to repository and remove them

```bash
git stash pop stash@{0}
```

<br>
get `stash-0` files back to repository(without remove)

```bash
git stash apply stash@{0}
```

<br>
remove `stash-1` from stash list

```bash
git stash drop stash@{1}
```

<br>
clear all stashes

```bash
git stash clear
```

<br>
get list of stashes

```bash
git stash list
```

<br>
stash part of files

```bash
git stash --patch | -p
```

#

#

### Cherry Pick

<br>
picking a commit from a branch and applying it to another branch

```bash
git cherry-pick <commitID>
```

<br>
bring a commit from a branch to this branch without commit them (leave them unstaged)

```bash
git cherry-pick --no-commit | -n <commitID>
```

#

#

### Git tag

<br>
get list of tags

```bash
git tag
```

<br>
filter tag list with pattern

```bash
git tag -l 'v1.*'
```

<br>
add a lightweight tag

```bash
git tag v2.1.8 <commitID>
```

<br>
add an annotated tags

```bash
git tag -a v1.0.0 -m 'message' <commitID>
```

<br>
add a tag by gpg signature

```bash
git tag -s v1.0.0 -m 'message' <commitID>
```

<br>
delete a tag

```bash
git tag -d v1.1.3
```

<br>
show tag info

```bash
git show v1.0.0
```

<br>
checkout in commitID and create new branch

```bash
git checkout -b branch_name <commitID>
```

<br>
checkout in tag version and create new branch

```bash
git checkout -b branch_name tag_name
```

#

#

### Git blame

<br>
when and by whom the file was updated

```bash
git blame <filename>
```

<br>
blame from line 1 to 10

```bash
git blame <filename> -L 1,10
```

#

#

### Git bisect

<br>
binary search commits

```bash
git bisect
```

<br>
start debug

```bash
git bisect start
```

<br>
specify the commit state(bad or good)

```bash
git bisect bad
```

<br>
this commitID is on good state

```bash
git bisect good <commitID>
```

<br>
quite from git bisect

```bash
git bisect reset
```

#

#

### Git remote

<br>
list of remotes

```bash
git remote
```

<br>
add new remote

```bash
git remote add remote_name "remote_address"
```

<br>
list of remotes with more information

```bash
git remote -v
```

<br>
remove a remote

```bash
git remote remove remote_name
```

<br>
rename a remote

```bash
git remote rename remote_name new_name
```

<br>
get more info

```bash
git remote show remote_name
```

<br>
push commits from branch to remote repository

```bash
git push remote_name branch_name
```

<br>
push tag to remote

```bash
git push remote_name tag_name
```

<br>
push all tag to remote

```bash
git push remote_name --tags
```

<br>
fetch remote new commits to local repository(you should merge them)

```bash
git fetch
```

<br>
automatically `git fetch` and `git merge`

```bash
git pull
```
