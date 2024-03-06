
## Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## data access
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solution

```

bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1



read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$



```


## notes

- `openssl`: Es el comando que invoca la herramienta OpenSSL, que es una utilidad de línea de comandos para trabajar con protocolos de seguridad como SSL/TLS.
    
- `s_client`: Es una suborden de OpenSSL que actúa como un cliente SSL/TLS. Se utiliza para conectarse a servidores remotos y realizar diversas operaciones de cliente SSL/TLS, como la negociación de protocolos y la verificación de certificados.
    
- `-connect localhost:30001`: Este es el argumento que indica a `s_client` qué servidor y puerto debe conectarse. En este caso, se especifica que se debe conectar al servidor que se está ejecutando en el localhost (la propia máquina) en el puerto 30001.
    

Entonces, en resumen, este comando establecerá una conexión SSL/TLS con un servidor que se está ejecutando en la misma máquina en el puerto 30001 utilizando la herramienta OpenSSL.

SSL/TLS proporciona una capa de seguridad adicional a las comunicaciones en Internet, garantizando la confidencialidad, la integridad y la autenticidad de los datos transmitidos entre el cliente y el servidor. Esto es fundamental para proteger la privacidad y la seguridad de las transacciones en línea, como las transacciones financieras y el intercambio de información sensible.
## references


