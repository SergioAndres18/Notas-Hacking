## Descripción
Can you get the flag? Additional details will be available after launching your challenge instance. Go to this [website](http://saturn.picoctf.net:63686/) and see what you can discover.

¿Puedes obtener la bandera? Los detalles adicionales estarán disponibles después de iniciar tu instancia de desafío. Ve a este [sitio web](http://saturn.picoctf.net:63686/) y mira qué puedes descubrir.
## Solución
Al ingresar a la página nos indica `Continue as guest`, al hacerlo nos dice que no tienen servicio de invitados en este momento. Al mirar las cookies con `F12` en el apartado `Almacenamiento` en el navegador `Firefox` encontramos una llamada `isAdmin` con valor `0`, si la modificamos a `1` y recargamos la página nos muestra la bandera:
`picoCTF{gr4d3_A_c00k13_65fd1e1a}`