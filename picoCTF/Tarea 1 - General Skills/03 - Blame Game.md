## Descripción
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/159/challenge.zip)

Parece que los commits de alguien están impidiendo que el programa funcione. ¿Quién es? Puedes descargar los archivos del desafío aquí:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/159/challenge.zip)
## Solución
Para conocer quien esta realizando commits usamos el comando `git log -- message.py` se utiliza para mostrar el historial de commits relacionados con el archivo.  Al hacer esto nos muestra lo siguiente:
```
commit 23e9d4ce78b3cea725992a0ce6f5eea0bf0bcdd4
Author: picoCTF{@sk_th3_1nt3rn_81e716ff} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    optimize file size of prod code

commit 3ce5c692e2f9682a866c59ac1aeae38d35d19771
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000
```

En el primer commit podemos encontrar la bandera en el autor del mismo.
## Referencias
https://primer.picoctf.org/#_git_version_control