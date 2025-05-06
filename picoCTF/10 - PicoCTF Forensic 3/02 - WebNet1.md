## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

Encontramos esta captura de paquetes y una llave. Recupera la bandera.
## Solución
1. Descargar la captura de paquetes y la llave.
2. Abrir la captura con el programa WireShark, allí podemos ver el hilo de transmisión de paquetes TLS. Pero no podemos ver su contenido.
3. En `Edit > Preferences... > Protocols > TLS` y añadimos la llave de desencriptación.
4. En `File > Export Objects > HTTPS...` y guardamos la imagen `vulture.jpeg`
5. Con el comando `strings vulture.jpg -n15` podemos ver dentro de la información de la imagen las cadenas que tengan mas de 15 caracteres, ahí esta la bandera `picoCTF{honey.roasted.peanuts}`