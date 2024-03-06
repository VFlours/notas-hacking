
## Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## data access
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solution

```
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$
```
## notes

2>/dev/null --> mada la salida de error al dispositivo nulo (no aparece en pantalla los errores)

  
En la línea de comandos de Unix/Linux, los números como `1` y `2` representan los descriptores de archivos estándar. En particular:

- `0` representa la entrada estándar (stdin).
- `1` representa la salida estándar (stdout).
- `2` representa la salida de error estándar (stderr).

Por lo tanto, `2>/dev/null` significa redirigir la salida de error estándar (stderr) a `/dev/null`, que es un dispositivo especial en Unix/Linux que se utiliza para descartar datos. En otras palabras, cualquier mensaje de error que se produzca al ejecutar el comando `find` se enviará a `/dev/null` y, por lo tanto, no se mostrará en la pantalla.

## references


