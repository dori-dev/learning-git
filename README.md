# Git CheatSheet

In this set of documents, we intend to teach the **Git source control** completely and comprehensively, the training starts from the basic level and covers all the commands that are widely used in the git.

This cheat sheet has been prepared and collected by [**Mohammad Dori**](https://github.com/dori-dev)

## Getting Started

- [Git installation](#Git-installation)
- [Git Config](#Git-Config)
- [Git Phases](#Git-Phases)
- [Git Commands](#Git-commands)

#

# Git-installation

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

# Git-Config

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

# Git-Phases

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

# Git-commands

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

### Git help

<br>
show document related to command

```bash
git help <any_commands>
```
