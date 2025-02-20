## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

¿Puedes descifrar la contraseña para obtener la bandera? Descarga el verificador de contraseñas aquí y necesitarás la bandera encriptada en el mismo directorio.
## Solución
Al ejecutar script de Python con el comando `python level1.py` nos pedirá una contraseña. Para conocerla debemos abrir el script con un editor de texto o de código y buscar dentro la contraseña. En este caso se encuentra dentro de la función `level_1_pw_check()` en la línea 19, la contraseña es `691d`.
```
La bandera es:
picoCTF{545h_r1ng1ng_56891419}
```