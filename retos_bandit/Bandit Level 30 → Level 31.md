
## Goal
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.
Clone the repository and find the password for the next level.

## data access
bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solution

```


bandit30@bandit:~$ mkdir /tmp/repoTemporal4
bandit30@bandit:~$ cd /tmp/repoTemporal4
bandit30@bandit:/tmp/repoTemporal4$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo


bandit30@bandit:/tmp/repoTemporal4$ cd repo/
bandit30@bandit:/tmp/repoTemporal4/repo$ ls
README.md
bandit30@bandit:/tmp/repoTemporal4/repo$ cat README.md
just an epmty file... muahaha


bandit30@bandit:/tmp/repoTemporal4/repo$ git tag
secret
bandit30@bandit:/tmp/repoTemporal4/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/repoTemporal4/repo$

```

## notes

El etiquetado Git es una forma de marcar puntos específicos en la historia del repositorio. Un ejemplo sería marcar puntos de liberación del software. El comando para ver las etiquetas es git tag. Para crear una etiqueta el comando es git tag -a <nombre_de_la_etiqueta> -m <"descripción/mensaje de la etiqueta">. Para ver más detalles, como el mensaje de la etiqueta y el commit, puedes usar el siguiente comando: git show <nombre_de_la_etiqueta>.


## references


