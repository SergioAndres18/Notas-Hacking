## Descripción
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
Este es un archivo de texto realmente extraño, ¿TXT? ¿Puedes encontrar la bandera?
## Solución
Podemos intentar leer el archivo con un lector hexadecimal usando el comando `xxd -l 200 flag.txt`
```
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
00000020: 9a00 0000 0173 5247 4200 aece 1ce9 0000  .....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 0026 9549 4441 5478 5eed dd6b  R$...&.IDATx^..k
00000060: 421b 39b7 05d0 3b2e 0694 f130 9a4c 2683  B.9...;....0.L&.
00000070: f9ae 5f80 4e3d 25bb 4cb3 f15a bfba a14a  .._.N=%.L..Z...J
00000080: 7574 2413 7927 c0ff fd0f 0000 0000 4826  ut$.y'........H&
00000090: e303 0000 0080 6c32 3e00 0000 00c8 26e3  ......l2>.....&.
000000a0: 0300 0000 806c 323e 0000 0000 c826 e303  .....l2>.....&..
000000b0: 0000 0080 6c32 3e00 0000 00c8 26e3 0300  ....l2>.....&...
000000c0: 0000 806c 323e 0000                      ...l2>..
```
En los primeros valores hexadecimales podemos ver que el archi no es un `.txt` sino un `.png`, usando el comando `mv flag.txt flag.png` podemos cambiar la extensión del archivo, una vez en formato `.png` abrimos la imagen con `eog flag.png

![[Imagen 02 - extensions.png]]