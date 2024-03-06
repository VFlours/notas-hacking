
## Goal

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit1**


## data access

puede estar el acceso por medio de la llave privada ssh o encontrando la contrseña con 

etc/pass/usuario,pero para eso debes de estar adentro


## Solution

```

bandit17@bandit:~$ wc -l passwords.old
100 passwords.old
bandit17@bandit:~$ wc -l passwords.new
100 passwords.new
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$

```

## notes



## references


