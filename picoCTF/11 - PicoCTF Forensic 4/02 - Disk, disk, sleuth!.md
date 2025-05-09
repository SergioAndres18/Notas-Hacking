## Descripción
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz)

Usa `srch_strings` de _The Sleuth Kit_ y algo de habilidad en la terminal para encontrar una bandera en esta imagen de disco: `dds1-alpine.flag.img.gz`.
## Solución
El archivo que descargamos es una imagen de un disco, el cual esta comprimido, usamos `gzip -d dds1-alpine.flag.img.gz` para descomprimir la imagen.

Para poder analizar el contenido del disco instalamos la herramienta `Sleuth Kit` con el comando `sudo apt install sleuthkit`, para poder ver las particiones del dentro de la imagen usamos `mmls dds1-alpine.flag.img`, no encontramos nada importante en esta información.

Podemos intentar ver si dentro de la imagen se encuentra alguna cadena que coincida con una bandera, para usamos `srch_strings dds1-alpine.flag.img | grep pico` y así podemos encontrar la bandera `picoCTF{f0r3ns1c4t0r_n30phyt3_a69a712c}`.
