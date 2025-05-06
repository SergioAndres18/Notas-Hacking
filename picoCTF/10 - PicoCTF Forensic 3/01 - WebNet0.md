## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

Encontramos esta captura de paquetes y una llave. Recupera la bandera.
## Solución
En las pistas nos habla de la desencriptación de transmisión de paquetes TLS, para esto se ocupa una llave, la cual nos la da picoCTF. Los pasos son:
1. Descargar la captura de paquetes y la llave.
2. Abrir la captura con el programa WireShark, allí podemos ver el hilo de transmisión de paquetes TLS. Pero no podemos ver su contenido.
3. En `Edit > Preferences... > Protocols > TLS` y añadimos la llave de desencriptación.
4. Una vez hecho esto podemos ver el contenido de las transmisiones, para encontrar la bandera en `Edit > Find next...` y en las opciones de la herramienta seleccionamos `Packet details`, `Narrow & Wide` y  `String`, buscamos `picoCTF`.
5. En el apartado hexadecimal de abajo podemos ver la bandera  `picoCTF{nongshim.shrimp.crackers}`
## Referencias
https://en-m-wikipedia-org.translate.goog/wiki/Transport_Layer_Security?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=wa