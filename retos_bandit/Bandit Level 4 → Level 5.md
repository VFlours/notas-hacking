
## Goal
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.
## data access

bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
## Solution

```
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ ls -h
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./*
QRrtZ▒i▒        ▒H
                  |▒▒ȧ▒▒▒▒^▒▒7L3▒▒Y▒ͯ    Ŵ▒▒▒▒E▒Y▒ܚ      ▒V&▒▒h▒F▒▒▒▒y▒▒▒O̫▒▒`▒\▒-⃐▒Hx▒▒2▒▒K▒▒i▒x▒#e▒>▒VO▒▒p{▒     ▒▒▒MUb4▒▒▒gQ▒▒eE}:▒g▒▒▒j8▒▒▒▒▒<.▒e▒▒S▒▒▒e 0▒▒▒▒▒]7▒▒▒▒▒▒▒b▒<▒~G=1▒▒▒▒▒▒▒B׃▒"
                ▒▒▒W▒▒9ؽ5lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
▒▒▒K▒~▒+▒▒9"T▒▒▒*Z$▒▒▒"▒r▒
▒Z▒\▒▒▒▒▒▒▒ж▒q▒▒▒7▒▒▒▒/▒n▒▒nbandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ ls ./-file07
./-file07
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$

```

## notes
file   --> nos dice el tipo de dato que contiene un archivo


## references


