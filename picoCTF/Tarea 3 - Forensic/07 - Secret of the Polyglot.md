## Descripción
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).

El Centro de Operaciones de Red (NOC) de tu institución local detectó un archivo sospechoso, y están recibiendo información contradictoria sobre qué tipo de archivo es. Te han llamado como experto externo para examinarlo. ¿Puedes extraer toda la información de este archivo extraño? Descarga el archivo sospechoso aquí.
## Solución
Si intentamos abrir  el pdf nos aparecerá un error, si usamos `file flag2of2-final.pdf` veremos que el archivo realmente es una imagen `.png`, usamos `mv flag2of2-final.pdf flag2of2-final.png` para cambiar la extensión del archivo, si abrimos la imagen resultante obtendremos una parte de la bandera.
![[Imagen 05 - Secret of the Polyglot.png]]

Si usamos `binwalk  flag2of2-final.png` para verificar que el archivo no tenga dentro otros archivos, como resultado tenemos lo siguiente.
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 50 x 50, 8-bit/color RGBA, non-interlaced
914           0x392           PDF document, version: "1.4"
1149          0x47D           Zlib compressed data, default compression
```

Como si existen más archivos usamos `binwalk -e flag2of2-final.png`, abrimos la carpeta que se creó, veremos 2 archivos, un archivo de texto y un archivo comprimido `.zlib`, usamos `cat 47D` para leer elcarchivo de texto, veremos lo siguiente:
```
q 0.1 0 0 0.1 0 0 cm
0 g
q
10 0 0 10 0 0 cm BT
/R7 16 Tf
1 0 0 1 50 250 Tm
(1n_pn9_&_pdf_90974127})Tj
ET
Q
Q
```

Ahí podemos ver la otra parte de la bandera, quedando como `picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}`