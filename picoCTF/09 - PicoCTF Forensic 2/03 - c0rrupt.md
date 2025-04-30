## Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Encontramos este archivo. Recupera la bandera
## Solución
Si vemos que tipo de archivo es con `file mystery` vemos que el archivo no tiene datos.
Observando el encabezado del archivo con `xxd mystery | head` vemos que es un archivo PNG corrupto ya que la extensión esta modificada.

Con `hexeditor mystery` podemos editar los valores hexadecimales del archivo
![[Imagen 03 - c0rrupt 01.png]]

Para corregirlo editamos la cabecera del archivo modificando los primeros valores a `89 50 4E 47 0D 0A 1A 0A`
También los hay varios chunks (IDHR, pHYs e IDAT) están corruptos que son bloques estructurados de datos que contienen información específica como cabecera, metadatos, paletas de colores, imagen y compresión.
```
IDHR -> 00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52
pHYs -> 00000040  00 09 70 48  59 73 00 00   16 25 00 00  16 25 01 49
IDAT -> 00000050  52 24 F0 00  00 FF A5 49   44 41 54 78  5E EC BD 3F
```

Una vez corregido el archivo con  `open mystery` podemos abrir la imagen y ver la bandera
![[Imagen 04 - c0rrupt 02.png]]