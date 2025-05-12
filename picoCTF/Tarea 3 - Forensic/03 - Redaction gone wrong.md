## Descripción
Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

Ahora NO me ves. Este informe contiene algunos datos críticos, algunos de los cuales han sido redactados correctamente, mientras que otros no. ¿Puedes encontrar una clave importante que no fue redactada adecuadamente?
## Solución
Descargamos y abrimos el archivo con `open Financial_Report_for_ABC_Labs.pdf`, en mi caso se abre con `LibreOficce`, el archivo son textos que fueron "censurados", pero podemos mover los textos y los recuadros negros que ocultan la información, la bandera se encuentra en un texto tapado por un recuadro, la bandera es `picoCTF{C4n_Y0u_S33_m3_fully}`