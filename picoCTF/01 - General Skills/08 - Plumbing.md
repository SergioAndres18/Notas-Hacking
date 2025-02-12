## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

A veces necesitas manejar datos de procesos fuera de un archivo. ¿Puedes encontrar una manera de conservar la salida de este programa y buscar la bandera? Conéctate a **jupiter.challenges.picoctf.org** en el puerto **4427**.
## Solución
Se propone crear un archivo .txt con la salida que arroja la conexión, para ello se usa el siguiente comando `nc jupiter.challenges.picoctf.org 4427 > output.txt`
Después en el archivo creado output.txt buscar la coincidencia con "picoCTF" se puede usar el siguiente comando: `grep "picoCTF" output.txt`

```
La respuesta es:
picoCTF{digital_plumb3r_5ea1fbd7}
```
## Notas adicionales

## Referencias
https://www.ionos.mx/digitalguide/servidores/herramientas/netcat/
https://www.hostinger.mx/tutoriales/comando-grep-linux