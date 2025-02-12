## Descripción
Our flag printing service has started glitching! Additional details will be available after launching your challenge instance.

¡Nuestro servicio de impresión de banderas ha comenzado a fallar! Detalles adicionales estarán disponibles después de iniciar tu instancia del desafío.
## Solución
Después de presionar el botón de "Launch Instance" en la pagina de picoCTF nos dirá la url y el puerto al que debemos conectarnos, en este caso fue el siguiente `nc saturn.picoctf.net 64738`el cual nos da como salida `picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}`
Para resolver esto tenemos que convertir los valores hexadecimales a valores ASCII, los cuales son los siguientes:
0x39 → '9'
0x63 → 'c'
0x34 → '4'
0x32 → '2'
0x61 → 'a'
0x34 → '4'
0x35 → '5'
0x64 → 'd'

Por ultimo concatenamos todos los caracteres.

```
La respuesta es:
picoCTF{gl17ch_m3_n07_9c42a45d}
```
## Notas adicionales
No hay notas adicionales