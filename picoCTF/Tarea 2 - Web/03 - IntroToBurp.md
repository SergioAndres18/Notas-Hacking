## Descripción
Try [here](http://titan.picoctf.net:60791/) to find the flag.

Intenta encontrar la bandera [aqui](http://titan.picoctf.net:60791/) 
## Solución
Al entrar en la página nos pide registrarnos, una vez lo hacemos nos pide ingresar un `OTP`. **OTP** se refiere a un **One-Time Password (Contraseña de un solo uso)**. Es un código que se genera para autenticar a un usuario **una sola vez** y por un **tiempo limitado**. Después de usarse (o tras cierto tiempo), ya no es válido. Se utiliza comúnmente para aumentar la seguridad en sistemas de autenticación, como en la verificación en dos pasos.

Sabiendo esto abrir el programa `BurpSuite` y junto a la extension de navegador `FoxyProxy` interceptamos las solicitudes `POST` y `GET`, dentro de ellas encontraremos el valor OTG, lo mandamos a la herramienta de `Repeater` de `BurpSuite`, eliminamos esa linea de código y enviamos, nos regresará la bandera:
`picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}`