
## Goal
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## data access
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Solution

```
bandit5@bandit:~/inhere$ find . -readable -size 1033c -type f
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```


## notes

find --> me permite buscar archivos

-redeable --> archivos que sean legibles

-size --> especificar el tamaño de archivo (c para bytes)

-type --> especificar el tipo de archivo( f regulares )

-xargs toma la salida estandar para tomarla como entrada estandar en otro comando
```
bandit5@bandit:~/inhere$ find . -readable -size 1033c -type f | xargs cat
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```


## references

manual de ayuda del comando find

