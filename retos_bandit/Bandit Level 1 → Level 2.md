## Objetivo

The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso
bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL


## Solución

ERROR
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$
```

SOLUCION
```
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
## Notas adicionales

Para poder entrar a archivos nombrados con "-" se debe de utilizar ya sea la ruta absoluta o relativa.

.  --> significa directorio actual
## Referencias

[Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)