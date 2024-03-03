## descripcion
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/1/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)

## pistas



## Solution
Utilizamos "wget" para descargar el codigo, es necesario archivo codebook.txt para que el script funcione.

```
VFlours-picoctf@webshell:~$ python code.py
Couldn't find codebook.txt. Did you download that file into the same directory as this script?
VFlours-picoctf@webshell:~$ 
```

solucion
```

VFlours-picoctf@webshell:~$ cat codebook.txt 
azbycxdwevfugthsirjqkplomn
VFlours-picoctf@webshell:~$ code.py
-bash: code.py: command not found
VFlours-picoctf@webshell:~$ python code.py 
picoCTF{c0d3b00k_455157_d9aa2df2}

```

## notes

Comandos utilizados:
	1. wget
	3. python
	


## references
