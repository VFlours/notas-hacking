## Description

This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag).

## pistas




## Solution

```
wget https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag
--2024-02-27 18:32:09--  https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                           100%[===================================================================================================>]      34  --.-KB/s    in 0s      

2024-02-27 18:32:09 (14.9 MB/s) - 'flag' saved [34/34]

VFlours-picoctf@webshell:~$ ls
README.txt  flag
VFlours-picoctf@webshell:~$ cat flag 
picoCTF{s4n1ty_v3r1f13d_b5aeb3dd}


```

## notes

Con el comando wget-- podemos descargar archivos copiando su link 


## references
