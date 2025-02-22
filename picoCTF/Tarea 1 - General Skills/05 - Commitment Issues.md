## Descripción
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/75/challenge.zip)

Accidentalmente escribí la bandera. ¡Por suerte la borré! Puedes descargar los archivos del desafío aquí:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/75/challenge.zip)
## Solución
Con el comando `git log` podemos ver el historial de commits en el repositorio y depues con el comando `git checkout ID_de_commit` o `git switch --detach ID_de_commit` para nos movemos a la versión del commit especificado, por último con el comando `cat message.txt` vemos la bandera dentro de archivo, la cual es `picoCTF{s@n1t1z3_9539be6b}`
## Referencias
https://primer.picoctf.org/#_git_version_control