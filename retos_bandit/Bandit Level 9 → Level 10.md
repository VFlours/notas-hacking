
## Goal

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## data access
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t


## Solution

```
bandit9@bandit:~$ strings data.txt | grep ==
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$

```


## notes

strings --> muestra las cadenas dentro de un archivo binario o de datos.

grep 
## references


