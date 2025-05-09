## Descripción
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
Additional details will be available after launching your challenge instance.

Descarga esta imagen de disco, encuentra la clave e inicia sesión en la máquina remota.  
**Nota**: si estás usando el _webshell_, descarga y extrae la imagen de disco en `/tmp`, no en tu directorio personal.
Detalles adicionales estarán disponibles una vez que inicies tu instancia del desafío.
## Solución
Descargamos el archivo y lo descomprimimos con `gzip -d disk.img.gz` y usamos `mmls disk.img` para ver las particiones.
```bash
sergio_so@DESKTOP-F40822T:~/oni$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
```

Con el comando `fls disk.img -o 206848` podemos ver las carpetas de la partición, con `fls disk.img -o 206848 470` ingresamos a la carpeta `root`, aquí encontramos una carpeta llamada `ssh`, ingresamos a ella.
```bash
sergio_so@DESKTOP-F40822T:~/oni$ fls disk.img -o 206848 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
sergio_so@DESKTOP-F40822T:~/oni$ fls disk.img -o 206848 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
```

Con el comando `icat disk.img -o 206848 2345 > key_file` extraemos el archivo `id_ed25519`, lo llamamos `key_file`. Si usamos `cat` no podemos leer el archivo, usamos `chmod 600 key_file` para otorgar permisos.

Nos conectamos a la instancia, dentro con un `ls` vemos los archivos, ahí encontramos una archivo `flag.txt`, con `cat` lo leemos y obtenemos la bandera.
```bash
sergio_so@DESKTOP-F40822T:~/oni$ ssh -i key_file -p 63189 ctf-player@saturn.picoctf.net
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
picoCTF{k3y_5l3u7h_339601ed}
```