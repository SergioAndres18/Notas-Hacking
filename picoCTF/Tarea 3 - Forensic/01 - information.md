## Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)

Los archivos siempre pueden modificarse de forma secreta. ¿Puedes encontrar la bandera? cat.jpg
## Solución
Al descargar la imagen e intentar abrirla solo nos muestra una imagen de un gato.
![[Imagen 01 - information.png]]

En las pistas dentro de picoCTF nos indican que veamos los detalles del archivo, esto lo podemos hacer con `exiftool cat.jpg` que nos muestra lo siguiente:
```
ExifTool Version Number         : 12.40
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 KiB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2025:05:11 13:52:50-06:00
File Inode Change Date/Time     : 2025:05:11 13:52:07-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```

En la parte de `License` podemos ver una cadena en base 64, la cual es `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`, podemos usar el comando `echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d` para desencriptarlo. La bandera es `picoCTF{the_m3tadata_1s_modified}`
