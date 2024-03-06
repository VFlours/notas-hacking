
## Goal
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## data access
bandit22
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

## Solution

```
bandit22@bandit:~$ ls -la /etc/cron.d
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
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat //usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ eecho I am user $myname | md5sum | cut -d ' ' -f 1
Command 'echo' not found, did you mean:
  command 'echo' from deb coreutils (8.32-4.1ubuntu1)
Try: apt install <deb name>
d41d8cd98f00b204e9800998ecf8427e
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
Command 'echo' not found, did you mean:
  command 'echo' from deb coreutils (8.32-4.1ubuntu1)
Try: apt install <deb name>
d41d8cd98f00b204e9800998ecf8427e
bandit22@bandit:~$echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$cat /tmp/88ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$



```

```
bandit22@bandit:/usr/bin$ ./cronjob_bandit23.sh
Copying passwordfile /etc/bandit_pass/bandit22 to /tmp/8169b67bd894ddbb4412f91573b38db3
bandit22@bandit:/usr/bin$ cat //tmp/8169b67bd894ddbb4412f91573b38db3
cat: ''$'\302\203''/tmp/8169b67bd894ddbb4412f91573b38db3': No such file or directory
bandit22@bandit:/usr/bin$ cat /tmp/8169b67bd894ddbb4412f91573b38db3
cat: ''$'\302\203''/tmp/8169b67bd894ddbb4412f91573b38db3': No such file or directory
bandit22@bandit:/usr/bin$^C
bandit22@bandit:/usr/bin$ cat /tmp/8169b67bd894ddbb4412f91573b38db3
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit22@bandit:/usr/bin$


```
## notes

se puede solucionar siguiendo los pasos que muestra el shell script o tambien llendo a la carpeta donde se encuentra este .sh y ejecutandolo para que te muestre lo que hace y ver a donde mueve la carpeta


## references


