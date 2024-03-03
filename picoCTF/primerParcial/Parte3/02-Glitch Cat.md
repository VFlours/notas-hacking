## descripcion

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 55826`
## pistas



## Solution

```
VFlours-picoctf@webshell:~$ nc saturn.picoctf.net 55826
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
^C


VFlours-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x39)
'9'
>>> chr(0x63)
'c'
>>> chr(0x34)
'4'
>>> chr(0x32)
'2'
>>> chr(0x61)
'a'
>>> chr(0x34)
'4'
>>> chr(0x35)
'5'
>>> chr(0x64)
'd'
>>> 

```

picoCTF{gl17ch_m3_n07_9c42a45d}

```
flag_missing_part = chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64)
print("picoCTF{gl17ch_m3_n07_" + flag_missing_part + "}")

otra solucion seria de esta manera.
```
## notes

Comandos utilizados:
	1. 


## references
