## Descripción
Help us test the form by submiting the username as `test` and password as `test!` Additional details will be available after launching your challenge instance.

¡Ayúdanos a probar el formulario enviando el nombre de usuario como `test` y la contraseña como `test!` Detalles adicionales estarán disponibles después de iniciar tu instancia del desafío.
## Solución
Al ingresar a la página nos pide iniciar cesión, si lo hacemos con usuario `test` y contraseña `test!` nos muestra un buscador de banderas, pero si buscamos alguna no nos muestra nada.

Si usamos el inspector del navegador con `F12` y nos vamos a la sección de red con la opción de `Registros persistentes` activada, regresamos al inicio y volvemos a ingresar, al hacerlo podemos ver registros con los id `cGljb0NURntwcm94aWVzX2Fs` y `bF90aGVfd2F5XzI1YmJhZTlhfQ==`, los cuales están en base64.
![[Imagen 06 - findme.png]]

Podemos usar ciberChef para convertirlos y obtener la bandera:
`picoCTF{proxies_all_the_way_25bbae9a}`
## Referencias
https://gchq.github.io/CyberChef/