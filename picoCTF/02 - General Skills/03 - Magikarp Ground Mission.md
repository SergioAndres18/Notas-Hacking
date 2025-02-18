## Descripción
Do you know how to move between directories and read files in the shell? Start the container, `ssh`to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password,  `ee388b88`
Additional details will be available after launching your challenge instance.

¿Sabes cómo moverte entre directorios y leer archivos en la terminal? Inicia el contenedor, conéctate a él usando `ssh`, y luego usa `ls` una vez conectado para comenzar. Inicia sesión mediante `ssh` como `ctf-player` con la contraseña `ee388b88`.  
Habrá detalles adicionales disponibles después de iniciar tu instancia de desafío.
## Solución
Para conectarnos por ssh usamos el comando que nos da picoCTF `ssh ctf-player@venus.picoctf.net -p 52945`.
Una ves conectados podemos usar `ls` para ver los archivos y carpetas de la ubicación, los archivos .txt los podemos abrir con `cat nombre.txt`.

Dentro de la maquina virtual nos da la bandera por partes y no da instrucciones, en las cuales tenemos que ir a la carpeta de arriba con `cd`y a la carpeta origen con `cd /`
```
La respuesta es:
picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}
```
## Notas adicionales

## Referencias