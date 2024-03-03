## descripcion

Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)
## pistas



## Solution

```

VFlours-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-03-01 01:03:17--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                                            100%[=================================================================================================================================================================>]     270  --.-KB/s    in 0s      

2024-03-01 01:03:17 (3.24 MB/s) - 'runme.py' saved [270/270]

VFlours-picoctf@webshell:~$ ls
README.txt  level3.flag.txt.enc  level3.hash.bin  level3.py  runme.py
VFlours-picoctf@webshell:~$ pyhton runme.py
-bash: pyhton: command not found
VFlours-picoctf@webshell:~$ python runme.py
picoCTF{run_s4n1ty_run}
VFlours-picoctf@webshell:~$ ^C
VFlours-picoctf@webshell:~$ 

```

## notes

Comandos utilizados:
	1. 


## references
