
## Goal
The password for the next level is stored in a hidden file in the **inhere** directory.
## data access
bandit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
## Solution

```
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct  5 06:19 .
drwxr-xr-x 3 root    root    4096 Oct  5 06:19 ..
-rw-r----- 1 bandit4 bandit3   33 Oct  5 06:19 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$

```

## notes

-l   --> lista todos los elementes.
-a --> muestra todos los archivos sin importar si son escondidos.

## references
