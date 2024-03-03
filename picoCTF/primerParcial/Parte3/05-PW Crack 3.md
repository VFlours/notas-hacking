## descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## pistas



## Solution

```

VFlours-picoctf@webshell:~$ ls  
README.txt  level3.flag.txt.enc  level3.hash.bin  level3.py


Se modifica el script 
def level_3_pw_check():
    pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
    for i in range(0, len(pos_pw_list)):
       user_pw = pos_pw_list[i]
       user_pw_hash = hash_pw(user_pw)
    
       if( user_pw_hash == correct_pw_hash ):
           print("Welcome back... your flag, user:")
           decryption = str_xor(flag_enc.decode(), user_pw)
           print(decryption)
           return
       print("That password is incorrect")




# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

VFlours-picoctf@webshell:~$ python level3.py
That password is incorrect
That password is incorrect
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

```

## notes

Comandos utilizados:
	1. 

Automatizamos para que pruebe las contraseñas
## references
