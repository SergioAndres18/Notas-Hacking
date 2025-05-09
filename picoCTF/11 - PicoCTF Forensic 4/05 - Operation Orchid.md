## Descripción
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
- [Download compressed disk image](https://artifacts.picoctf.net/c/212/disk.flag.img.gz)

Descarga esta imagen de disco y encuentra la bandera.  
**Nota**: si estás usando el _webshell_, descarga y extrae la imagen de disco en `/tmp`, no en tu directorio personal.
* Descargar imagen de disco comprimida
## Solución
Descargamos el archivo y lo descomprimimos con `gzip -d disk.flag.img.gz`
```bash
sergio_so@DESKTOP-F40822T:~/o_o$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
```

Con el comando `fls disk.flag.img -o 411648 -r | grep flag` buscamos si existe una bandera en el disco, encontramos un archivo llamado `flag.txt.enc`.
```bash
sergio_so@DESKTOP-F40822T:~/o_o$ fls disk.flag.img -o 411648 -r | grep flag
+ r/r * 1876(realloc):  flag.txt
+ r/r 1782:     flag.txt.enc
+ 
```

Si intentamos leer el archivo con `icat disk.flag.img -o 411648 1782` nos sale una cadena ilegible, esto se debe que el archivo se encuentra encriptado.
```bash
sergio_so@DESKTOP-F40822T:~/o_o$ icat disk.flag.img -o 411648 1782
Salted__0��!�-6V����0�U��l��&�:�pj_1�0�|�h
                                          �Ȥ7� ���؎$�%

```

Debemos extraer y guardar el archivo para cambiar su extensión, con `icat disk.flag.img -o 411648 1782 > flag.txt.enc` podemos hacerlo, `411648` es la dirección de la partición y `1782` la dirección del archivo.

Ahora que tenemos el archivo debemos encontrar la contraseña para desencriptarlo. Para encontrarlo leemos el siguiente archivo:
```bash
sergio_so@DESKTOP-F40822T:~/o_o$ icat disk.flag.img -o 411648 1875
touch flag.txt
nano flag.txt
apk get nano
apk --help
apk add nano
nano flag.txt
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
```

La contraseña es `unbreakablepassword1234567`, con el siguiente comando lo desencriptamos.
```bash
sergio_so@DESKTOP-F40822T:~/o_o$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
409747D0497F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:124:
```

Con un `cat` podemos leerlo y obtener la bandera.
```bash
sergio_so@DESKTOP-F40822T:~/o_o$ cat flag.txt
picoCTF{h4un71ng_p457_0a710765}
```
