# Git CheatSheet

In this set of documents, we intend to teach the **Git source control** completely and comprehensively, the training starts from the basic level and covers all the commands that are widely used in the git.

This cheat sheet has been prepared and collected by [**Mohammad Dori**](https://github.com/dori-dev)

## Getting Started

- [Git installation](#Git-installation)
- [Git Config](#Git-Config)

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
