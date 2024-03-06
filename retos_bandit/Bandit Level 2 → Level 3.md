
## Goal
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## data access
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solution

```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$

SEGUNDA SOLUCION

bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$

```

## notes

los archivos que tengan espacios en el nombre se tienen que poner comillas dobles o cancelar los espacios con barra invertida.

## references
