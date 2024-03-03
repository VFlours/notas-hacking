## descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.

## pistas



## Solution

```

VFlours-picoctf@webshell:~$ ls
README.txt  contrasena.txt  convertidorCadenas.py  fixme2.py  level1.flag.txt.enc  level1.py
VFlours-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: level1.flag.txt.enc
That password is incorrect
VFlours-picoctf@webshell:~$ cat level1.flag.txt.enc 
A
 Rr1wQ  nVT_nPRVWVFlours-picoctf@webshell:~$ strins level1.flag.txt.enc 
-bash: strins: command not found
VFlours-picoctf@webshell:~$ strings level1.flag.txt.enc 
VFlours-picoctf@webshell:~$ file level1.flag.txt.enc 
level1.flag.txt.enc: data
VFlours-picoctf@webshell:~$ cat level1.flag.txt.enc | base64 -d
base64: invalid input
VFlours-picoctf@webshell:~$ nano level1.py
VFlours-picoctf@webshell:~$ python level1.py
Traceback (most recent call last):
  File "/home/VFlours-picoctf/level1.py", line 15, in <module>
    decryption = str_xor(flag_enc.decode(), user_pw)
NameError: name 'user_pw' is not defined
VFlours-picoctf@webshell:~$ nano level1.py
VFlours-picoctf@webshell:~$ python level1.py
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
VFlours-picoctf@webshell:~$ 


VFlours-picoctf@webshell:~$ cat level1.py
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()

def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "1e1a"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()
VFlours-picoctf@webshell:~$ 

```

## notes

Comandos utilizados:
	1. 

Al ejecutar el archivo .py este nos solicita una contraseña, por lo tanto este valida la entrada de texto. Con esto sabemos que viendo el codigo podremos saber que contraseña se utiliza.

## references
