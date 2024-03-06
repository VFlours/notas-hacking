
## Goal
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## data access
bandit28
AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solution

```

bandit28@bandit:~$ mkdir /tmp/repoTemporal
mkdir: cannot create directory ‘/tmp/repoTemporal’: File exists
bandit28@bandit:~$ mkdir /tmp/repoTemporal2
bandit28@bandit:~$ cd /tmp/repoTemporal2
bandit28@bandit:/tmp/repoTemporal2$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo

bandit28@bandit:/tmp/repoTemporal2$ ls
repo
bandit28@bandit:/tmp/repoTemporal2$ cd repo/
bandit28@bandit:/tmp/repoTemporal2/repo$ ls
README.md
bandit28@bandit:/tmp/repoTemporal2/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/repoTemporal2/repo$ git log
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

commit f08b9cc63fa1a4602fb065257633c2dae6e5651b
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    add missing data

commit a645bcc508c63f081234911d2f631f87cf469258
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    initial commit of README.md
bandit28@bandit:/tmp/repoTemporal2/repo$ git show^C
bandit28@bandit:/tmp/repoTemporal2/repo$ git show 14f754b3ba6531a2b89df6ccae6446e8969a41f3
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx

bandit28@bandit:/tmp/repoTemporal2/repo$ ^C
bandit28@bandit:/tmp/repoTemporal2/repo$


```

## notes


se puede ver el historial que ha sufrido el archivo readme.md por lo tanto se pone el comando git log, una vez que vemos los cambio podemos ver esos cambio con el comando git show
## references


