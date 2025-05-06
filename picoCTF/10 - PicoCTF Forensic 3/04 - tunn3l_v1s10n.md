## Descripción
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

Encontramos este archivo. Recupera bandera.
## Solución
Al descargar el archivo podemos ver que no tiene extensión, con comando `file` no podemos ver nada, al ver la cabecera en hexadecimal del archivo con `xxd tunn3l_v1s10n | head` y vemos que comienza con `BM`, podemos inferir que el archivo es `.bmp` con el comando `mv tunn3l_v1s10n tunn3l_v1s10n.bmp`, intentamos abrir el archivo pero sale corrupto, así que intentaremos reparar el archivo con un editor hexadecimal, siguiendo los siguientes pasos:
1. Con el comando `hexeditor tunn3l_v1s10n.bmp` abrimos el editor, los datos de las primeras líneas están de la siguiente manera:
```
	00000000  42 4D 8E 26  2C 00 00 00   00 00 BA D0  00 00 BA D0
	00000010  00 00 6E 04  00 00 32 01   00 00 01 00  18 00 00 00
	00000020  00 00 58 26  2C 00 25 16   00 00 25 16  00 00 00 00
```
2. Debemos editar las siguientes líneas: 
```
00000000  42 4D 8E 26  2C 00 00 00   00 00 28 00  00 00 28 00
00000010  00 00 6E 04  00 00 40 04   00 00 01 00  18 00 00 00
00000020  00 00 58 26  2C 00 25 16   00 00 25 16  00 00 00 00
```

Dentro de las cosas que cambiamos fueron, el offset de donde termina la cabecera y el tamaño de la imagen. Una vez modificado el archivo al intentar abrirlo vemos lo siguiente:
![[Imagen 02 - tunn3l_v1s10n.png]]
La bandera es `picoCTF{qu1t3_a_v13w_2020}`