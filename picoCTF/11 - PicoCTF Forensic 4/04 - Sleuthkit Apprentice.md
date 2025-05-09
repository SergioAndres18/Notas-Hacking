## Descripción
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
- [Download compressed disk image](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)

Descarga esta imagen de disco y encuentra la bandera.  
**Nota:** si estás usando la terminal web (_webshell_), descarga y extrae la imagen de disco en el directorio `/tmp`, no en tu directorio personal.

- [Descargar imagen de disco comprimida](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)
## Solución
El archivo que descargamos es una imagen de un disco, el cual esta comprimido, usamos `gzip -d disk.flag.img.gz` para descomprimir la imagen.

Para poder ver las particiones del dentro de la imagen usamos `mmls disk.flag.img`
```bash
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
```

Podemos intentar encontrar la bandera buscando alguna cadena que coincida con lo que buscamos, con `fls disk.flag.img -o 360448 -r` el `360448` indica a partir de que dirección de memoria iniciar la búsqueda, en este caso buscamos a partir de donde comienza la partición de `Linux`, si lo combinamos con `grep` y buscamos:
```bash
sergio_so@DESKTOP-F40822T:~/s_ap$ fls disk.flag.img -o 360448 -r | grep flag
++ r/r * 2082(realloc): flag.txt
++ r/r 2371:    flag.uni.txt
```

Encontramos un archivo `.txt` llamado `flag`, para poder leerlo y ver la bandera usamos lo siguiente:
```bash
sergio_so@DESKTOP-F40822T:~/s_ap$ icat disk.flag.img -o 360448 2371
picoCTF{by73_5urf3r_2f22df38}
```