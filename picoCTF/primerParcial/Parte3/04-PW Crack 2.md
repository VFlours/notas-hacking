## descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## pistas



## Solution

```

VFlours-picoctf@webshell:~$ ls
README.txt  level2.flag.txt.enc  level2.py
VFlours-picoctf@webshell:~$ python level2.py 
Please enter correct password for flag: l
That password is incorrect
VFlours-picoctf@webshell:~$ cat level2.
cat: level2.: No such file or directory
VFlours-picoctf@webshell:~$ cat level2.py
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
VFlours-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> flag = 
KeyboardInterrupt
>>> flag = chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)
>>> print(flag)
de76
>>> exit()
VFlours-picoctf@webshell:~$ python level2.py 
Please enter correct password for flag: ^CTraceback (most recent call last):
  File "/home/VFlours-picoctf/level2.py", line 27, in <module>
    level_2_pw_check()
  File "/home/VFlours-picoctf/level2.py", line 17, in level_2_pw_check
    user_pw = input("Please enter correct password for flag: ")
KeyboardInterrupt

VFlours-picoctf@webshell:~$ python level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
VFlours-picoctf@webshell:~$ 

```

## notes

Comandos utilizados:
	1. 

Al ejecutar el archivo .py este nos solicita una contraseña, por lo tanto este valida la entrada de texto. Con esto sabemos que viendo el codigo podremos saber que contraseña se utiliza. Pero este codigo necesita ejecutarse para que nos de la contraseña real


## references
