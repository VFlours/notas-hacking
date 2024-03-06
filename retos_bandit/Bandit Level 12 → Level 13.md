
## Goal
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)


## data access
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solution

```

bandit12@bandit:~$
bandit12@bandit:~$ mkdir
bandit12@bandit:~$ mkdir /tmp/381/
bandit12@bandit:~$ cd /tmp/381
bandit12@bandit:/tmp/381$ xxd -r ~/data.txt > data
bandit12@bandit:/tmp/381$ cat data
▒h44▒z▒▒A▒▒▒▒@=▒h4hh▒?▒)[=▒h▒▒O(B▒▒2A▒▒▒)▒tZc▒▒:▒pã)▒A▒ˈ▒0▒▒▒΅A▒yjeϢx,▒(▒▒▒▒z▒E▒+"▒2▒/▒-▒▒e"▒▒▒^▒▒▒▒t▒j▒▒▒$▒d▒@▒dJơ'7\▒▒▒$▒▒m1c▒▒#>▒aԽ▒EV▒▒F▒▒OCӐc@M▒C▒▒▒]▒▒Y2^h8▒▒▒D=▒▒~ O▒I▒▒NDpF▒+▒|b#Jv▒#▒J▒▒d▒LފW$▒Û▒͖y▒`
                                  ▒\&   ▒▒[▒@*w▒M▒0θ▒▒nr▒▒C▒▒`e$b▒
                                                                  ~▒{▒▒▒
                                                                        ▒▒`▒<▒▒▒▒a▒▒?e:T▒▒▒e▒T4±b▒▒▒▒)▒@ِ▒▒▒x=bandit12@bandit:/tmp/381$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/381$ mv data data.gz
bandit12@bandit:/tmp/381$ ls
data.gz
bandit12@bandit:/tmp/381$ gzip -d data.gz
bandit12@bandit:/tmp/381$ ls
data
bandit12@bandit:/tmp/381$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/381$ mv data data.bz2
bandit12@bandit:/tmp/381$ ls
data.bz2
bandit12@bandit:/tmp/381$ bzip2 -d data.bz2
bandit12@bandit:/tmp/381$ ls
data
bandit12@bandit:/tmp/381$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/381$ mv data data.gz
bandit12@bandit:/tmp/381$ gzip -d data.gz
bandit12@bandit:/tmp/381$ ls
data
bandit12@bandit:/tmp/381$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/381$ mv data data.tar
bandit12@bandit:/tmp/381$ ls
data.tar
bandit12@bandit:/tmp/381$ tar xf data.tar
bandit12@bandit:/tmp/381$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/381$ rm data.tar
bandit12@bandit:/tmp/381$ ls
data5.bin
bandit12@bandit:/tmp/381$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/381$ mv data5.bin data5.tar
bandit12@bandit:/tmp/381$ ls
data5.tar
bandit12@bandit:/tmp/381$ tar xf data5.tar
bandit12@bandit:/tmp/381$ ls
data5.tar  data6.bin
bandit12@bandit:/tmp/381$ rm data5.tar
bandit12@bandit:/tmp/381$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/381$ mv data6.bin data6.zip
bandit12@bandit:/tmp/381$ mv data6.bin data6.bz2
mv: cannot stat 'data6.bin': No such file or directory
bandit12@bandit:/tmp/381$ mv data6.zip data6.bz2
bandit12@bandit:/tmp/381$ ls
data6.bz2
bandit12@bandit:/tmp/381$ gzip2 data6.bz2
Command 'gzip2' not found, did you mean:
  command 'gzip' from deb gzip (1.10-4ubuntu4.1)
  command 'bzip2' from deb bzip2 (1.0.8-5build1)
Try: apt install <deb name>
bandit12@bandit:/tmp/381$ bzip2 data6.bz2
bzip2: Input file data6.bz2 already has .bz2 suffix.
bandit12@bandit:/tmp/381$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/381$ ls
data6
bandit12@bandit:/tmp/381$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/381$ mv data6 data6.tar
bandit12@bandit:/tmp/381$ tar xf data6.tar
bandit12@bandit:/tmp/381$ ls
data6.tar  data8.bin
bandit12@bandit:/tmp/381$ rm data6.tar
bandit12@bandit:/tmp/381$ ls
data8.bin
bandit12@bandit:/tmp/381$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/381$ mv data8.bin data8.gz
bandit12@bandit:/tmp/381$ ls
data8.gz
bandit12@bandit:/tmp/381$ gzip -d data8.gz
bandit12@bandit:/tmp/381$ ls
data8
bandit12@bandit:/tmp/381$ file data8
data8: ASCII text
bandit12@bandit:/tmp/381$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/381$

```

``

```
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cat data.txt | file-
Command 'file-' not found, did you mean:
  command 'file' from deb file (1:5.41-3ubuntu0.1)
  command 'file2' from deb file-kanji (1.1-20)
Try: apt install <deb name>
bandit12@bandit:~$ cat data.txt | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt |file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat |
> ^C
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$

```
## notes

xxd -r  vaciado hexadecimal



## references


