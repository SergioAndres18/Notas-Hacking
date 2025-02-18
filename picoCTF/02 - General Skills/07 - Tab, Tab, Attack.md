## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip)

Usar la autocompletación con Tab en la terminal te añadirá años de vida, especialmente cuando trabajas con estructuras de directorios largas y nombres de archivos extensos: [Addadshashanammu.zip](https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip)
## Solución
Con el comando `unzip` descomprimimos el archivo .zip, el cual nos da varias carpetas anidadas, para meternos a la siguiente carpeta ingresamos el comando `cd` y el nombre la primer carpeta junto un / y podemos darle a la tecla tabulador para escribir rápidamente la siguiente carpeta, así hasta que ya no haya carpetas.

Al ubicarnos en la ultima carpeta ejecutamos el comando `ls` para ver los archivos en la misma, solo existe uno, con el comando `strings fang-of-haynekhtnamet | grep -i "pico"` obtenemos la bandera `picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}`