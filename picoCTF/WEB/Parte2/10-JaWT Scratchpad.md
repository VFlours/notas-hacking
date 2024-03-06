## descripcion

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210
## pistas

What is that cookie?
Have you heard of JWT?
## Solution


JWT (JSON Web Token) es un estándar abierto (RFC 7519) que define una forma compacta y autónoma de transmitir información de forma segura entre partes como un objeto JSON. Esta información puede ser verificada y confiable porque está firmada digitalmente.

Un JWT consta de tres partes separadas por puntos:

1. Encabezado (Header): Contiene el tipo de token y el algoritmo de firma utilizado.
2. ![[Pasted image 20240305185952.png]]
3. Carga útil (Payload): Contiene los datos que se quieren transmitir, como por ejemplo el nombre de usuario o permisos de acceso.
4. ![[Pasted image 20240305190005.png]]
5. Firma (Signature): Utiliza una clave secreta para firmar la combinación del encabezado y la carga útil, lo que garantiza que el token no ha sido alterado en el camino.
6. ![[Pasted image 20240305190018.png]]

JWT es comúnmente utilizado para la autenticación y autorización en aplicaciones web y servicios API. Cuando un usuario se autentica en un sistema, se le otorga un JWT que puede ser enviado en las solicitudes subsiguientes para demostrar su identidad y acceder a recursos protegidos. El servidor puede verificar la validez del token y autorizar las acciones del usuario en función de la información contenida en él.


```
nano hash(es donde ira contenida la cookie jwt)

john hash -w "path donde se encuentra el archivo rockyou"

se obtiene la palabra ilovepico la cual sera intercambiada en el apartado de contraseña ver imagen de abajo

```
![[Pasted image 20240305194337.png]]

luego nos generara el nuevo token jwt el cual sera intercambiado en el cookie editor en la web,recargaremos y nos saldra la bandera

![[Pasted image 20240305194122.png]]
## notas

Comandos utilizados:
	1.

## references
