## Descripción
Can you get the flag? Additional details will be available after launching your challenge instance. Go to this [website](http://saturn.picoctf.net:63437/) and see what you can discover.

¿Puedes obtener la bandera? Los detalles adicionales estarán disponibles después de iniciar tu instancia de desafío. Ve a este [sitio web](http://saturn.picoctf.net:63437/) y mira qué puedes descubrir.
## Solución
En la página nos dice que nos registremos, al hacerlo nos dice `Log In Failed`, al ver el código de la página nos damos cuenta de que la validación de la contraseña y usuario se hace de manera local y no en el servidor, nos metemos al archivo `login.php` podemos ver como se evalúa el usuario y su contraseña, podemos encontrar otro archivo llamado `secure.js` donde encontramos el usuario y contraseña a evaluar del `admin`. Si nos registramos como `admin` con contraseña `strongPassword098765` se nos muestra la bandera:
`picoCTF{j5_15_7r4n5p4r3n7_05df90c8}`