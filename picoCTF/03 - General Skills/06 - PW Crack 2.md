## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.

¿Puedes descifrar la contraseña para obtener la bandera? Descarga el verificador de contraseñas aquí y necesitarás la bandera encriptada en el mismo directorio.
## Solución
Al ejecutar script de Python con el comando `python level1.py` nos pedirá una contraseña. Para conocerla debemos abrir el script con un editor de texto o de código y buscar dentro la contraseña. La contraseña se encuentra dentro de la función `level_2_pw_check` en la condición del `if (user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39))`, para obtener la contraseña tenemos que realizar los comando en Python `chr(0x34)`, `chr(0x65)`, `chr(0x63)` y `chr(0x39)`. La contraseña es '4ec9'.
```
La bandera es:
picoCTF{tr45h_51ng1ng_9701e681}
```