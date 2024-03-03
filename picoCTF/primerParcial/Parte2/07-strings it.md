## descripcion

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?
## pistas



## Solution

Si utilizamos "cat" tendremos texto no legible, por el tipo de archivo. Tendremos que utilizar otro

```
VFlours-picoctf@webshell:~$ file strings 
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=94ec6b5e9cef175e834e0f7fcaedeaa167603c90, not stripped
VFlours-picoctf@webshell:~$ 

```

```

VFlours-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}
VFlours-picoctf@webshell:~$ 

```

## notes

Comandos utilizados:
	1. strings


## references
