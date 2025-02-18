## Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) might help!
¿Puedes revisar los datos en este binario: static? ¡Este script de BASH podría ayudarte!
## Solución
1. Al ejecutar el archivo static no arroja lo siguiente: "Oh hai! Wait what? A flag? Yes, it's around here somewhere!" Para obtener la bandera podemos usar el comando `strings static | less`el cual nos da las cadenas de un archivo binario, dentro de las cadenas que nos muestra, se puede observar la bandera fácilmente.
2. Otra posible solución es usar el comando `strings static | grep pico`. El cual nos da también la bandera
3. Por último podemos usar el script BASH para obtener el resultado.
```
./ltdis.sh static
cat static.ltdis.strings.txt | grep pico
```

```
La bandera es:
picoCTF{d15a5m_t34s3r_98d35619}
```
