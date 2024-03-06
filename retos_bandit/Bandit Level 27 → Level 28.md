
## Goal
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## data access

bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
## Solution

```


bandit27@bandit:~$ mkdir /tmp/repoTemporal
bandit27@bandit:~$ cd /tmp/repoTemporal
bandit27@bandit:/tmp/repoTemporal$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo


bandit27@bandit:/tmp/repoTemporal$ ls
repo
bandit27@bandit:/tmp/repoTemporal$ cd repo
bandit27@bandit:/tmp/repoTemporal/repo$ ls -la
total 16
drwxr-sr-x 3 bandit27 root 4096 Jul  3 12:24 .
drwx--S--- 3 bandit27 root 4096 Jul  3 12:24 ..
drwxr-sr-x 8 bandit27 root 4096 Jul  3 12:24 .git
-rw-r--r-- 1 bandit27 root   68 Jul  3 12:24 README


bandit27@bandit:/tmp/repoTemporal/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

## notes


al poner el puerto de se debe de poner con dos puntos despues del localhost
## references


