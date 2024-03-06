
## Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## data access
bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solution

```

bandit14@bandit:~$ nc localhost 30000
^C
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$ nc localhost 30000 <<< "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq"
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt


```


## notes


nc herramienta que me permite conectarme a un servidor en un puerto especifico

-lnvp sirve par abrir un puerto
## references


