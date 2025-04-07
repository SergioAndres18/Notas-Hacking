## Descripción
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).
Encuentra la bandera en esta imagen.
## Solución
La herramienta `exiftool` sirve para **leer, escribir y modificar metadatos** de archivos, especialmente de imágenes (como `.jpg`, `.png`, `.tiff`), pero también funciona con videos, audios, PDFs y muchos otros tipos de archivo. Es muy útil para ver información como la fecha de captura, modelo de cámara, ubicación GPS, y otros datos incrustados por dispositivos o software. También permite editar o eliminar esos metadatos, lo cual es útil para preservar la privacidad o para organizar archivos según su contenido.

Se puede usar el comando `sudo apt install exiftool` para instalar la herramienta. Y usando el comando `exiftool pico_img.png` obtenemos lo siguiente:
```
ExifTool Version Number         : 12.40
File Name                       : pico_img.png
Directory                       : .
File Size                       : 106 KiB
File Modification Date/Time     : 2020:10:26 12:38:23-06:00
File Access Date/Time           : 2025:04:07 12:24:02-06:00
File Inode Change Date/Time     : 2025:04:07 12:24:02-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360
```

Dentro del metadato `Artist` podemos ver la bandera `picoCTF{s0_m3ta_d8944929}`