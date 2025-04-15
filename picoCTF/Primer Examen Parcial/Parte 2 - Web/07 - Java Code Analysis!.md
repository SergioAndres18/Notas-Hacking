#### Description

BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!

Additional details will be available after launching your challenge instance.

#### Hints 

1.-Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?.

2.- The 'role' and 'userId' fields in the JWT can be of interest to you!.

3.- The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.

4.- Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.
#### Solucion

entras a la pagina y entras a la seccion FLAG.
* inspeccionas el elemento.
* Te vas a "Network" regargas la pagina.
* dal clik al archivo (xhr) "saturn.picoctf.net".
* En la seccion "Autorizacion" veras una key la copias.
* te vas a esta pagina https://jwt.io/   .
* En "PAYLOAD" (morado) cambias "role" : "Admin"   y   "email" : "admin"
y "userId" : 2    .
*````
Deveria quedar algo asi:
```
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1745202640,
  "iat": 1744597840,
  "userId": 2,
  "email": "admin"
}  

``````

Ahora en donde avías inspeccionado la pagina, en  "Application" ve a " Local storage "
y cambia el token anterior por el nuevo, y también el token-payload  (con el morado), refrescan la pagina y listo.

`````
picoCTF{w34k_jwt_n0t_g00d_7745dc02}

Referencias:
https://www.youtube.com/watch?v=AT61XquM3mI