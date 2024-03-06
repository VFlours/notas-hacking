
## Goal
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## data access
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solution

```
bandit29@bandit:/tmp/repoTemporal3$ ls
repo
bandit29@bandit:/tmp/repoTemporal3$ cd repo/
bandit29@bandit:/tmp/repoTemporal3/repo$ ls
README.md
bandit29@bandit:/tmp/repoTemporal3/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>



bandit29@bandit:/tmp/repoTemporal3/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/repoTemporal3/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/repoTemporal3/repo$ git branch
* dev
  master


bandit29@bandit:/tmp/repoTemporal3/repo$ ls
code  README.md
bandit29@bandit:/tmp/repoTemporal3/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/repoTemporal3/repo$

```

## notes

se puede ver todas las ramas de git con git branch -a

se puede cambiar de ramas con git checkout 'rama'

## references


