## Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796
## Solución
En la página debemos ingresar con un usuario y contraseña, podemos usar cualquiera, pero al entrar nos dice que no tenemos bandera.
Al revisar las cookies de la página podemos ver que la cookie `Admin` que esta marcada como`False`. Podemos usar una extensión del navegador para modificar las cookies, en mi caso uso Firefox y use esta extensión https://addons.mozilla.org/es-MX/firefox/addon/cookie-editor/.
Al cambiar la cookie a `True`y recargar la página podemos ver la bandera 
```
picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}
```
## Referencias
https://addons.mozilla.org/es-MX/firefox/addon/cookie-editor/