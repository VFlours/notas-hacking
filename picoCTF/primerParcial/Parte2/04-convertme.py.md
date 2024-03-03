## descripcion
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/24/convertme.py)

## pistas
Utilizamos "wget" para descargar el archivo, al ejecutarlos nos pide transformar un numero a binario y al colocarlo nos da la bandera

## Solution

```
VFlours-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt  code.py  convertme.py  flag  ltdis.sh  static  text.tct  warm
VFlours-picoctf@webshell:~$ python convertme.py
If 59 is in decimal base, what is it in binary base?
Answer: 111011
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}
VFlours-picoctf@webshell:~$ 


```

## notes

Comandos utilizados:
	1.wget


## references
