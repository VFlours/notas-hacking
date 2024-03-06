
## Goal
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## data access
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT


## Solution

```

bandit20@bandit:~$ ls -ls
total 16
16 -rwsr-x--- 1 bandit21 bandit20 15600 Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ nc -lnvp2020
Listening on 0.0.0.0 2020
^C
bandit20@bandit:~$ nc -lnvp 2120 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 137897
bandit20@bandit:~$ Listening on 0.0.0.0 2120
^C
bandit20@bandit:~$ nc -lnvp 2820 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2] 140847
bandit20@bandit:~$ Listening on 0.0.0.0 2820
^C
bandit20@bandit:~$ jobs
[1]-  Running                 nc -lnvp 2120 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2]+  Running                 nc -lnvp 2820 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect 2820
Connection received on 127.0.0.1 47020
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[2]+  Done                    nc -lnvp 2820 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$


```

## notes


con el & mandamos el trabajo a segundo plano

- `nc`: Es el comando para iniciar Netcat, una herramienta de red versátil que puede actuar como cliente o servidor para leer o escribir datos en conexiones de red.
    
- `-l`: Esta opción indica a Netcat que debe iniciar un servidor de escucha.
    
- `-n`: Evita la resolución de nombres de DNS.
    
- `-v`: Muestra un mayor detalle o verbosidad.
    
- `-p 2120`: Especifica que Netcat debe escuchar en el puerto 2120.
    
- `<<<`: Este operador en bash redirige la cadena "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" hacia la entrada estándar del comando `nc`, lo que significa que esta cadena se enviará al cliente que se conecte al servidor de escucha.
    
- `&`: Esto coloca el comando en segundo plano, lo que significa que se ejecutará en segundo plano y liberará la terminal para que puedas seguir utilizando la misma.
    

En resumen, este comando inicia un servidor Netcat en el puerto 2120 y enviará la cadena "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" a cualquier cliente que se conecte a este servidor.
## references


