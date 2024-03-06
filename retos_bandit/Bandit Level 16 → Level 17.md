
## Goal
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.


## data access
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solution

```
bandit16@bandit:~$ nmap localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-22 18:21 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00017s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 22 18:04:08 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 22 18:04:08 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 22 18:03:08 2024 GMT; NotAfter: Feb 22 18:04:08 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEWdQAXzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIyMTgwMzA4WhcNMjQwMjIyMTgwNDA4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC0
EWB28TWVpVUtrYSaYvmbjtrgpiTuEqg01/SReTOErvDgCyz8mhJ06BhcWK0RDiNz
E1BeQ1s7bo4V8knTeqgTd3cA9XIKO8BgqmGwYiPJyBVDMO+9S4dojnuJGViyhoM7
e0kKwdp7+uEER22koJg+ZqyI/dSSmvaDqMAU+D6FKxcxKjF8vTQzn0CLsYSXPHxT
mhshEAC8jWhYggcUxG0L1qMJnh/NL18e0jwBeCrE2PwsRuh1Qc6vl4Fd/mUByDJb
KSjsR3zDoegCWzh5lTAbnt5eaT47PBNA4foRLypdCG1tG+Cbgk6d0BGtluAJz9D8
5vEfrVpm38OelPOo0vBJAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAl
z9TnfQ4cqpUeKMFRzhzuHEvuglEdfmmWmhpQ+NnpcI686OZDshzpHFRVUQjwMulr
XuhDoohLwnd+AOB4BqYWWYoF2z1mo3rsxZxxCoI7y8SP331O46Aqc4SyKMEfYBXq
mCaK5VQebSZotRPqI6jS2W7/+UmJXXKG4pEKI5pBA5tTnvNSbh6Yk87cFlAitTcN
36V1lq8S7tj2BZSfcC+nyoqwPPeLTb5beQTmKG0/JFDnYeHCbVQALq5AhXXH5G67
ytpppb4itSOMr9bfv+Awx6PPLbOJ/gxF1c1HkXX5/Pjbdy2W4sCykvXAJBir2BFe
ixo6bdA2sW0cz3uzk5x7
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 50A07C31ACC7CA17B4A55E8A66FE9C28CCE83046AD5B6C40A39B42B040E28F10
    Session-ID-ctx:
    Resumption PSK: 3E457DB246FD6277828AC161572F9CA01DDF8F631B6C0025915A33B058916F88B27F42497868C1C286C640E2F596E07C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d5 fe 56 7f 7c 44 0f 09-aa 20 5d ad 9d 9b 72 2f   ..V.|D... ]...r/
    0010 - 45 b2 58 c9 d3 5d 28 63-a2 f7 52 ff fd 34 9d 46   E.X..](c..R..4.F
    0020 - bc 83 1c 94 d0 e9 42 08-4d 25 57 b6 2f ba 2a 90   ......B.M%W./.*.
    0030 - 60 02 da bb 70 ae de ec-9a 8c 07 a7 ca d3 0b 08   `...p...........
    0040 - ac 91 8f 5b 33 12 ae bf-ac 75 a8 e6 c4 6e b9 e9   ...[3....u...n..
    0050 - 97 0b e9 37 86 8c f3 d2-9c 28 0d 43 d0 f0 62 a5   ...7.....(.C..b.
    0060 - 3f 31 f3 ff cb 2b fe 17-18 72 93 ac ad 5d cd e6   ?1...+...r...]..
    0070 - e7 9a 51 5d cb 5f f5 6d-f2 7f d8 e6 af 65 e4 a0   ..Q]._.m.....e..
    0080 - 33 d3 da 86 c8 db d7 91-92 df 63 76 84 b9 84 c4   3.........cv....
    0090 - 7f c1 f9 84 cf 61 32 fb-bd 81 72 bd 7c f1 2a d7   .....a2...r.|.*.
    00a0 - 01 20 6a c6 d5 3e 5e 0f-7a 79 40 3a 98 62 c5 2a   . j..>^.zy@:.b.*
    00b0 - 41 51 62 c7 f5 94 0f 0c-96 e7 01 4f c6 7e 5c c1   AQb........O.~\.
    00c0 - a9 9b d2 e8 a5 e1 a5 3c-be 4a a1 2e 00 a2 ac e3   .......<.J......

    Start Time: 1708626125
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 00216F6A0D3163E26BB528CD8AF04E5E509BD8727726E0B4109D314BFD77C0BA
    Session-ID-ctx:
    Resumption PSK: 0292EA93080CD167425765C4C8C7A78E4C2646EC22D30D282142961526FF9ED77D3B5A2150B7E95B84D54B12B44F4925
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d5 fe 56 7f 7c 44 0f 09-aa 20 5d ad 9d 9b 72 2f   ..V.|D... ]...r/
    0010 - be 68 a8 7b d2 ed 31 7c-60 c8 46 37 40 82 30 8e   .h.{..1|`.F7@.0.
    0020 - 6e e2 72 61 49 40 3f f4-a6 4d 1b d8 62 9d 36 c1   n.raI@?..M..b.6.
    0030 - 71 34 ca ab 9d cc 07 c8-c6 1a f2 51 0b af 7f ab   q4.........Q....
    0040 - 71 e6 84 ba 7b a2 70 14-64 f5 2f dc 84 76 ce e9   q...{.p.d./..v..
    0050 - 92 48 d4 4b 2f 69 14 c4-5c 48 99 5f 2f 96 e7 d5   .H.K/i..\H._/...
    0060 - 02 68 94 6c 4a f6 46 62-24 eb 16 dd 8e 7a bf 82   .h.lJ.Fb$....z..
    0070 - 7b f0 7c b9 c8 c1 a3 eb-7e 97 39 ab d6 72 95 1d   {.|.....~.9..r..
    0080 - 53 6a 4f ff 92 f1 df 98-b4 fb dd 26 77 05 41 41   SjO........&w.AA
    0090 - e2 c8 48 d5 a6 4e a1 13-3a 7a 26 ec 66 68 df 7a   ..H..N..:z&.fh.z
    00a0 - f0 4d 2d 77 66 a9 82 6e-34 d0 fd 18 63 af 07 04   .M-wf..n4...c...
    00b0 - e3 09 0a d7 0d 9d ad f7-11 c2 64 7c 57 38 48 40   ..........d|W8H@
    00c0 - 99 7e ef 4a e2 7c c3 a6-f6 a5 ba d9 50 a6 9c c2   .~.J.|......P...

    Start Time: 1708626125
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$


```


## notes

nmap -> solamente te muestra los 100 primeros puertos,en orden en el que son mas utilizados

con la llave privada ssh se puede entrar al siguiente nivel utilizando el siguiente comando

```
ulise@SSJ MINGW64 ~
$ ssh -i llave bandit17@bandit.labs.overthewire.org -p 2220

```

`nmap` es una poderosa herramienta de escaneo de redes que se utiliza para descubrir hosts y servicios en una red informática, así como para crear un mapa de la red.

llave es el nombre del archivo donde esta guardada la llave ssh privada.

## references


