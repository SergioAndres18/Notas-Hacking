## Descripción
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

El cifrado de un solo uso puede ser criptográficamente seguro, pero no cuando conoces la clave. ¿Puedes resolver esto? Te hemos dado la bandera cifrada, la clave y una tabla para ayudarte `UFJKXQZQUNB` con la clave `SOLVECRYPTO`. ¿Puedes usar esta [tabla](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) para resolverlo?
## Solución
Usando `CyberChef` con la herramienta `Vigenère Decode`, ingresamos la llave `SOLVECRYPTO` y el texto cifrado `UFJKXQZQUNB`, dándonos la bandera `picoCTF{CRYPTOISFUN}`
## Referencias
https://gchq.github.io/CyberChef/