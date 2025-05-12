## Descripción
How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/128/unknown.zip).

¿Qué tal un juego de escondidas? Descarga este archivo aquí.
## Solución
Al descargar la imagen e intentar abrirla solo nos muestra una imagen de un gato.
![[Imagen 04 - CanYouSee.png]]

En las pistas dentro de picoCTF nos indican que veamos los detalles del archivo, esto lo podemos hacer con `exiftool ukn_reality.jpg` que nos muestra lo siguiente:
```
ExifTool Version Number         : 12.40
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.2 MiB
File Modification Date/Time     : 2024:03:11 18:05:51-06:00
File Access Date/Time           : 2025:05:11 19:06:34-06:00
File Inode Change Date/Time     : 2025:05:11 19:06:20-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
```

En la parte de `Attribution URL` podemos ver una cadena en base 64, la cual es `cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==`, podemos usar el comando `echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==" | base64 -d` para desencriptarlo. La bandera es `picoCTF{ME74D47A_HIDD3N_3b9209a2}`