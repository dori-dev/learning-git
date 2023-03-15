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

### Create Repository

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
