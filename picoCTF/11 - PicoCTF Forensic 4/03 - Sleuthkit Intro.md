## Descripción
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory. [Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)
Additional details will be available after launching your challenge instance.

Descarga la imagen de disco y usa `mmls` sobre ella para encontrar el tamaño de la partición de Linux. Conéctate al servicio de verificación remoto para comprobar tu respuesta y obtener la bandera.  
**Nota**: si estás usando el _webshell_, descarga y extrae la imagen de disco en `/tmp`, no en tu directorio personal.

Haz clic en “Download disk image” para obtenerla.
## Solución
El archivo que descargamos es una imagen de un disco, el cual esta comprimido, usamos `gzip -d disk.img.gz` para descomprimir la imagen.

Para poder ver las particiones del dentro de la imagen usamos:
```bash
sergio_so@DESKTOP-F40822T:~/s_intro$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
```

Lanzamos la instancia de picoCTF y en ella nos dice lo siguiente:
```bash
sergio_so@DESKTOP-F40822T:~/s_intro$  nc saturn.picoctf.net 54157
What is the size of the Linux partition in the given disk image?
Length in sectors: 0000202752
0000202752
Great work!
picoCTF{mm15_f7w!}
```

Respondiendo correctamente nos muestra la bandera.
