## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg)

Las muñecas Matryoshka son un conjunto de muñecas de madera de tamaño decreciente colocadas una dentro de otra. ¿Cuál es la última? Imagen: esta.
## Solución
Al descargar la imagen y abrirla podemos ver que es una muñeca.
![[Imagen 01 - Matryoshka doll.png]]

Al usar el comando `binwalk dolls.jpg` nos muestra:
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378952, uncompressed size: 383937, name: base_images/2_c.jpg
651610        0x9F15A         End of Zip archive, footer length: 22
```

Podemos ver que dentro de la imagen existe otra imagen, con el comando `binwalk -e dolls.jpg` podemos extraer la imagen dentro, nos creara una carpeta con el nombre de la imagen y dentro un archivo `.zip` y otra carpeta llamada `base_images` dentro esta la imagen que estaba dentro de la imagen,  aplicar de nuevo el primer comando a la imagen veremos que existe otra imagen dentro, así que deberemos repetir el proceso hasta obtener la bandera.

Al final obtendremos un archivo `flag.txt` y con el comando `cat` lo leemos y obtenemos la bandera `picoCTF{96fac089316e094d41ea046900197662}`